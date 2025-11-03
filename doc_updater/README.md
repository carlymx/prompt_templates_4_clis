[ESPAÑOL](README_ES.md) | [ENGLISH](README.md)

# Qwen CLI Projects Documentation

This directory contains several Qwen CLI assistants that facilitate different development and configuration tasks.

## Available Assistants

- **angular_project_assistant**: Tool for creating Angular projects with interactive and customizable configuration
- **prompt_assistant**: Template for creating other high-quality prompt templates
- **samba_assistant**: Assistant for configuring Samba on Linux systems
- **server_assistant**: Assistant for launching local HTTP servers with Python
- **doc_update**: Assistant for creating and updating documentation files (new)

## Common Characteristics

All assistants follow a consistent structure:

- `.toml` file with the assistant template
- Documentation in Spanish and English
- Instructions for future iterations in `QWEN.md`
- Conversation logs in `.chat_log/resumen_conversacion.md`

## Usage

Each assistant can be used by executing its name as a command in Qwen CLI after copying its `.toml` file to the `~/.qwen/commands/` directory.

## New Assistant: doc_update

The `doc_update` is a newly created assistant that facilitates the creation and updating of documentation files for CLI projects, including:

- README.md
- README_ES.md
- QWEN.md
- .chat_log/resumen_conversacion.md

Includes bidirectional links between READMEs and processes chat log information.