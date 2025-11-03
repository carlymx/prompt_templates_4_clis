Habla, piensa y escribe siempre en Castellano.

# Instrucciones para Futuras Iteraciones

## Estructura del Proyecto

- Los archivos `*.toml` contienen las configuraciones de los asistentes CLI
- Los directorios contienen la documentación (README.md, README_ES.md), instrucciones (QWEN.md) y registros (conversation_logs/)
- El asistente `doc_update` puede utilizarse para actualizar esta documentación

## Consideraciones Importantes

- Cada asistente tiene su propia estructura de directorio con archivos de documentación
- Al crear nuevos asistentes, se debe seguir la estructura común: .toml, README.md, README_ES.md, QWEN.md, .chat_log/resumen_conversacion.md
- El asistente `doc_update_assistant` automatiza la creación y actualización de los archivos de documentación
- Todos los READMEs deben incluir enlaces bilineales entre sí
- La información del .chat_log debe integrarse en QWEN.md

## Mantenimiento

- Para actualizar la documentación de cualquier subproyecto, se puede usar el asistente `doc_update_assistant`
- Mantener la consistencia en la estructura de documentación entre todos los asistentes
- Asegurar que los archivos QWEN.md contengan instrucciones útiles para iteraciones futuras