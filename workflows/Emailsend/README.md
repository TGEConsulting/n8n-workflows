Workflows de Email Send

Objetivo

Esta carpeta agrupa los workflows de n8n que utilizan el nodo Email Send (SMTP) para notificar por correo el resultado de distintos procesos automatizados. El objetivo es avisar cuando se agrega un nuevo archivo a Google Drive y enviar reportes por correo tras sincronizar datos con HubSpot, evitando la revision manual de estos eventos.

Estructura

El primer workflow parte de un Google Drive Trigger que detecta la creacion de un nuevo archivo y utiliza el nodo Email Send para notificar por correo mediante una cuenta SMTP. El segundo workflow, disparado manualmente o de forma programada, obtiene datos mediante HTTP Request, los transforma con nodos Code, genera un archivo de hoja de calculo (Spreadsheet File), sincroniza la informacion con HubSpot y finalmente envia un correo de reporte con el resultado del proceso mediante Email Send.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow deseado en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales SMTP en el nodo Email Send, indicando los destinatarios del correo. Paso 3: Para el primer workflow, configurar ademas las credenciales de Google Drive y la carpeta a monitorear. Paso 4: Para el segundo workflow, configurar las credenciales de HubSpot y ajustar el codigo de los nodos Code segun el formato de los datos de origen. Paso 5: Activar o ejecutar el workflow y verificar en el historial de ejecuciones de n8n que los correos se envian correctamente con la informacion esperada.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0113_Emailsend_GoogleDrive_Send_Triggered.json | Google Drive New File Email Notification | Envia un correo de notificacion cuando se agrega un nuevo archivo a Google Drive.
1628_Emailsend_Code_Automation_Webhook.json | Data Sync Report to HubSpot and Email | Obtiene datos, los procesa, los sincroniza con HubSpot y envia un correo con el reporte del resultado.
