# README Generator Tool

[📖 Leer en Español](./README_ES.md)

<!-- Badges Section -->
![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Version](https://img.shields.io/badge/version-1.0.0-green.svg)
![Type](https://img.shields.io/badge/type-skill-orange.svg)

## Description

An intelligent tool that automatically creates or updates comprehensive bilingual README.md and README_ES.md files with GitHub best practices. This skill analyzes your project structure, detects the technology stack, and generates professional documentation tailored to your specific project type.

## Table of Contents

- [Description](#description)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Command Flags](#command-flags)
- [Project Detection](#project-detection)
- [Generated Structure](#generated-structure)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgments](#acknowledgments)

## Features

- **Automatic Project Analysis**: Detects programming language, framework, and technology stack
- **Bilingual Support**: Generates both English (README.md) and Spanish (README_ES.md) versions
- **GitHub-Ready**: Includes badges, shields, and professional formatting
- **Customizable Output**: Multiple flags to control content generation
- **Smart Content**: Adapts documentation based on detected project type
- **Cross-References**: Bidirectional links between language versions

## Installation

```bash
# Clone the repository
git clone <repo-url>

# Navigate to directory
cd readme-generator

# The tool is ready to use - no additional dependencies required
```

## Usage

### Basic Usage

Run the tool in your project directory:

```bash
# Generate full bilingual README files with GitHub elements
<command>
```

### Advanced Usage with Flags

```bash
# Exclude GitHub-specific elements (badges, shields)
<command> --no-github

# Create only English README
<command> --english-only

# Create only Spanish README
<command> --spanish-only

# Create minimal version (Title, Description, Installation, Usage only)
<command> --simple

# Include TODO/Roadmap sections based on code analysis
<command> --todolist
```

### Combining Flags

```bash
# Minimal English-only version without GitHub elements
<command> --simple --english-only --no-github

# Full Spanish version with TODO analysis
<command> --todolist --spanish-only
```

## Command Flags

| Flag | Description |
|------|-------------|
| `--no-github` | Exclude GitHub-specific elements (badges, shields) |
| `--english-only` | Create only README.md (skip README_ES.md) |
| `--spanish-only` | Create only README_ES.md (skip README.md) |
| `--simple` | Create minimal version with basic sections only |
| `--todolist` | Include "Implemented" and "TODO/Roadmap" sections |

## Project Detection

The tool automatically detects:

- **Programming Languages**: JavaScript, Python, Java, Go, Rust, Ruby, etc.
- **Frameworks**: React, Vue, Angular, Express, Django, Flask, etc.
- **Build Systems**: npm, yarn, pip, Maven, Gradle, Cargo, etc.
- **Testing Setup**: Jest, Mocha, pytest, JUnit, etc.
- **Configuration Files**: package.json, Cargo.toml, requirements.txt, etc.

## Generated Structure

### Full Version (default)

Both README files include:

1. **Title** with language switcher link
2. **Badges** (license, version, tech-specific)
3. **Description** - Project overview
4. **Table of Contents** - Navigation links
5. **Installation** - Step-by-step setup instructions
6. **Usage** - Clear examples and code snippets
7. **API Documentation** - Function/endpoint documentation
8. **Contributing** - Contribution guidelines
9. **License** - License information
10. **Acknowledgments** - Credits and thanks

### Simple Version (--simple flag)

Minimal structure with:

1. Title
2. Description
3. Installation
4. Usage

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

- Inspired by the need for consistent, professional documentation across projects
- Thanks to the open-source community for best practices inspiration
- Special thanks to contributors who improve this tool
