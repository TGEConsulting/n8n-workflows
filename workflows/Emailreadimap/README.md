Workflows de Email Read (IMAP)

Objetivo

Esta carpeta agrupa los workflows de n8n que utilizan el nodo Email Read (IMAP) para leer correos electronicos entrantes y procesarlos de distintas formas: guardar adjuntos en Nextcloud, archivar el contenido en Google Drive, o responder automaticamente convirtiendo el cuerpo del mensaje a partir de Markdown. El objetivo es evitar la revision y el procesamiento manual de los correos recibidos en una bandeja de entrada.

Estructura

El primer workflow lee los correos por IMAP y guarda sus adjuntos directamente en Nextcloud mediante un nodo Function de apoyo. Un workflow basico se limita a leer los correos por IMAP como plantilla de partida sin procesamiento adicional. Un grupo de workflows (variante de archivado) lee los correos, convierte su contenido con el nodo Markdown, descarga recursos adicionales mediante HTTP Request y los guarda en Google Drive, enviando ademas una notificacion por correo o Gmail. Otro grupo de workflows (variante de respuesta automatica) lee los correos, convierte el contenido a Markdown, evalua una condicion con un nodo If y envia una respuesta automatica por correo o Gmail segun el resultado.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow deseado en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de la cuenta de correo IMAP de origen en el nodo Email Read (IMAP). Paso 3: Segun el workflow, configurar las credenciales de Nextcloud, Google Drive o Gmail para el destino del contenido procesado. Paso 4: Ajustar las condiciones del nodo If en los workflows de respuesta automatica segun el criterio deseado. Paso 5: Ejecutar el workflow y verificar en el historial de ejecuciones de n8n que los correos se leen y procesan correctamente.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0134_Emailreadimap_Nextcloud_Send.json | Email Attachments to Nextcloud | Lee correos por IMAP y guarda sus archivos adjuntos en Nextcloud.
1050_Emailreadimap_Send.json | Basic IMAP Email Reader | Plantilla basica que lee correos entrantes por IMAP como punto de partida.
1277_Emailreadimap_Manual_Send_Webhook.json | Email Content to Google Drive Archive | Lee correos, convierte su contenido con Markdown, descarga recursos y los archiva en Google Drive.
1284_Emailreadimap_Markdown_Send.json | Email Auto-Reply with Markdown | Lee correos, convierte el contenido con Markdown y envia una respuesta condicional por correo o Gmail.
1427_Emailreadimap_Manual_Send_Webhook.json | Email Content to Google Drive Archive (variante) | Variante del flujo de archivado de correos en Google Drive con notificacion por Gmail.
1588_Emailreadimap_Markdown_Send.json | Email Auto-Reply with Markdown (variante) | Variante del flujo de respuesta automatica de correos basada en Markdown.
1936_Emailreadimap_Manual_Send_Webhook.json | Email Content to Google Drive Archive (variante) | Otra variante del flujo de archivado de correos en Google Drive.
1962_Emailreadimap_Manual_Send_Webhook.json | Email Content to Google Drive Archive (variante) | Otra variante del flujo de archivado de correos en Google Drive.
