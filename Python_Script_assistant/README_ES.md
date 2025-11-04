[ESPAÑOL](README_ES.md) | [ENGLISH](README.md)

# Documentación del Template: Python Script Assistant

## Descripción del Proyecto

El template `python_script_assistant` es un asistente especializado en la creación de scripts Python para automatizar tareas comunes del sistema, ya sea en modo CLI o GUI. Se basa en la estructura genérica de scripts Python documentada en `estructura_genericas_scripts_python.md` y proporciona una base sólida para desarrollar herramientas de línea de comandos o interfaces gráficas.

## Características Principales

- **Estructura estándar**: Implementa la estructura genérica de Python con cabecera, manejo de dependencias, logging, etc.
- **Compatibilidad multiplataforma**: Soporta tanto Windows como Linux con detección automática del sistema operativo
- **Manejo de dependencias automático**: Verifica e instala bibliotecas necesarias en un entorno virtual
- **Interfaz coloreada**: Uso de Colorama para mejorar la legibilidad de la salida (con clase sustituta si no está disponible)
- **Sistema de logging**: Registro de eventos y errores en archivos de texto
- **Manejo de seguridad**: Validación de entradas y verificación de permisos

## Instrucciones de Uso

1. El asistente se activa con un prompt del usuario que describe la tarea específica a automatizar
2. El asistente guía al usuario a través de preguntas para definir las características del script
3. Se implementa el script con la estructura genérica de Python
4. Se incluyen las funciones específicas para la tarea de automatización
5. Se generan archivos de documentación y log si es necesario

## Estructura del Proyecto

- `Python_Script_assistant.toml`: El archivo de configuración del asistente
- `estructura_genericas_scripts_python.md`: Documentación con la estructura genérica de scripts Python
- `QWEN.md`: Instrucciones para futuras iteraciones
- `README_ES.md`: Documentación principal del proyecto en español (este archivo)

## Instrucciones para Iteraciones Futuras

1. **Actualización de funcionalidades**: Si se añaden nuevas características a los scripts CLI, actualizar `Python_Script_assistant.toml` y la documentación
2. **Mantenimiento de compatibilidad**: Asegurar que el template sigue siendo compatible con la estructura genérica documentada
3. **Mejora de seguridad**: Incorporar nuevas prácticas de seguridad según evolucionen los requisitos
4. **Expansión de ejemplos**: Añadir ejemplos de scripts para nuevos tipos de tareas de automatización
5. **Soporte multiplataforma**: Verificar y mejorar la compatibilidad con más sistemas operativos si es necesario

## Archivos de Documentación

- [README en español](README_ES.md)
- [README en inglés](README.md)
- [Instrucciones para Qwen CLI](QWEN.md)
- [Estructura genérica de scripts Python](./ref/estructura_genericas_scripts_python.md)
- [Resumen de conversaciones](.chat_log/resumen_conversacion.md)