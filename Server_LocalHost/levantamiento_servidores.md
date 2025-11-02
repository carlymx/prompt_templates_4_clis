# Guía para Levantar Servidores HTTP Locales con Python

## Descripción
Python incluye un módulo incorporado llamado `http.server` que permite levantar rápidamente un servidor web local para servir archivos estáticos. Esta funcionalidad es especialmente útil para probar aplicaciones web locales, páginas HTML, o para compartir archivos temporalmente.

## Comando Básico

### Python 3
```bash
python3 -m http.server [puerto]
```

### Python 2 (obsoleto)
```bash
python -m SimpleHTTPServer [puerto]
```

## Parámetros

- **puerto** (opcional): Número de puerto donde se levantará el servidor (por defecto es 8000)

## Ejemplos de Uso

### Servidor en puerto por defecto (8000)
```bash
python3 -m http.server
```
Accede en: `http://localhost:8000`

### Servidor en puerto específico
```bash
python3 -m http.server 8080
```
Accede en: `http://localhost:8080`

### Servidor en un directorio específico
```bash
cd /ruta/al/directorio && python3 -m http.server 8000
```

## Importante

- El servidor sirve archivos desde el directorio donde se ejecuta el comando
- Todos los archivos del directorio (y subdirectorios) estarán accesibles
- Este servidor NO es adecuado para uso en producción
- Es ideal para desarrollo y pruebas locales
- El servidor se detiene con `Ctrl+C`

## Seguridad y Consideraciones

- Los archivos se sirven con los permisos del usuario que ejecuta el comando
- No incluye autenticación ni seguridad avanzada
- No sirve archivos ocultos (que comienzan con punto)
- Solo debe usarse en redes locales o de confianza
- Es un servidor de propósito único para desarrollo

## Compatibilidad

- Compatible con Python 3.0+
- No requiere instalación de paquetes adicionales
- Disponible en todos los sistemas donde esté instalado Python 3

## Utilidad en Desarrollo Web

- Ideal para probar aplicaciones web estáticas
- Útil para visualizar HTML, CSS y JavaScript sin problemas de CORS
- Permite probar funcionalidades que requieren un servidor HTTP (por ejemplo, AJAX)
- Perfecto para servir prototipos y demostraciones locales

## Alternativas

- Node.js: `npx http-server`
- PHP: `php -S localhost:8000`
- Ruby: `ruby -run -e httpd . -p 8000`
- Go: `goexec 'http.ListenAndServe(`:8000`, http.FileServer(http.Dir(`.`)))'`

## Prompt Template

```
Levanta un servidor HTTP local usando Python en el directorio [ruta_al_directorio] y puerto [puerto]. 
Accede a la aplicación en http://localhost:[puerto]
```

Donde:
- `[ruta_al_directorio]` es la ruta donde están los archivos a servir
- `[puerto]` es el número de puerto (por ejemplo, 8000, 8080)