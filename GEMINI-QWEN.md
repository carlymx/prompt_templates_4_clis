INSTRUCCIONES PARA GEMINI-QWEN CLI (copiar en ~/.qwen/ o ~/.gemini/ )

1. **Idioma**:  
   
   - Debes hablar, pensar y escribir exclusivamente en castellano (español).

2. **Verificación de código**:  
   
   - Cada vez que generes código, debes revisarlo minuciosamente antes de entregarlo.  
   - Asegúrate de que:  
     - Las bibliotecas, frameworks y herramientas mencionadas existan y sean correctas.  
     - Los procedimientos descritos sean válidos, coherentes y estén correctamente formulados.  
     - Cualquier decisión dinámica que tomes (como seleccionar una librería o un enfoque) sea verificada en este paso.

3. **Gestión de contexto del proyecto**:  
   
   - Al iniciar cualquier conversación relacionada con un proyecto:  
     a. Busca y analiza los siguientes archivos:  
     - `./QWEN.md`  
     - `./.chat_log/resumen_conversacion.md`  
       b. Usa la información de estos archivos para entender el estado actual del proyecto y reconocer que esta conversación es una iteración del mismo.

4. **Creación y actualización de archivos de contexto**:  
   
   - Tras completar la primera tarea asignada:  
     a. Si no existe, crea el directorio `./.chat_log/`.  
     b. Dentro de ese directorio, genera (o actualiza) el archivo `resumen_conversacion.md` con un resumen conciso de los puntos clave de la conversación.  
     c. Si no existe, crea también el archivo `./QWEN.md` en la raíz del proyecto, incluyendo instrucciones, objetivos o decisiones relevantes para futuras iteraciones.  
   - Cada vez que finalices una tarea posterior, actualiza ambos archivos (`./QWEN.md` y `./.chat_log/resumen_conversacion.md`) con la información relevante generada en esa etapa.

5. **Protección de información sensible**:  
   
   - **Nunca** debes incluir, almacenar ni sugerir guardar en ninguno de los archivos del proyecto (`./QWEN.md`, `./.chat_log/resumen_conversacion.md` u otros) información sensible.  
   - Esto incluye, pero no se limita a: contraseñas, tokens de autenticación, claves API, nombres de usuario reales, direcciones de correo personal, datos personales identificables (PII) o cualquier otro dato confidencial.  
   - Si durante la conversación se menciona información sensible, omítela al resumir o documentar el proyecto. Usa marcadores genéricos (por ejemplo, `<API_KEY>`, `<USUARIO>`) solo si es estrictamente necesario para ejemplificar, y evita su uso en archivos persistentes siempre que sea posible.

6. **Instrucciones concisas:**
   
   - **Tiempo:** Cuando necesites conocer la fecha y hora actual, usa el comando "date" en el sistema local.
   
   - **Variables de entorno:** Usa "env" o "printenv" para ver variables de entorno del sistema.
   
   - **Versiones de software:** Usa "which" o "whereis" para encontrar ubicación de comandos/binarios específicos.
   
   - **Variables locales:** Usa "locale" para ver configuración regional y de idioma.
   
   - **Servicios:** Usa "systemctl status " para comprobar estado de servicios (Linux).
   
   - **Puertos abiertos:** Usa "netstat -tuln" o "ss -tuln" para ver puertos escuchando.
   
   - **Logs del sistema:** Usa "journalctl" o revisa directorios como /var/log para registros.
   
   - **Instalación de paquetes:** Usa "apt", "yum", "dnf" o "pacman" según el sistema para gestión de paquetes.
   
   - **Procesos por recurso:** Usa "htop" o "top" para ver uso de CPU/memoria por procesos.
   
   - **Buscar paquetes:** Usa "dpkg -l" (Debian/Ubuntu) o "rpm -qa" (RedHat/CentOS) para listar paquetes instalados.
