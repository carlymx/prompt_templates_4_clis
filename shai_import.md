
🇬🇧 Adaptation of Prompts from Gemini CLI to Shai CLI

That is an excellent question that addresses the issue of interoperability between AI CLI tools.

Although there is no direct "import" function or a specific command that automatically converts a TOML prompt template file from Gemini CLI to the internal format or commands of shai CLI, you can generally adapt and use the core content.

💡 The Key: Reusing the Prompt Text

The key is that the Gemini CLI's .toml file essentially contains a structured prompt text (along with metadata such as the description).

1. Gemini CLI Format (.toml)

Slash commands (/command) in Gemini CLI are defined in TOML files (e.g., ~/.gemini/commands/my_command.toml) with a simple structure:
Ini, TOML

description = "Description of what the prompt does"
prompt = """
Your detailed prompt goes here.
You can use argument injections like {{args}} 
and shell commands like !{git diff --staged}
"""

The crucial element is the value of the prompt key.

2. Usage in Shai CLI

Shai CLI focuses on executing shell commands from natural language.
Scenario	Recommended Action
Direct Use as Input Prompt	Simply copy the prompt text (the content between the triple quotes """) and use it as your direct input prompt in shai.
Define a System Context	If the prompt is a long-term "behavior" instruction (e.g., "You are a Rust expert"), you can copy the prompt content to shai's system context file (such as SHAI.md, depending on the implementation).
Create a Shell Function or Alias	If you want to invoke it with a short name, similar to Gemini CLI, you can create a shell alias or function that calls shai with your saved prompt text.

Conclusion

Yes, you can use the content. Not through a direct TOML format import, but by reusing the prompt template text and feeding it to shai as a standard prompt or as part of its system context configuration.

--
--

🇪🇸 Adaptación de Prompts de Gemini CLI a Shai CLI

Es una excelente pregunta que toca el tema de la interoperabilidad entre herramientas CLI de IA.

Aunque no existe una función de "importación" directa o un comando específico que convierta automáticamente un archivo TOML de un prompt template del Gemini CLI al formato interno o de comandos del shai CLI, generalmente puedes adaptar y usar el contenido principal.

💡 La Clave: Reutilizar el Texto del Prompt

La clave está en que el archivo .toml del Gemini CLI contiene esencialmente un texto de prompt estructurado (junto con metadatos como la descripción).

1. Formato de Gemini CLI (.toml)

Los comandos slash (/comando) en Gemini CLI se definen en archivos TOML (ej. ~/.gemini/commands/mi_comando.toml) con una estructura simple:
Ini, TOML

description = "Descripción de lo que hace el prompt"
prompt = """
Tu prompt detallado va aquí.
Puedes usar inyecciones de argumentos como {{args}} 
y comandos de shell como !{git diff --staged}
"""

El elemento crucial es el valor de la clave prompt.

2. Uso en Shai CLI

Shai CLI se enfoca en la ejecución de comandos de shell a partir de lenguaje natural.
Escenario	Acción Recomendada
Uso directo como Prompt de Entrada	Simplemente copia el texto del prompt (el contenido entre las triples comillas """) y úsalo como tu prompt de entrada directa en shai.
Definir un Contexto del Sistema	Si el prompt es una instrucción de "comportamiento" (ej. "Eres un experto en Rust"), puedes copiar el contenido del prompt al archivo de contexto del sistema de shai (como SHAI.md, dependiendo de la implementación).
Crear una Función o Alias de Shell	Si quieres invocarlo con un nombre corto, puedes crear un alias o una función de shell que llame a shai con tu texto de prompt guardado.

Conclusión

Sí, puedes usar el contenido. No a través de una importación de formato TOML directo, sino reutilizando el texto de la plantilla de prompt y alimentándolo a shai como un prompt estándar o como parte de su configuración de contexto del sistema.
