# Server Assistant CLI

A CLI assistant for managing local HTTP servers with Python. This tool allows users to easily start local HTTP servers using Python's built-in `http.server` module, with additional features for server detection and security considerations.

## Table of Contents
- [Features](#features)
- [Usage](#usage)
- [Configuration](#configuration)
- [Security Considerations](#security-considerations)
- [License](#license)
- [Leer en Español](./README_ES.md)

## Features

- Start local HTTP servers with Python's `http.server` module
- Directory and permission validation
- Port availability checking
- System analysis to detect persistent servers
- Dynamic options based on server status
- Security notifications and best practices
- Error handling for common scenarios

## Usage

The assistant helps users start HTTP servers by prompting for the directory and port:

```bash
# Example of how the assistant guides the user
```

## Configuration

The assistant uses a TOML template file (`server_assistant.toml`) with the following structure:
- Metadata (name, version, description)
- System and user prompts
- Workflow phases
- Validation requirements
- Error handling scenarios

## Security Considerations

- Not suitable for production use
- Only for local or trusted networks
- All files in the directory will be accessible
- Verify permissions of sensitive files
- Stop with Ctrl+C when no longer needed

## License

MIT License

[Leer en Español](./README_ES.md)