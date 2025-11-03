[ESPAÑOL](README_ES.md) | [ENGLISH](README.md)

# Angular Project Generator

An interactive configuration tool for creating customized Angular projects with various options for styling, language, database, platform support, and more.

## Features

- **Interactive Setup**: Answer a series of questions to configure your project
- **Styling Options**: Choose between CSS or SCSS for styling
- **Language Choice**: Select JavaScript or TypeScript for development
- **Ionic Integration**: Optional integration with Ionic for mobile components
- **Database Configuration**: Support for MongoDB, MariaDB, or local JSON storage
- **Multi-Platform Support**: Build for Web, Android, iOS, or all platforms using Capacitor
- **Project Templates**: Start with blank, minimal, basic examples, or custom templates

## Usage

The tool guides you through creating a new Angular project by asking a series of questions about your preferences and requirements. Based on your responses, it generates a detailed action plan before executing the necessary commands to create your project.

## Options

### Project Name

Specify the name of your project which will be used for the root folder.

### Styling

Choose between:

- **CSS**: Standard Cascading Style Sheets
- **SCSS**: SASS CSS extension with additional functionality

### Programming Language

Choose between:

- **TypeScript**: Recommended for modern Angular projects with type safety
- **JavaScript**: Traditional scripting language

### Ionic Integration

Optional integration with Ionic framework for:

- UI components for mobile and desktop applications
- Enhanced mobile development capabilities

### Database Configuration

Select your preferred database solution:

- **MongoDB**: NoSQL database for flexible data storage
- **MariaDB**: Relational database for structured data
- **Local JSON**: Simple file-based storage for basic projects

### Project Type

Choose from several project templates:

- **Blank**: Base project structure without components
- **Minimal**: Basic structure with a minimal starting component
- **Basic with Examples**: Project with example components demonstrating Angular features
- **Basic with Ionic Page**: Ionic UI components example (when Ionic is selected)
- **Custom**: Provide specific requirements or attach a requirements file

### Target Devices

Select your target platforms:

- **Web / Web App**
- **Android** (using Capacitor)
- **iOS** (using Capacitor)
- **All** (Web, Android, and iOS)
- **No specific target**

## Requirements

- Node.js
- Angular CLI
- (Optional) Ionic CLI for Ionic projects
- (Optional) Capacitor for mobile platforms

## Security

This project follows security best practices:

- No sensitive information stored in code
- Use environment variables for sensitive configurations
- Follow Angular security guidelines

## Development Guidelines

- Follow Angular style guide
- Use TypeScript by default for type safety
- Modular component architecture
- Comprehensive testing
- Proper documentation