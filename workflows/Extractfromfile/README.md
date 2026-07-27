Workflows de Extract From File

Objetivo

Esta carpeta agrupa un conjunto amplio de workflows de n8n que utilizan el nodo Extract From File para obtener el contenido de archivos (documentos, hojas de calculo, PDFs o imagenes) recibidos por distintos canales. El objetivo es automatizar la lectura y el procesamiento de archivos adjuntos provenientes de WhatsApp, Gmail, formularios, Google Drive o solicitudes HTTP, evitando la extraccion manual de su contenido.

Estructura

Cada workflow combina un disparador especifico con el nodo Extract From File para obtener el contenido del archivo recibido. Algunos workflows reciben el archivo por WhatsApp o Gmail y responden automaticamente tras procesarlo; otros usan un n8n Form Trigger para que el usuario suba un archivo, cuyo contenido se extrae y se guarda en Google Sheets o Google Drive; otros descargan el archivo mediante HTTP Request y lo procesan hacia una base de datos vectorial como Supabase para busquedas semanticas; y otro grupo utiliza un Google Drive Trigger para extraer el contenido de un archivo, convertirlo a otro formato con Convert To File y guardarlo nuevamente en Drive, en ocasiones con apoyo de un modelo de IA. La mayoria incluye nodos Sticky Note explicativos y un nodo Error Handler (Stop And Error) para el manejo de fallos.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow deseado en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales del canal de origen del archivo (WhatsApp, Gmail, Google Drive o el formulario de n8n). Paso 3: Configurar las credenciales del destino de los datos extraidos (Google Sheets, Google Drive, Supabase u otro servicio segun el workflow). Paso 4: Ajustar el tipo de archivo y las opciones de extraccion en el nodo Extract From File segun el formato esperado. Paso 5: Activar o probar el workflow enviando un archivo de ejemplo y verificar en el historial de ejecuciones de n8n que el contenido se extrae y procesa correctamente.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0601_Extractfromfile_Manual_Create_Webhook.json | WhatsApp File Extraction Bot | Recibe un archivo por WhatsApp, extrae su contenido y responde al usuario.
0646_Extractfromfile_Form_Export_Webhook.json | Form File Upload Extraction | Extrae el contenido de un archivo subido mediante un formulario de n8n.
0694_Extractfromfile_Manual_Automation_Webhook.json | File Extraction Automation | Extrae el contenido de un archivo como parte de un flujo de automatizacion.
0741_Extractfromfile_Stickynote_Automation_Triggered.json | File Extraction Tool for AI Agent | Expone la extraccion de contenido de archivos como herramienta para un agente de IA.
0828_Extractfromfile_Gmail_Send_Triggered.json | Gmail Attachment Extraction and Reply | Extrae el contenido de un adjunto de Gmail y responde automaticamente segun el resultado.
1246_Extractfromfile_HTTP_Automation_Webhook.json | File Ingestion to Supabase Vector Store | Descarga un archivo por HTTP, extrae su contenido y lo indexa en Supabase para busquedas semanticas.
1254_Extractfromfile_Form_Automate_Triggered.json | Form File Upload to Sheets and Drive | Extrae el contenido de un archivo subido por formulario y lo guarda en Google Sheets y Google Drive.
1364_Extractfromfile_Manual_Create_Webhook.json | File Extraction Automation (variante) | Variante del flujo de extraccion de contenido de archivos.
1365_Extractfromfile_Manual_Create_Webhook.json | File Extraction Automation (variante) | Otra variante del flujo de extraccion de contenido de archivos.
1438_Extractfromfile_Manual_Process_Webhook.json | File Extraction and Processing | Extrae el contenido de un archivo y lo procesa segun el flujo configurado.
1444_Extractfromfile_Converttofile_Automation_Webhook.json | Google Drive File Format Converter | Extrae el contenido de un archivo de Google Drive, lo convierte a otro formato con IA y lo guarda de nuevo en Drive.
1472_Extractfromfile_Converttofile_Create_Triggered.json | Google Drive File Format Converter (variante) | Variante del flujo de conversion de formato de archivos de Google Drive.
1488_Extractfromfile_Form_Automation_Triggered.json | Form File Upload Extraction (variante) | Variante del flujo de extraccion de archivos subidos por formulario.
1493_Extractfromfile_Form_Automation_Webhook.json | Form File Upload Extraction (variante) | Otra variante del flujo de extraccion de archivos subidos por formulario.
1501_Extractfromfile_Form_Automate_Triggered.json | Form File Upload to Sheets and Drive (variante) | Variante del flujo de extraccion de archivos de formulario hacia Sheets y Drive.
1590_Extractfromfile_Converttofile_Create_Triggered.json | Google Drive File Format Converter (variante) | Otra variante del flujo de conversion de formato de archivos de Google Drive.
1641_Extractfromfile_Manual_Automation_Webhook.json | File Extraction Automation (variante) | Variante adicional del flujo de extraccion de contenido de archivos.
1764_Extractfromfile_HTTP_Automation_Webhook.json | File Ingestion to Supabase Vector Store (variante) | Variante del flujo de ingestion de archivos hacia Supabase.
1847_Extractfromfile_Form_Automation_Triggered.json | Form File Upload Extraction (variante) | Otra variante del flujo de extraccion de archivos de formulario.
1978_Extractfromfile_Converttofile_Automation_Webhook.json | Google Drive File Format Converter (variante) | Otra variante del flujo de conversion de formato de archivos de Google Drive.
1981_Extractfromfile_Form_Automate_Triggered.json | Form File Upload to Sheets and Drive (variante) | Otra variante del flujo de extraccion de archivos de formulario hacia Sheets y Drive.
