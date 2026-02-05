# Generador de README

[📖 Read in English](./README.md)

<!-- Sección de Badges -->
![Licencia](https://img.shields.io/badge/licencia-MIT-blue.svg)
![Versión](https://img.shields.io/badge/versión-1.0.0-green.svg)
![Tipo](https://img.shields.io/badge/tipo-skill-orange.svg)

## Descripción

Una herramienta inteligente que crea o actualiza automáticamente archivos README.md y README_ES.md bilingües completos con las mejores prácticas de GitHub. Esta skill analiza la estructura de tu proyecto, detecta el stack tecnológico y genera documentación profesional adaptada a tu tipo de proyecto específico.

## Tabla de Contenidos

- [Descripción](#descripción)
- [Características](#características)
- [Instalación](#instalación)
- [Uso](#uso)
- [Banderas de Comando](#banderas-de-comando)
- [Detección de Proyecto](#detección-de-proyecto)
- [Estructura Generada](#estructura-generada)
- [Contribuir](#contribuir)
- [Licencia](#licencia)
- [Agradecimientos](#agradecimientos)

## Características

- **Análisis Automático de Proyecto**: Detecta lenguaje de programación, framework y stack tecnológico
- **Soporte Bilingüe**: Genera versiones en inglés (README.md) y español (README_ES.md)
- **Listo para GitHub**: Incluye badges, shields y formato profesional
- **Salida Personalizable**: Múltiples banderas para controlar la generación de contenido
- **Contenido Inteligente**: Adapta la documentación según el tipo de proyecto detectado
- **Referencias Cruzadas**: Enlaces bidireccionales entre versiones de idioma

## Instalación

```bash
# Clonar el repositorio
git clone <repo-url>

# Navegar al directorio
cd readme-generator

# La herramienta está lista para usar - no requiere dependencias adicionales
```

## Uso

### Uso Básico

Ejecuta la herramienta en el directorio de tu proyecto:

```bash
# Generar archivos README bilingües completos con elementos de GitHub
<command>
```

### Uso Avanzado con Banderas

```bash
# Excluir elementos específicos de GitHub (badges, shields)
<command> --no-github

# Crear solo README en inglés
<command> --english-only

# Crear solo README en español
<command> --spanish-only

# Crear versión mínima (Título, Descripción, Instalación, Uso solamente)
<command> --simple

# Incluir secciones TODO/Roadmap basadas en análisis de código
<command> --todolist
```

### Combinación de Banderas

```bash
# Versión mínima solo en inglés sin elementos de GitHub
<command> --simple --english-only --no-github

# Versión completa en español con análisis de TODO
<command> --todolist --spanish-only
```

## Banderas de Comando

| Bandera | Descripción |
|---------|-------------|
| `--no-github` | Excluir elementos específicos de GitHub (badges, shields) |
| `--english-only` | Crear solo README.md (omitir README_ES.md) |
| `--spanish-only` | Crear solo README_ES.md (omitir README.md) |
| `--simple` | Crear versión mínima solo con secciones básicas |
| `--todolist` | Incluir secciones "Implementado" y "TODO/Roadmap" |

## Detección de Proyecto

La herramienta detecta automáticamente:

- **Lenguajes de Programación**: JavaScript, Python, Java, Go, Rust, Ruby, etc.
- **Frameworks**: React, Vue, Angular, Express, Django, Flask, etc.
- **Sistemas de Compilación**: npm, yarn, pip, Maven, Gradle, Cargo, etc.
- **Configuración de Testing**: Jest, Mocha, pytest, JUnit, etc.
- **Archivos de Configuración**: package.json, Cargo.toml, requirements.txt, etc.

## Estructura Generada

### Versión Completa (por defecto)

Ambos archivos README incluyen:

1. **Título** con enlace de cambio de idioma
2. **Badges** (licencia, versión, específicos de tecnología)
3. **Descripción** - Resumen del proyecto
4. **Tabla de Contenidos** - Enlaces de navegación
5. **Instalación** - Instrucciones de configuración paso a paso
6. **Uso** - Ejemplos claros y snippets de código
7. **Documentación API** - Documentación de funciones/endpoints
8. **Contribuir** - Guías de contribución
9. **Licencia** - Información de licencia
10. **Agradecimientos** - Créditos y agradecimientos

### Versión Simple (banderas --simple)

Estructura mínima con:

1. Título
2. Descripción
3. Instalación
4. Uso

## Contribuir

¡Agradecemos las contribuciones! Por favor, sigue estos pasos:

1. Haz fork del repositorio
2. Crea una rama de funcionalidad (`git checkout -b feature/funcionalidad-increible`)
3. Haz commit de tus cambios (`git commit -m 'Añadir funcionalidad increíble'`)
4. Haz push a la rama (`git push origin feature/funcionalidad-increible`)
5. Abre un Pull Request

Por favor, lee [CONTRIBUTING.md](CONTRIBUTING.md) para pautas detalladas.

## Licencia

Este proyecto está licenciado bajo la [Licencia MIT](LICENSE) - consulta el archivo LICENSE para más detalles.

## Agradecimientos

- Inspirado en la necesidad de documentación consistente y profesional en todos los proyectos
- Gracias a la comunidad de código abierto por la inspiración en mejores prácticas
- Agradecimientos especiales a los contribuyentes que mejoran esta herramienta
