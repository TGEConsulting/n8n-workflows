Workflows de Execute Command

Objetivo

Esta carpeta agrupa los workflows de n8n que utilizan el nodo Execute Command para ejecutar comandos del sistema operativo donde corre n8n como parte de tareas de automatizacion local: monitoreo de servidor con notificacion por correo, procesamiento de archivos locales nuevos y lectura o conversion de archivos binarios. El objetivo es automatizar tareas de sistema que normalmente requeririan ejecutar comandos manualmente en la maquina donde se aloja n8n.

Estructura

El primer workflow recibe una solicitud por Webhook, ejecuta comandos del sistema para obtener informacion (por ejemplo del estado del servidor), evalua el resultado con un nodo If y envia una notificacion por Mailgun. El segundo workflow, disparado manualmente, ejecuta un comando, evalua su salida con un nodo If y la procesa con un Function Item. Dos workflows identicos utilizan un Local File Trigger para detectar nuevos archivos en una carpeta local, ejecutan comandos del sistema para procesarlos y organizan el resultado con nodos Set y Split Out. El ultimo workflow lee un archivo binario, mueve sus datos, ejecuta un comando sobre el y evalua el resultado con un nodo If. Todos incluyen un nodo Error Handler (Stop And Error) para el manejo de fallos.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow deseado en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Revisar cuidadosamente el comando configurado en cada nodo Execute Command, ya que se ejecuta directamente en el sistema operativo donde corre la instancia de n8n. Paso 3: Configurar las credenciales de Mailgun si el workflow lo requiere, y ajustar la ruta de la carpeta local a monitorear en los workflows con Local File Trigger. Paso 4: Ejecutar o activar el workflow segun su disparador. Paso 5: Verificar en el historial de ejecuciones de n8n que el comando se ejecuta correctamente y que el resultado se procesa como se espera.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0097_Executecommand_Mailgun_Automation_Webhook.json | Server Command Check with Mailgun Alert | Ejecuta comandos del sistema a partir de una solicitud Webhook y notifica el resultado por Mailgun.
0190_Executecommand_Functionitem_Automate.json | Execute Command Output Processor | Ejecuta un comando del sistema y procesa su salida con un Function Item.
0534_Executecommand_Localfile_Process_Triggered.json | Local File Processing with System Commands | Detecta nuevos archivos locales y ejecuta comandos del sistema para procesarlos.
1190_Executecommand_Readbinaryfile_Automate_Triggered.json | Binary File Processing with System Commands | Lee un archivo binario y ejecuta un comando del sistema para procesarlo.
1587_Executecommand_Localfile_Automation_Triggered.json | Local File Processing with System Commands (variante) | Variante del flujo de procesamiento de archivos locales con comandos del sistema.
