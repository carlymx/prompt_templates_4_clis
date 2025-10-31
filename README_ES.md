[Versión en Español](README_ES.md) | [English Version](README.md)


# Plantillas de Prompts para CLI de IA

Colección profesional de plantillas de prompts depuradas para herramientas de IA por línea de comandos.

## Descargo de Responsabilidad

No me hago responsable de ningún resultado derivado del uso de estas plantillas de prompts. Los usuarios asumen todos los riesgos y responsabilidades por:

- Cualquier modificación del sistema, cambios en archivos o comandos ejecutados
- Pérdida de datos, corrupción o consecuencias no deseadas
- Implicaciones de seguridad al ejecutar comandos generados por IA
- Problemas de compatibilidad con entornos o configuraciones específicas
- Impactos en el rendimiento de sistemas o aplicaciones

Estas plantillas se proporcionan "tal cual" con fines educativos y de productividad. Dado que todo está en lenguaje natural, te animo a **revisar y modificar cualquier comando** para adaptarlo a tus necesidades específicas antes de probarlo.

Siempre:
- Revisa los comandos antes de ejecutarlos
- Prueba primero en entornos seguros
- Mantén copias de seguridad adecuadas
- Comprende las implicaciones de cada operación
- Personaliza las plantillas para tu caso de uso particular

Úsalas bajo tu propia discreción y riesgo.

## ¿Qué es esto?

Los LLMs modernos con capacidades agenticas nos permiten comandar la terminal mediante instrucciones estructuradas en lenguaje natural. Estas plantillas de prompts proporcionan flujos de trabajo completos que guían a los asistentes de IA a través de procedimientos complejos con objetivos claros.

A diferencia de los prompts simples de una línea, estas plantillas ofrecen flujos de trabajo completos y probados para propósitos específicos.

## Características Principales

Basándote en mi estructura de plantillas, encontrarás:

- **Metadatos Completos** - Nombre, versión, descripción y localización
- **Flujos de Trabajo Estructurados** - Ejecución por fases con progresión clara
- **Manejo Integral de Errores** - Procedimientos de recuperación y validación
- **Documentación Integrada** - Guías y ejemplos incorporados
- **Consideraciones de Seguridad** - Medidas de seguridad y mejores prácticas
- **Gestión de Backups** - Control de versiones y capacidades de rollback
- **Requisitos de Validación** - Comprobaciones previas a la ejecución y verificación de herramientas

## La IA es Tu Co-piloto

Estas plantillas representan el esfuerzo colaborativo entre la experiencia humana y la asistencia de IA. Crear prompts efectivos requiere:

- Comprensión clara de tus objetivos
- Múltiples iteraciones y pruebas
- Explicaciones detalladas de los flujos de trabajo
- Refinamiento continuo basado en resultados

Si bien la IA acelera el desarrollo, exige una comunicación precisa y un pensamiento estructurado para lograr los resultados deseados.

## 🚀 Configuración Rápida

1. Copia los archivos `.toml` de cualquier categoría a tu directorio de configuración de CLI:
   - `~/.qwen/commands/` (Qwen CLI)
   - `~/.gemini/commands/` (Gemini CLI)

2. Reinicia tu CLI y presiona `/` para descubrir nuevos comandos

3. Ejecuta las plantillas directamente:
```bash
qwen document-code
gemini analyze-data
```
Para SHAI de momento no hay una implementación directa [Lee la aclaración](./shai_import.md)


## Licencia

Licencia MIT
