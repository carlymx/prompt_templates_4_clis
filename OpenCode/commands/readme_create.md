---
description: Creates or updates comprehensive bilingual README.md and README_ES.md files with GitHub best practices
template: |
  You are creating comprehensive README files for a project. Analyze the current directory structure and project files to generate appropriate documentation.

  ## Context Analysis
  Current working directory: {{working_directory}}
  
  ## Detect Project Type
  First, analyze the project to understand:
  - Programming language(s) used
  - Framework or technology stack
  - Build system and package manager
  - Testing setup
  - Documentation structure
  - Configuration files

  ## Argument Processing
  Check for these flags in the command arguments:
  - `--no-github`: Exclude GitHub-specific elements (badges, shields)
  - `--english-only`: Create only README.md (skip README_ES.md)
  - `--spanish-only`: Create only README_ES.md (skip README.md)
  - `--simple`: Create minimal version (Title, Description, Installation, Usage only)
  - `--todolist`: Include "Implemented" and "TODO/Roadmap" sections based on code analysis

  ## Files to Create/Update

  {{#unless spanish_only}}
  ### File: README.md
  Generate a comprehensive README in English with the following structure:

  ```markdown
  # Project Title

  {{#unless no_github}}
  [📖 Leer en Español](./README_ES.md)

  <!-- Badges Section -->
  ![License](https://img.shields.io/badge/license-MIT-blue.svg)
  ![Version](https://img.shields.io/badge/version-1.0.0-green.svg)
  <!-- Add relevant badges based on project type -->
  {{/unless}}

  ## Description
  Brief, compelling description of what this project does and why it exists.

  ## Table of Contents
  - [Description](#description)
  - [Installation](#installation)
  - [Usage](#usage)
  {{#if todolist}}- [Implemented Features](#implemented-features)
  - [TODO / Roadmap](#todo--roadmap){{/if}}
  - [API Documentation](#api-documentation)
  - [Contributing](#contributing)
  - [License](#license)
  - [Acknowledgments](#acknowledgments)

  ## Installation
  Provide step-by-step installation instructions:
  ```bash
  # Clone the repository
git clone <repo-url>

  # Navigate to directory
cd project-name

  # Install dependencies
<install-command>
```

  ## Usage
  Provide clear usage examples:
  ```bash
  # Basic usage
<command>

  # Example output
  ```

  Include code examples if applicable:
  ```javascript
  // Example code
  ```

  {{#if todolist}}
  ## Implemented Features
  Based on analysis of the codebase:
  - [x] Feature 1 (detected from existing code/tests)
  - [x] Feature 2
  - [x] Feature 3

  ## TODO / Roadmap
  Suggested improvements and pending features:
  - [ ] Feature 4 (based on TODO comments in code)
  - [ ] Feature 5
  - [ ] Feature 6
  {{/if}}

  {{#unless simple}}
  ## API Documentation
  If applicable, document key functions, classes, or endpoints:

  ### Function/Endpoint Name
  **Description:** Brief description
  **Parameters:**
  - `param1` (type): Description
  - `param2` (type): Description

  **Returns:** Description of return value

  **Example:**
  ```javascript
  // Usage example
  ```

  ## Contributing
  We welcome contributions! Please follow these steps:
  1. Fork the repository
  2. Create a feature branch (`git checkout -b feature/amazing-feature`)
  3. Commit your changes (`git commit -m 'Add amazing feature'`)
  4. Push to the branch (`git push origin feature/amazing-feature`)
  5. Open a Pull Request

  Please read [CONTRIBUTING.md](CONTRIBUTING.md) for detailed guidelines.

  ## License
  This project is licensed under the [MIT License](LICENSE) - see the LICENSE file for details.

  ## Acknowledgments
  - Thanks to [Name](link) for [contribution]
  - Inspired by [project/resource]
  - Special thanks to [person/team]
  {{/unless}}
  ```
  {{/unless}}

  {{#unless english_only}}
  ### File: README_ES.md
  Generate the Spanish version with the same structure:

  ```markdown
  # Título del Proyecto

  {{#unless no_github}}
  [📖 Read in English](./README.md)

  <!-- Sección de Badges -->
  ![Licencia](https://img.shields.io/badge/licencia-MIT-blue.svg)
  ![Versión](https://img.shields.io/badge/versión-1.0.0-green.svg)
  <!-- Añadir badges relevantes según el tipo de proyecto -->
  {{/unless}}

  ## Descripción
  Descripción breve y convincente de qué hace este proyecto y por qué existe.

  ## Tabla de Contenidos
  - [Descripción](#descripción)
  - [Instalación](#instalación)
  - [Uso](#uso)
  {{#if todolist}}- [Funcionalidades Implementadas](#funcionalidades-implementadas)
  - [TODO / Roadmap](#todo--roadmap){{/if}}
  - [Documentación API](#documentación-api)
  - [Contribuir](#contribuir)
  - [Licencia](#licencia)
  - [Agradecimientos](#agradecimientos)

  ## Instalación
  Instrucciones de instalación paso a paso:
  ```bash
  # Clonar el repositorio
git clone <repo-url>

  # Navegar al directorio
cd project-name

  # Instalar dependencias
<install-command>
```

  ## Uso
  Ejemplos claros de uso:
  ```bash
  # Uso básico
<command>

  # Ejemplo de salida
  ```

  Incluir ejemplos de código si aplica:
  ```javascript
  // Ejemplo de código
  ```

  {{#if todolist}}
  ## Funcionalidades Implementadas
  Basado en el análisis del código:
  - [x] Funcionalidad 1 (detectada del código/tests existentes)
  - [x] Funcionalidad 2
  - [x] Funcionalidad 3

  ## TODO / Roadmap
  Mejoras sugeridas y funcionalidades pendientes:
  - [ ] Funcionalidad 4 (basada en comentarios TODO del código)
  - [ ] Funcionalidad 5
  - [ ] Funcionalidad 6
  {{/if}}

  {{#unless simple}}
  ## Documentación API
  Si aplica, documentar funciones, clases o endpoints clave:

  ### Nombre de la Función/Endpoint
  **Descripción:** Breve descripción
  **Parámetros:**
  - `param1` (tipo): Descripción
  - `param2` (tipo): Descripción

  **Retorna:** Descripción del valor de retorno

  **Ejemplo:**
  ```javascript
  // Ejemplo de uso
  ```

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
  - Gracias a [Nombre](link) por [contribución]
  - Inspirado en [proyecto/recurso]
  - Agradecimientos especiales a [persona/equipo]
  {{/unless}}
  ```
  {{/unless}}

  ## Instructions

  1. **Analyze the project:** Use the available tools to explore the current directory structure, identify the project type, main files, and technology stack.

  2. **Parse arguments:** Check `$ARGUMENTS` for any flags (`--no-github`, `--english-only`, `--spanish-only`, `--simple`, `--todolist`)

  3. **Generate content:** Based on the project analysis and arguments, generate appropriate README content that is:
     - Accurate (reflects actual project structure)
     - Comprehensive (covers all relevant aspects)
     - Well-formatted (proper Markdown)
     - Professional (GitHub-ready)

  4. **Create/update files:**
     - If `--english-only`: Only create/update README.md
     - If `--spanish-only`: Only create/update README_ES.md
     - Otherwise: Create/update both files

  5. **Include bidirectional links:**
     - In README.md: Add `[📖 Leer en Español](./README_ES.md)` near the top
     - In README_ES.md: Add `[📖 Read in English](./README.md)` near the top

  6. **If `--todolist` is specified:**
     - Scan the codebase for TODO/FIXME comments
     - Analyze existing functionality (tests, exports, implementations)
     - Create realistic "Implemented" and "TODO" sections

  7. **Output:** Report what files were created/updated and provide a summary of the README structure.
---

Analyze the project structure and create/update the README files accordingly.

Current directory: !pwd

Project files: !ls -la

{{if $ARGUMENTS}}
Arguments provided: $ARGUMENTS
{{else}}
No arguments provided - using default mode (full GitHub bilingual)
{{endif}}

Please generate the README files based on the project analysis and any provided arguments.
