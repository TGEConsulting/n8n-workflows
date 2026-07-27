Workflows de Form

Objetivo

Esta carpeta agrupa un conjunto amplio de workflows de n8n que utilizan el n8n Form Trigger para recibir datos directamente desde un formulario y procesarlos hacia distintos destinos. El objetivo es automatizar el registro de respuestas de formularios en hojas de calculo, tareas, notificaciones y otros sistemas, evitando la carga manual de la informacion recibida.

Estructura

Cada workflow parte de un Form Trigger que recibe los datos ingresados por el usuario. Segun el workflow, la informacion se registra en Google Sheets, se crea una tarea en Asana con notificacion por WhatsApp, se sube un archivo a S3, se extrae contenido de un archivo adjunto, se convierte a HTML o Markdown, se agregan los resultados con Aggregate, se envia una solicitud HTTP a un servicio externo, o se actualiza un video de YouTube. La mayoria incluye nodos Sticky Note explicativos y un nodo Error Handler (Stop And Error) para el manejo de fallos.

Metodo de aplicacion

Paso 1: Localizar el archivo JSON del workflow especifico segun su nombre y la descripcion de la tabla siguiente. Paso 2: Importarlo en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 3: Configurar las credenciales de las aplicaciones externas que utilice el workflow. Paso 4: Personalizar los campos del formulario segun la informacion que se desea recolectar. Paso 5: Activar el workflow, enviar una respuesta de prueba a traves del formulario y verificar en el historial de ejecuciones de n8n que los datos se procesan correctamente en el destino configurado.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0484_Form_Stickynote_Automation_Webhook.json | Form Submission Automation | Procesa las respuestas de un formulario como parte de un flujo de automatizacion.
0633_Form_GoogleSheets_Create_Triggered.json | Multi-step Form Registration to Google Sheets | Registra en Google Sheets las respuestas de un formulario de varios pasos, generando un identificador unico con Crypto.
0648_Form_GoogleSheets_Create_Triggered.json | Multi-step Form Registration to Google Sheets (variante) | Variante del flujo de registro de formularios de varios pasos en Google Sheets.
0732_Form_Youtube_Update_Triggered.json | Form to YouTube Video Update | Actualiza los datos de un video de YouTube a partir de una respuesta de formulario.
0733_Form_Code_Create_Triggered.json | Form Data Processing with Code | Procesa las respuestas de un formulario con logica personalizada mediante el nodo Code.
0805_Form_Html_Create_Triggered.json | Form to HTML Content Generator | Genera contenido HTML a partir de las respuestas de un formulario.
0890_Form_Stickynote_Send_Triggered.json | Form Submission Notification | Envia una notificacion a partir de una respuesta de formulario.
1316_Form_Stickynote_Automation_Webhook.json | Form Submission Automation (variante) | Variante del flujo de procesamiento de respuestas de formulario.
1348_Form_Automation_Triggered.json | Form Submission Automation (variante) | Otra variante del flujo de procesamiento de respuestas de formulario.
1371_Form_S3_Import_Triggered.json | Form File Upload to S3 | Sube a un bucket de AWS S3 el archivo recibido a traves de un formulario.
1420_Form_Extractfromfile_Automate_Triggered.json | Form File Upload Extraction | Extrae el contenido de un archivo subido mediante un formulario.
1441_Form_Automation_Triggered.json | Form Submission Automation (variante) | Otra variante del flujo de procesamiento de respuestas de formulario.
1537_Form_GoogleSheets_Automation_Triggered.json | Form to Google Sheets Logging | Registra las respuestas de un formulario en Google Sheets.
1554_Form_GoogleSheets_Automation_Triggered.json | Form to Google Sheets Logging (variante) | Variante del flujo de registro de formularios en Google Sheets.
1611_Form_Stickynote_Automate_Triggered.json | Form Submission Automation (variante) | Otra variante del flujo de procesamiento de respuestas de formulario.
1649_Form_Extractfromfile_Automate_Triggered.json | Form File Upload Extraction (variante) | Variante del flujo de extraccion de archivos subidos por formulario.
1762_Form_Aggregate_Automation_Triggered.json | Form Response Aggregation | Agrega multiples respuestas de un formulario con el nodo Aggregate.
1767_Form_HTTP_Automation_Webhook.json | Form Submission to External API | Envia las respuestas de un formulario a un servicio externo mediante HTTP Request.
1873_Form_HTTP_Automation_Webhook.json | Form Submission to External API (variante) | Variante del flujo de envio de respuestas de formulario a un servicio externo.
1886_Form_Markdown_Automation_Webhook.json | Form to Markdown Content | Convierte las respuestas de un formulario en contenido con formato Markdown.
1908_Form_Asana_Automate_Triggered.json | Form to Asana Task with WhatsApp Notification | Crea una tarea en Asana a partir de una respuesta de formulario y notifica por WhatsApp.
1957_Form_Stickynote_Automation_Triggered.json | Form Submission Automation (variante) | Otra variante del flujo de procesamiento de respuestas de formulario.
1968_Form_Stickynote_Automation_Webhook.json | Form Submission Automation (variante) | Otra variante del flujo de procesamiento de respuestas de formulario.
