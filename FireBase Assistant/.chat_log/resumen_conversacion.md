### Resumen de Contexto: Asistente de Firebase

**Objetivo Principal:**
Crear una plantilla de prompt TOML sofisticada y robusta para un asistente de línea de comandos que guía a los usuarios en la configuración de proyectos de Firebase.

**Artefacto Final:**
- `prompt_template.toml`: La versión final de la plantilla de prompt creada durante esta sesión.

**Características Clave Implementadas:**
- **Multilingüe:** Todo el contenido está en español.
- **Modos Duales:**
    - **Modo de Configuración:** Guarda las opciones en un archivo `firebase_setup.json` sin ejecutar nada.
    - **Modo Directo:** Ejecuta comandos en tiempo real con confirmación previa.
- **Gestión de Estado:**
    - Comprueba si existe un archivo `firebase_setup.json` al inicio y ofrece opciones (ejecutar, editar, borrar).
    - Pregunta si se desea ejecutar la configuración después de guardarla.
- **Robustez y Seguridad:**
    - **Validación de Entradas:** Comprueba que los datos del usuario (como el ID del proyecto) tengan el formato correcto.
    - **Manejo de Errores:** Proporciona mensajes de error claros y sugiere soluciones.
    - **Confirmación de Usuario:** Requiere confirmación antes de ejecutar cualquier acción destructiva o de creación en el Modo Directo.
    - **Navegación Flexible:** Permite al usuario volver al paso anterior.
- **Análisis de Contexto:**
    - Escanea archivos `*.md` en el directorio para obtener contexto y autocompletar sugerencias.
- **Reporte Final:**
    - Genera un reporte `firebase_setup_report.html` con un resumen completo de la sesión, incluyendo acciones, éxitos, errores y soluciones.
- **Metadatos:**
    - Incluye una caja de información en la plantilla con versión, autor, fecha y descripción.

**Instrucciones para Uso Futuro:**
Para continuar trabajando en esta plantilla, utiliza el contenido de `prompt_template.toml` como punto de partida. El resumen anterior te ayudará a recordar la lógica y las características implementadas.
