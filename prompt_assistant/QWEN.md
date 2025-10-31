Habla, piensa y escribe siempre en Castellano.

## Asistente para Crear Prompt Templates

Este proyecto contiene un template para Qwen CLI que sirve como guía para crear otros prompt templates de alta calidad.

### Componentes principales:

- `prompt_assistant.toml`: Template de asistente para crear otros prompts templates
- Archivos de ejemplo y documentación en el directorio prompt_assistant
- Scripts de creación y verificación

### Funcionalidades:

1. **Workflow completo**:
   - Determinación del propósito del nuevo template
   - Recopilación de información sobre buenas prácticas
   - Planificación de la estructura
   - Preguntas al usuario para personalizar el template
   - Creación del archivo .toml
   - Validación de elementos importantes
   - Generación de documentación
   - Registro del proceso de creación
   - Propuesta de pruebas
   - Refinamiento basado en feedback

2. **Características técnicas**:
   - Metadatos completos
   - Manejo de errores y recuperación
   - Validaciones y comprobaciones
   - Documentación integrada
   - Consideraciones de seguridad
   - Soporte para diferentes dominios
   - Funcionalidades de backup/rollback
   - Informes y seguimiento

3. **Seguridad**:
   - Consideración de aspectos de seguridad en los templates generados
   - Validación de los elementos creados
   - Confirmación de operaciones importantes

### Uso:

1. El template se encuentra en `./prompt_assistant.toml`
2. Copiar al directorio `~/.qwen/commands/` para usarlo con Qwen CLI
3. Ejecutar el asistente con `prompt_assistant`

### Estructura del proyecto:

- `prompt_assistant.toml` - Template principal para crear prompts templates
- `conversation_logs/` - Registros del proceso de desarrollo
- `QWEN.md` - Documentación relevante para iteraciones futuras
- `README.md` - Documentación para GitHub

### Instrucciones para iteraciones futuras:

- Cada vez que se realicen modificaciones al template `.toml`, actualice según sea necesario los archivos de registro de conversación en `conversation_logs/`
- Modifique este archivo `QWEN.md` para reflejar nuevas funcionalidades o cambios importantes
- Actualice el archivo `README.md` en GitHub para mantener la documentación al día
- Considere crear entradas en el changelog para nuevas versiones
- Cree un backup de la versión anterior en un subdirectorio `.backup` antes de realizar cambios significativos
- Documente los cambios realizados en los archivos de log y en este archivo QWEN.md
