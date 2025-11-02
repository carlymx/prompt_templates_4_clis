# Asistente CLI para Servidores

Un asistente CLI para gestionar servidores HTTP locales con Python. Esta herramienta permite a los usuarios iniciar fácilmente servidores HTTP locales usando el módulo incorporado de Python `http.server`, con características adicionales para detección de servidores y consideraciones de seguridad.

## Tabla de Contenidos
- [Características](#características)
- [Uso](#uso)
- [Configuración](#configuración)
- [Consideraciones de Seguridad](#consideraciones-de-seguridad)
- [Licencia](#licencia)
- [Read in English](./README.md)

## Características

- Iniciar servidores HTTP locales con el módulo `http.server` de Python
- Validación de directorio y permisos
- Verificación de disponibilidad de puertos
- Análisis del sistema para detectar servidores persistentes
- Opciones dinámicas según el estado del servidor
- Notificaciones de seguridad y buenas prácticas
- Manejo de errores para escenarios comunes

## Uso

El asistente ayuda a los usuarios a iniciar servidores HTTP solicitando el directorio y puerto:

```bash
# Ejemplo de cómo el asistente guía al usuario
```

## Configuración

El asistente utiliza un archivo de plantilla TOML (`server_assistant.toml`) con la siguiente estructura:
- Metadatos (nombre, versión, descripción)
- Prompts del sistema y del usuario
- Fases del flujo de trabajo
- Requisitos de validación
- Escenarios de manejo de errores

## Consideraciones de Seguridad

- No apto para uso en producción
- Solo para redes locales o de confianza
- Todos los archivos en el directorio serán accesibles
- Verificar permisos de archivos sensibles
- Detener con Ctrl+C cuando ya no sea necesario

## Licencia

Licencia MIT

[Read in English](./README.md)