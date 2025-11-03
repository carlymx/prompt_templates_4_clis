[ESPAÑOL](README_ES.md) | [ENGLISH](README.md)

# Documentación de Proyectos Qwen CLI

Este directorio contiene varios asistentes para Qwen CLI que facilitan diferentes tareas de desarrollo y configuración.

## Asistentes Disponibles

- **angular_project_assistant**: Herramienta para crear proyectos de Angular con configuración interactiva y personalizable
- **prompt_assistant**: Plantilla para crear otros prompt templates de alta calidad
- **samba_assistant**: Asistente para configurar Samba en sistemas Linux
- **server_assistant**: Asistente para levantar servidores HTTP locales con Python
- **doc_update**: Asistente para crear y actualizar archivos de documentación (nuevo)

## Características Comunes

Todos los asistentes siguen una estructura consistente:

- Archivo `.toml` con el template del asistente
- Documentación en español e inglés
- Instrucciones para iteraciones futuras en `QWEN.md`
- Registro de conversaciones en `.chat_log/resumen_conversacion.md`

## Uso

Cada asistente se puede usar ejecutando su nombre como comando en Qwen CLI después de copiar su archivo `.toml` al directorio `~/.qwen/commands/`.

## Nuevo Asistente: doc_update

El asistente `doc_update` es un asistente recién creado que facilita la creación y actualización de archivos de documentación para proyectos CLI, incluyendo:

- README.md
- README_ES.md
- QWEN.md
- .chat_log/resumen_conversacion.md

Incluye enlaces bilineales entre los READMEs y procesa la información del chat log.