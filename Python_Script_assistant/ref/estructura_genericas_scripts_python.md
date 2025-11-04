# Estructura Genérica de Scripts Python

Este documento describe las características comunes y la estructura genérica extraída de los scripts Python de ejemplo, con el objetivo de servir como Prompt Template para crear nuevos scripts con funcionalidades similares.

## 1. Cabecera con Metadatos y Arte ASCII

### Descripción

La mayoría de los scripts comienzan con un encabezado que combina un arte ASCII decorativo con metadatos del script, como nombre, versión, autor y fecha.

### Características

* **Arte ASCII:** Un bloque de caracteres ASCII que forma una imagen o texto decorativo.
* **Metadatos:** Información estructurada sobre el script:
  * Nombre del script
  * Versión
  * Fecha de lanzamiento
  * Autor y contacto (email)
* **Comentarios `#`:** Se usan para delimitar visualmente la cabecera.

### Ejemplo de Prompt Template

```python
#!/usr/bin/env python3
##################################################################
#                                                                #
#                  NOMBRE DEL NUEVO SCRIPT                       #
#                   Vx.x (FECHA ESPERADA)                        #
#             <NOMBRE_USUARIO> - user@mail.com                   #
#                                                                #
##################################################################

# Importación de bibliotecas estándar (sys, os, platform, etc.)
import os
import sys
# ... más importaciones
```

## 2. Detección del Sistema Operativo

### Descripción

Los scripts utilizan la biblioteca `platform` para identificar dinámicamente el sistema operativo en el que se están ejecutando (por ejemplo, Windows o Linux). Esta información es crucial para:

* Adaptar rutas de archivos y directorios específicos del sistema.
* Determinar comandos específicos del sistema operativo (como `cls` o `clear`).
* Ajustar la lógica de instalación de dependencias (por ejemplo, rutas de `Scripts` en Windows vs `bin` en Linux).

### Características

* **Uso de `platform.system()`:** Se llama a esta función para obtener una cadena como "Windows", "Linux" o "Darwin".
* **Uso condicional basado en el SO:** La cadena resultante se utiliza en estructuras `if/elif` para ejecutar código específico del sistema operativo.

### Ejemplo de Prompt Template

```python
# ... (importaciones)
import platform
# ... (más importaciones)

# [Opcional: Definir constantes basadas en SO]
OPERATING_SYSTEM = platform.system()
IS_WINDOWS = OPERATING_SYSTEM == "Windows"
IS_LINUX = OPERATING_SYSTEM == "Linux"

# [Ejemplo de uso condicional]
def clear_screen():
    os.system('cls' if IS_WINDOWS else 'clear')

# [Otro ejemplo de uso condicional]
def get_venv_executable():
    if IS_WINDOWS:
        return os.path.join("venv", "Scripts", "python")
    else:
        return os.path.join("venv", "bin", "python")
```

## 3. Instalación Automática de Dependencias

### Descripción

Para garantizar que todas las bibliotecas Python necesarias estén disponibles, los scripts implementan una lógica de verificación e instalación automática de dependencias.

* **Verificación de importación:** Se intenta importar cada biblioteca esencial.
* **Creación de entorno virtual (venv):** Si no existe un entorno virtual (`venv`), o si se está en Linux y no hay un venv activo, se crea uno nuevo.
* **Instalación con pip:** Se utiliza `subprocess` para llamar a `pip install` desde el ejecutable del entorno virtual recién creado o existente.
* **Reinicio del script:** Tras la instalación, se utiliza `os.execv` para reiniciar el script *dentro* del entorno virtual, asegurando que todas las dependencias recién instaladas estén disponibles para la ejecución principal.

### Características

* **Bloque `try...except ImportError`:** Se usa para detectar si una biblioteca está ausente.
* **Uso de `subprocess.check_call`:** Se llama a `pip` para instalar paquetes de forma no interactiva.
* **Manejo de rutas del venv:** Se construye la ruta al ejecutable de Python del venv de forma específica para Windows/Linux.
* **Reinicio con `os.execv`:** Reemplaza la imagen del proceso actual con una nueva ejecución del script en el entorno virtual.

### Ejemplo de Prompt Template

```python
# ... (importaciones)
import subprocess
import os
# ... (más importaciones)

def setup_virtualenv_and_install():
    """Crea un entorno virtual e instala las dependencias necesarias."""
    if not os.path.exists("venv"):
        print("Creando entorno virtual 'venv'...")
        subprocess.check_call([sys.executable, "-m", "venv", "venv"])

    python_exec = get_venv_executable() # [Usar la función definida en Sección 2]

    print("Instalando dependencias...")
    subprocess.check_call([python_exec, "-m", "pip", "install", "--upgrade", "pip"])
    subprocess.check_call([python_exec, "-m", "pip", "install", "Pillow", "piexif", "colorama"]) # [Lista de dependencias]
    return python_exec

def ensure_dependencies():
    """Asegura que las dependencias estén disponibles y reinicia el script en el venv si es necesario."""
    try:
        import PIL # [Bibliotecas esenciales del script]
        import piexif
        # ... otras bibliotecas
    except ImportError:
        print("Faltan dependencias. Instalando en un entorno virtual...")
        python_exec = setup_virtualenv_and_install()
        print("Reiniciando el script dentro del entorno virtual...")
        os.execv(python_exec, [python_exec] + sys.argv)

# [Llamada a esta función al inicio de main]
```

## 4. Manejo de Colorama para Salida Coloreada (si procede)

### Descripción

La biblioteca `colorama` se utiliza para imprimir texto coloreado en la consola, mejorando la legibilidad de la salida del script. Sin embargo, si `colorama` no está instalada *al inicio del script*, se necesita una estrategia para que el script no falle y siga funcionando, posiblemente instalando `colorama` posteriormente como se describe en la Sección 3. Para lograrlo, se utiliza un patrón de *clase falsa* (*mock class*) que devuelve cadenas vacías si `colorama` no está disponible.

### Características

* **`try...except ImportError` para colorama:** Se intenta importar `colorama`.
* **Clase sustituta (`EmptyColor`):** Si falla la importación, se define una clase que intercepta cualquier atributo (como `Fore.GREEN`, `Style.RESET_ALL`) y lo convierte en una cadena vacía.
* **Asignación de objetos sustitutos:** Se crean objetos `Fore`, `Style` y una función `init` sustitutos que no hacen nada.
* **Llamada a `init()`:** Se llama a `init()` al inicio para activar el soporte de color si `colorama` está disponible.

### Ejemplo de Prompt Template

```python
# ... (importaciones)

try:
    from colorama import Fore, Style, init
except ImportError:
    print("Advertencia: 'colorama' no está instalado. La salida no tendrá colores hasta que se instalen las dependencias.")
    # Clase ficticia que devuelve una cadena vacía para cualquier atributo que se le pida
    class EmptyColor:
        def __getattr__(self, name):
            return ""

    # Se crean los objetos sustitutos
    Fore = EmptyColor()
    Style = EmptyColor()

    # Función 'init' sustituta que no hace nada
    def init(autoreset=True):
        pass

init(autoreset=True) # [Se llama a init para soporte de color si está disponible]

# [El resto del script puede ahora usar Fore, Style, etc., de forma segura]
print(Fore.CYAN + "Este texto puede ser cyan" + Style.RESET_ALL)
```

Nota: Al no ser una biblioteca preinstalada de python, la utilización de esta y otras bibliotecas con el mismo problema debe hacerse después de instalarse su dependencia, no antes.

## 5. Funciones de Utilidad Comunes

### Descripción

Los scripts incluyen funciones reutilizables para tareas comunes que no forman parte directa de su lógica principal, como limpiar la pantalla o mostrar un banner.

### Características

* **`clear_screen()`:** Llama al comando del sistema (`cls` en Windows, `clear` en Unix) para limpiar la consola.
* **`print_banner()`:** Imprime el arte ASCII almacenado en una variable o string, opcionalmente con información adicional como la versión y el nombre del script, usando `colorama` para darle color.

### Ejemplo de Prompt Template

```python
# [Se asume que colorama ha sido manejado como en la Sección 4]

def clear_screen():
    os.system('cls' if IS_WINDOWS else 'clear') # [IS_WINDOWS de Sección 2]

def print_banner():
    banner = r"""
    [PON AQUÍ TU ARTE ASCII]
    """
    print(Fore.CYAN + banner)
    print(Fore.YELLOW + f"Versión {VERSION} - {SCRIPT_NAME}")
    print(Fore.YELLOW + "-------------------------------------------------\n" + Style.RESET_ALL)

# [Constantes para banner]
VERSION = "1.0"
SCRIPT_NAME = "Mi Nuevo Script"
```

## 6. Sistema de Logging

### Descripción

Los scripts implementan un sistema de logging para registrar eventos, errores y el progreso del proceso en archivos de texto (`.log`). Esto es invaluable para la depuración y auditoría.

### Características

* **Uso de la biblioteca `logging`:** Se configura un `logger` con un `FileHandler`.
* **Niveles de log:** Se utilizan niveles como `INFO` para eventos generales y `ERROR` para fallos.
* **Formato de registro:** Se define un formato estándar para las entradas del log (por ejemplo, fecha, nivel, mensaje).
* **Directorio de logs:** Se crea un directorio específico (por ejemplo, `logs/`) para almacenar los archivos de log.
* **Nombre de archivo del log:** Se genera un nombre de archivo único para cada ejecución del script, incluyendo la fecha y hora.

### Ejemplo de Prompt Template

```python
# ... (importaciones)
import logging
from datetime import datetime
import os
# ... (más importaciones)

def setup_logger(log_file_path):
    """
    Configura y devuelve un logger para registrar eventos en un archivo.
    """
    logger = logging.getLogger('mi_script_logger') # [Use un nombre único para el logger]
    logger.setLevel(logging.INFO)
    if not logger.handlers: # [Evita duplicados si la función se llama varias veces]
        file_handler = logging.FileHandler(log_file_path)
        file_handler.setLevel(logging.INFO)
        # [Opcional: Añadir un handler para consola con un nivel diferente]
        # console_handler = logging.StreamHandler()
        # console_handler.setLevel(logging.ERROR)
        formatter = logging.Formatter('%(asctime)s - %(levelname)s - %(message)s')
        file_handler.setFormatter(formatter)
        # console_handler.setFormatter(formatter)
        logger.addHandler(file_handler)
        # logger.addHandler(console_handler)
    return logger

# [En la función principal o al inicio del proceso]
def main():
    # ...
    log_dir = "logs"
    os.makedirs(log_dir, exist_ok=True) # [Crea el directorio si no existe]
    log_file = os.path.join(log_dir, f"mi_script_{datetime.now().strftime('%Y%m%d_%H%M%S')}.log")
    logger = setup_logger(log_file)
    # ...
    # [Durante el procesamiento]
    logger.info("Inicio del procesamiento de archivos.")
    # logger.error("Ocurrió un error al procesar el archivo X.")
    # ...
```

## 7. Interacción con el Usuario

### Descripción

Los scripts interactúan con el usuario para obtener configuraciones iniciales necesarias para su ejecución (directorios, formatos, niveles de compresión, etc.). En scripts de consola, se utiliza `input()`, mientras que en GUI se usan controles como campos de texto, menús desplegables y botones.

### Características (Consola)

* **`input()`:** Se usa para solicitar datos al usuario.
* **`get_input()`:** Función auxiliar común que encapsula `input()` y permite valores por defecto.
* **Confirmación de configuración:** Se muestra un resumen de las opciones elegidas antes de iniciar el procesamiento principal y se pide confirmación al usuario.

### Características (GUI - Tkinter)

* **Importación de `tkinter`:** Se importan módulos para crear la interfaz gráfica.
* **Clase principal (`ReCompresionApp`):** Contiene la lógica de la interfaz.
* **Widgets (`Tk`, `Frame`, `Label`, `Entry`, `Button`, `Combobox`, `Scale`, `ProgressBar`, `ScrolledText`):** Se utilizan para construir la interfaz visual.
* **Variables de control (`tk.StringVar`, `tk.IntVar`):** Se usan para enlazar valores de widgets a variables del programa.
* **Manejo de eventos (`command` en botones):** Se definen funciones que se ejecutan al interactuar con los controles.
* **Hilos (`threading.Thread`):** Para evitar que la interfaz se bloquee durante operaciones largas.

### Ejemplo de Prompt Template (Consola)

```python
def get_input(prompt, default=None):
    """
    Solicita entrada al usuario con un valor por defecto opcional.
    """
    value = input(Fore.YELLOW + prompt + Style.RESET_ALL)
    return value if value else default

def main():
    # ...
    # [Ejemplo de interacción]
    while True:
        src_dir = get_input("Ingrese el directorio a procesar: ")
        if not src_dir:
            print(Fore.RED + "No se ingresó directorio. Saliendo..." + Style.RESET_ALL)
            sys.exit(1)
        if not os.path.isdir(src_dir):
            print(Fore.RED + "El directorio ingresado no existe. Intente nuevamente." + Style.RESET_ALL)
            continue
        break # [Sale del bucle si el directorio es válido]

    # [Más interacciones para obtener otras configuraciones]

    # [Resumen y confirmación]
    print("\n" + Fore.YELLOW + "Opciones elegidas:" + Style.RESET_ALL)
    print(Fore.YELLOW + f"Directorio origen: {src_dir}" + Style.RESET_ALL)
    # ... imprimir otras opciones
    confirm = get_input(Fore.GREEN + "¿La configuración es correcta? (S/n): " + Style.RESET_ALL, "S").lower()
    if confirm != "s":
        print(Fore.RED + "Proceso cancelado por el usuario." + Style.RESET_ALL)
        sys.exit()
    # ...
```

### Ejemplo de Prompt Template (GUI - Tkinter)

```python
# ... (importaciones)
import tkinter as tk
from tkinter import filedialog, ttk, scrolledtext
# ... (más importaciones)

class MiAppGUI:
    def __init__(self, master):
        self.master = master
        master.title("Mi Nuevo Script GUI v1.0")
        master.geometry("800x600")
        # ... [configurar widgets como en el ejemplo original]

    def create_widgets(self):
        # ... [crear y posicionar los widgets]
        pass

    # ... [más métodos para manejar eventos de la GUI]

def main():
    root = tk.Tk()
    app = MiAppGUI(root)
    root.mainloop() # [Inicia el bucle de eventos de la GUI]
```

## 8. Manejo de Multiproceso

### Descripción

Para acelerar tareas que pueden paralelizarse (como procesar múltiples archivos), los scripts utilizan el módulo `concurrent.futures` y la clase `ProcessPoolExecutor`. Permiten al usuario elegir el número de procesos a utilizar.

### Características

* **`concurrent.futures.ProcessPoolExecutor`:** Se usa para gestionar un grupo de procesos trabajadores.
* **Función de procesamiento individual (`process_single_image`, `organize_single_file`, etc.):** Se define una función que puede procesar una unidad de trabajo (por ejemplo, un archivo) de forma aislada.
* **Creación de tareas:** Se prepara una lista de argumentos para cada llamada a la función de procesamiento individual.
* **Ejecución secuencial o multiproceso:** Se decide si usar la función de procesamiento directamente (modo 1 proceso) o a través del `ProcessPoolExecutor` (modo multiproceso).
* **Uso de `as_completed`:** Se itera sobre los futuros devueltos por el executor para manejar los resultados a medida que se completan y actualizar el progreso.

### Ejemplo de Prompt Template

```python
# ... (importaciones)
from concurrent.futures import ProcessPoolExecutor, as_completed
# ... (más importaciones)

def process_single_item(args):
    """
    Procesa una unidad de trabajo (por ejemplo, un archivo) de forma aislada.
    args: Una tupla con los argumentos necesarios.
    return: Un diccionario con el resultado del procesamiento.
    """
    # item_path, param1, param2, ... = args
    # ... [lógica de procesamiento para un solo ítem]
    result = {'src': item_path, 'ok': False, 'error': None}
    # try:
    #    ... [procesar item_path]
    #    result['ok'] = True
    # except Exception as e:
    #    result['error'] = str(e)
    return result

def run_sequential(items_list, other_params, logger):
    """
    Ejecuta el procesamiento en modo secuencial.
    """
    processed = 0
    errors = 0
    total = len(items_list)

    for idx, item_path in enumerate(items_list, start=1):
        res = process_single_item((item_path, *other_params)) # [Desempaquetar otros parámetros]
        if res['ok']:
            processed += 1
            logger.info(f"Procesado: {res['src']}")
        else:
            errors += 1
            logger.error(f"Error procesando {res['src']}: {res['error']}")
        print(f"\rProgreso: {idx}/{total} ítems procesados", end='')

    print('\nProceso secuencial finalizado.')
    return total, processed, errors

def run_multiprocess(items_list, other_params, logger, workers):
    """
    Ejecuta el procesamiento en modo multiproceso.
    """
    total = len(items_list)
    processed = 0
    errors = 0

    tasks = [(item_path, *other_params) for item_path in items_list] # [Preparar lista de argumentos]

    with ProcessPoolExecutor(max_workers=workers) as executor:
        futures = {executor.submit(process_single_item, t): t for t in tasks}
        completed = 0
        for future in as_completed(futures):
            completed += 1
            res = future.result()
            if res['ok']:
                processed += 1
                logger.info(f"Procesado: {res['src']}")
            else:
                errors += 1
                logger.error(f"Error procesando {res['src']}: {res['error']}")
            print(f"\rProgreso: {completed}/{total} ítems procesados", end='')

    print('\nProceso multiproceso finalizado.')
    return total, processed, errors

def main():
    # ... [configuración e interacción con usuario para obtener n_procs]
    n_procs = 4 # [Ejemplo: valor obtenido por el usuario o predeterminado]
    # ...
    # [Decidir e invocar la función de ejecución adecuada]
    if n_procs == 1 or len(items_list) <= 1:
        total, processed, errors = run_sequential(items_list, other_params, logger)
    else:
        total, processed, errors = run_multiprocess(items_list, other_params, logger, workers=n_procs)
    # ...
```

## Conclusión

Este documento resume las estructuras y patrones comunes extraídos de los scripts de ejemplo. Puede utilizarse como base para generar nuevos scripts con funcionalidades similares, proporcionando un Prompt Template que incluya estas características genéricas.