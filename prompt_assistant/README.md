# Asistente para Crear Prompt Templates

Plantilla general para crear otros prompt templates de alta calidad usando Qwen CLI.

## Descripción

Este proyecto contiene un template de asistente para Qwen CLI que sirve como guía y herramienta para crear otros prompts templates con buenas prácticas, estructura completa y funcionalidades avanzadas.

El asistente implementa una metodología completa para el desarrollo de prompts templates que incluye: determinación de propósito, planificación de estructura, manejo de errores, validación, documentación, registro de proceso y pruebas.

## Características

- **Workflow completo**: Implementa un proceso estructurado para crear prompts templates
- **Buenas prácticas**: Incorpora elementos esenciales como metadatos, manejo de errores, validaciones, etc.
- **Personalización**: Hace preguntas al usuario para adaptar el template a sus necesidades específicas
- **Documentación integrada**: Genera archivos de documentación (QWEN.md, README.md) para futuras referencias
- **Seguridad considerada**: Incluye elementos de seguridad en los templates generados
- **Validación exhaustiva**: Asegura que se incluyan todos los elementos importantes
- **Soporte para diferentes dominios**: Adaptable a diferentes tipos de tareas y contextos

## Componentes

- `prompt_assistant.toml`: Template principal del asistente para crear otros prompts
- `conversation_logs/`: Registros del proceso de creación de templates
- `QWEN.md`: Documentación relevante para iteraciones futuras
- `README.md`: Documentación para GitHub

## Instalación

1. Copiar `prompt_assistant.toml` al directorio `~/.qwen/commands/`
2. Reiniciar Qwen CLI para cargar el nuevo comando

## Uso

```
prompt_assistant
```

El asistente guiará al usuario a través de todas las etapas necesarias para crear un prompt template personalizado y de alta calidad.

## Flujo de Trabajo

1. Determinación del propósito del nuevo template
2. Recopilación de información sobre buenas prácticas
3. Planificación de la estructura del template
4. Preguntas personalizadas al usuario
5. Creación del archivo .toml con toda la estructura
6. Validación de elementos importantes
7. Generación de documentación
8. Registro del proceso de creación
9. Propuesta de pruebas
10. Refinamiento basado en feedback

## Contribuciones

Las contribuciones son bienvenidas. Por favor, abre un issue para discutir cambios antes de enviar un pull request.

## Licencia

Este proyecto está licenciado bajo los términos descritos en el archivo LICENSE (si existe).
