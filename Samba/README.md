# Asistente Samba para Qwen CLI

Plantilla avanzada para configurar Samba en sistemas Linux usando Qwen CLI.

## Descripción

Este proyecto contiene un template de asistente para Qwen CLI que permite configurar fácilmente comparticiones Samba en sistemas Linux. Ofrece dos modos de operación: generación de reporte inicial del estado actual de Samba o configuración directa paso a paso de un nuevo servicio Samba.

## Características

- **Doble modo de operación**: Reporte de estado o configuración directa
- **Soporte multi-distribución**: Compatible con Manjaro, Ubuntu, Fedora y otras
- **Integración con servicios de red**: WINS, Avahi y NetBIOS
- **Manejo de errores**: Recuperación automática y procedimientos de rollback
- **Seguridad**: No almacena contraseñas root, backup automático de configuraciones
- **Diagnóstico**: Comandos específicos para verificación y troubleshooting
- **Reportes**: Generación de informes HTML detallados

## Instalación

1. Copiar `samba_assistant.toml` al directorio `~/.qwen/commands/`
2. Reiniciar Qwen CLI para cargar el nuevo comando

## Uso

```
samba_assistant
```

El asistente guiará al usuario a través de todas las etapas necesarias para evaluar o configurar el servicio Samba.

## Estructura del Proyecto

- `samba_assistant.toml`: Template principal del asistente
- `archive/`: Archivos de ejemplo y logs de desarrollo
- `conversation_logs/`: Resumen del proceso de desarrollo para referencia futura

## Contribuciones

Las contribuciones son bienvenidas. Por favor, abre un issue para discutir cambios antes de enviar un pull request.

## Licencia

Este proyecto está licenciado bajo los términos descritos en el archivo LICENSE (si existe).