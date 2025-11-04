# Qwen CLI - Proyecto Pyginx: Plantilla de Scripts Python

## Descripción del Proyecto

El proyecto Pyginx es una plantilla o Prompt Template diseñada para generar nuevos scripts Python con una estructura genérica común. Se ha analizado una serie de scripts de ejemplo para extraer patrones y buenas prácticas de desarrollo, creando así una base reutilizable para desarrollar nuevos scripts de propósito general.

## Tipo de Proyecto

Este es un **proyecto de documentación y plantilla de código**, no una aplicación funcional completa. Su propósito es servir como guía y plantilla para crear nuevos scripts Python con estructuras comunes.

## Objetivo Principal

- Proporcionar una estructura genérica documentada para scripts Python
- Facilitar la creación de nuevos scripts con características comunes ya implementadas
- Documentar patrones y buenas prácticas de desarrollo de scripts Python

## Componentes Principales

### Documentación Principal

- `estructura_genericas_scripts_python.md`: Documento principal que describe la estructura genérica común extraída de scripts Python de ejemplo
- `README.md`: Documentación principal del proyecto en inglés
- `README_ES.md`: Documentación principal del proyecto en español
- `QWEN.md`: Instrucciones para futuras interacciones con Qwen CLI (este archivo)
- `instruciones.md`: Instrucciones para Qwen CLI

### Estructura Genérica Documentada

La estructura genérica incluye:

1. **Cabecera con metadatos y arte ASCII**: Bloque decorativo que incluye nombre del script, versión, autor y fecha
2. **Detección del sistema operativo**: Uso de `platform` para adaptar comportamientos según el SO
3. **Instalación automática de dependencias**: Lógica para verificar e instalar bibliotecas necesarias en un entorno virtual
4. **Manejo de Colorama para salida coloreada**: Clase sustituta para evitar errores si `colorama` no está disponible
5. **Funciones de utilidad comunes**: Funciones reutilizables como `clear_screen()` y `print_banner()`
6. **Sistema de logging**: Registro de eventos y errores en archivos de texto
7. **Interacción con el usuario**: Interfaces de consola o GUI para obtener configuración
8. **Manejo de multiproceso**: Uso de `concurrent.futures` para procesar tareas en paralelo

## Convenciones del Proyecto

### Idiomas

- La documentación se mantiene en inglés y español con enlaces mutuos
- Los comentarios en el código generan pueden estar en español (como en los ejemplos de la plantilla)

### Estructura de Documentación

- Archivos README en ambos idiomas con enlaces bilineales
- Documentación técnica detallada en `estructura_genericas_scripts_python.md`
- Archivos de contexto para Qwen CLI separados

### Convenciones de Código

- Uso de entornos virtuales (venv) para manejar dependencias
- Manejo de dependencias faltantes con instalación automática
- Soporte multilenguaje para la salida del script (con Colorama)
- Separación clara entre lógica principal y funciones auxiliares

## Archivos Importantes

- `estructura_genericas_scripts_python.md`: Contiene la plantilla completa con ejemplos de código y explicaciones detalladas
- `instruciones.md`: Contiene instrucciones para Qwen CLI sobre cómo usar este proyecto
- Carpeta `.chat_log/`: Contiene archivos de registro de conversaciones (actualmente solo `resumen_conversacion.md`)

## Uso del Proyecto

Este proyecto sirve como base para generar nuevos scripts Python con las siguientes características:

1. Copiar la estructura genérica del archivo `estructura_genericas_scripts_python.md`
2. Adaptar las secciones según las necesidades específicas del nuevo script
3. Implementar las funciones y lógica específica para el propósito del nuevo script
4. Mantener la estructura de cabecera, manejo de dependencias y logging

## Notas Especiales

- Este proyecto es una plantilla/documentación, no una aplicación funcional en sí misma
- La documentación está estructurada para servir como Prompt Template para crear nuevos scripts
- La estructura genérica es altamente adaptable y puede modificarse según las necesidades del nuevo script
- Se enfatiza en buenas prácticas como el uso de entornos virtuales y manejo de dependencias
- Se han creado archivos de template TOML para asistentes especializados en diferentes tipos de tareas
- El archivo `Python_Script_assistant.toml` es un template para crear scripts CLI o GUI de automatización
- El proyecto también incluye un mecanismo para documentar conversaciones y decisiones en `.chat_log/resumen_conversacion.md`

## Tareas Futuras

1. Actualizar `estructura_genericas_scripts_python.md` con nuevas características genéricas si se analizan más scripts de ejemplo
2. Mantener la consistencia entre las versiones en inglés y español de la documentación
3. Documentar conversaciones y decisiones importantes en `.chat_log/resumen_conversacion.md`
4. Asegurar que los enlaces bilineales entre READMEs se mantengan actualizados
5. Crear nuevos templates TOML para asistentes especializados según sea necesario
6. Mantener actualizada la documentación de los templates existentes
7. Continuar expandiendo los ejemplos de scripts tanto para CLI como para GUI en el template
8. Mejorar las validaciones y controles de seguridad en los scripts generados por los templates

## Archivos de Documentación

- [README en español](README_ES.md)
- [README en inglés](README.md)
- [Resumen de conversaciones](.chat_log/resumen_conversacion.md)
- [Estructura genérica de scripts Python](estructura_genericas_scripts_python.md)
- [Instrucciones para Qwen CLI](instruciones.md)