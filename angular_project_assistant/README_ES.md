[ESPAÑOL](README_ES.md) | [ENGLISH](README.md)

# Generador de Proyectos Angular

Una herramienta de configuración interactiva para crear proyectos Angular personalizados con varias opciones para estilos, lenguaje, base de datos, soporte multiplataforma y más.

## Características

- **Configuración Interactiva**: Responde una serie de preguntas para configurar tu proyecto
- **Opciones de Estilo**: Elige entre CSS o SCSS para estilizado
- **Elección de Lenguaje**: Selecciona JavaScript o TypeScript para el desarrollo
- **Integración con Ionic**: Integración opcional con Ionic para componentes móviles
- **Configuración de Base de Datos**: Soporte para MongoDB, MariaDB o almacenamiento local en JSON
- **Soporte Multiplataforma**: Construye para Web, Android, iOS o todas las plataformas usando Capacitor
- **Plantillas de Proyecto**: Comienza con plantillas en blanco, mínimas, con ejemplos básicos o personalizadas

## Uso

La herramienta te guía a través de la creación de un nuevo proyecto Angular haciendo una serie de preguntas sobre tus preferencias y requisitos. Basado en tus respuestas, genera un plan de acción detallado antes de ejecutar los comandos necesarios para crear tu proyecto.

## Opciones

### Nombre del Proyecto

Especifica el nombre de tu proyecto que se usará para la carpeta raíz.

### Estilo

Elige entre:

- **CSS**: Hojas de estilo en cascada estándar
- **SCSS**: Extensión SASS CSS con funcionalidades adicionales

### Lenguaje de Programación

Elige entre:

- **TypeScript**: Recomendado para proyectos Angular modernos con seguridad de tipos
- **JavaScript**: Lenguaje de scripting tradicional

### Integración con Ionic

Integración opcional con el framework Ionic para:

- Componentes de interfaz de usuario para aplicaciones móviles y de escritorio
- Capacidades mejoradas de desarrollo móvil

### Configuración de Base de Datos

Selecciona tu solución de base de datos preferida:

- **MongoDB**: Base de datos NoSQL para almacenamiento de datos flexible
- **MariaDB**: Base de datos relacional para datos estructurados
- **JSON Local**: Almacenamiento simple basado en archivos para proyectos básicos

### Tipo de Proyecto

Elige entre varias plantillas de proyecto:

- **En Blanco**: Estructura de proyecto base sin componentes
- **Mínimo**: Estructura básica con un componente inicial mínimo
- **Básico con Ejemplos**: Proyecto con componentes de ejemplo que demuestran características de Angular
- **Básico con Página de Ionic**: Ejemplo de componentes de interfaz de Ionic (cuando se selecciona Ionic)
- **Personalizado**: Proporciona requisitos específicos o adjunta un archivo de requisitos

### Dispositivos de Destino

Selecciona tus plataformas objetivo:

- **Web / Aplicación Web**
- **Android** (usando Capacitor)
- **iOS** (usando Capacitor)
- **Todas** (Web, Android e iOS)
- **Ningún objetivo específico**

## Requisitos

- Node.js
- Angular CLI
- (Opcional) Ionic CLI para proyectos con Ionic
- (Opcional) Capacitor para plataformas móviles

## Seguridad

Este proyecto sigue las mejores prácticas de seguridad:

- Sin información sensible almacenada en el código
- Uso de variables de entorno para configuraciones sensibles
- Sigue las directrices de seguridad de Angular

## Directrices de Desarrollo

- Sigue la guía de estilo de Angular
- Usa TypeScript por defecto para seguridad de tipos
- Arquitectura modular de componentes
- Pruebas comprehensivas
- Documentación adecuada