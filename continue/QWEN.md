# Asistente para Reanudar Trabajo en Proyectos

## Idioma

Este asistente habla, piensa y escribe en castellano (español).

## Propósito del Proyecto

El propósito de este asistente es ayudar a reanudar el trabajo en proyectos mediante el análisis de archivos de contexto existentes. El asistente examina documentos como QWEN.md, .chat_log/resumen_conversacion.md, README.md y otros archivos de log para comprender el estado actual del proyecto y prepararse para continuar el trabajo.

## Componentes Principales

- Archivo de configuración TOML: resume_work_assistant.toml
- Sistema de análisis de contexto para leer archivos de documentación existentes
- Workflow estructurado para reanudación de trabajo

## Funcionalidades

- Análisis de archivos de contexto existentes
- Identificación del estado actual del proyecto
- Resumen de tareas completadas y pendientes
- Preparación para continuar el trabajo
- Validación de estructura y archivos necesarios

## Uso

Cuando se inicie una nueva sesión de trabajo, este asistente se encargará de analizar los archivos de contexto existentes para "ponerse al día" con el estado del proyecto y estar listo para continuar con las tareas pendientes.

## Estructura del Proyecto

- resume_work_assistant.toml: Archivo de configuración del asistente
- .chat_log/: Directorio para logs de conversaciones (si existe)
- QWEN.md: Instrucciones para iteraciones futuras
- README.md: Documentación principal del proyecto

## Instrucciones para Iteraciones Futuras

1. Analiza siempre primero los archivos de contexto existentes
2. Resume claramente el estado actual del proyecto
3. Identifica tareas pendientes o incompletas
4. Confirma que estás listo para continuar con el trabajo
5. Sigue las instrucciones específicas encontradas en archivos QWEN.md o README.md del proyecto