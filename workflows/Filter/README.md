Workflows de Filter

Objetivo

Esta carpeta agrupa un conjunto amplio y diverso de workflows de n8n cuyo elemento comun es el uso del nodo Filter para quedarse solo con los datos que cumplen determinadas condiciones antes de continuar el flujo. Cubren casos de uso muy variados (notificaciones, reportes, monitoreo de feeds, encuestas) combinados con distintos disparadores y aplicaciones, unidos por la necesidad de descartar informacion irrelevante antes de procesarla.

Estructura

Cada workflow combina un disparador (Manual, Schedule, Webhook, Telegram, Slack, WhatsApp o un formulario de n8n) con uno o mas nodos Filter que aplican condiciones sobre los datos recibidos. Segun el workflow, los datos filtrados se envian a Telegram, Slack o Gmail, se registran en Google Sheets, se resumen con el nodo Summarize, se convierten con Extract From File, se sincronizan con ConvertKit o Jira, o se obtienen de un feed RSS mediante RSS Feed Read. La mayoria incluye nodos Sticky Note explicativos y un nodo Error Handler (Stop And Error) para el manejo de fallos.

Metodo de aplicacion

Paso 1: Localizar el archivo JSON del workflow especifico segun su nombre y la descripcion de la tabla siguiente. Paso 2: Importarlo en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 3: Configurar las credenciales de las aplicaciones externas que utilice el workflow. Paso 4: Ajustar las condiciones del nodo Filter segun el criterio que se desee aplicar a los datos. Paso 5: Activar o ejecutar el workflow y verificar en el historial de ejecuciones de n8n que los datos se filtran y se procesan correctamente.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0335_Filter_Telegram_Send_Triggered.json | Filtered Telegram Notification | Filtra los datos recibidos y envia una notificacion por Telegram si cumplen la condicion.
0411_Filter_Form_Send_Triggered.json | Form Response Filtering | Filtra las respuestas de un formulario de n8n antes de procesarlas.
0431_Filter_Convertkit_Create_Triggered.json | Filtered ConvertKit Subscriber Sync | Filtra suscriptores antes de sincronizarlos con ConvertKit.
0451_Filter_Slack_Update_Webhook.json | Filtered Slack Update | Filtra los datos de una solicitud Webhook y actualiza un mensaje en Slack.
0572_Filter_Schedule_Send_Scheduled.json | Scheduled Filtered Report | Filtra datos de forma programada y envia el resultado a traves del canal configurado.
0595_Filter_Manual_Send_Triggered.json | Manual Filtered Send | Filtra datos manualmente y los envia al destino configurado.
0612_Filter_Slack_Send_Scheduled.json | Scheduled Filtered Slack Message | Filtra datos de forma programada y envia un mensaje a Slack.
0801_Filter_Schedule_Import_Webhook.json | Scheduled Filtered Import | Filtra datos importados de forma programada antes de procesarlos.
0830_Filter_Summarize_Send_Scheduled.json | Survey Response Summary Report | Filtra respuestas de un formulario, las resume con IA y envia un reporte programado por Gmail.
0849_Filter_Extractfromfile_Create_Triggered.json | Filtered File Content Extraction | Extrae el contenido de un archivo y lo filtra antes de continuar el flujo.
0879_Filter_HTTP_Update_Webhook.json | Filtered HTTP Data Update | Filtra datos obtenidos por HTTP Request antes de actualizarlos en el destino.
0917_Filter_Whatsapp_Create_Triggered.json | Filtered WhatsApp Automation | Filtra mensajes recibidos por WhatsApp antes de procesarlos.
0948_Filter_Schedule_Create_Scheduled.json | Scheduled Filtered Creation | Filtra datos de forma programada antes de crear un registro en el destino configurado.
1321_Filter_Manual_Send_Triggered.json | Manual Filtered Send (variante) | Variante del flujo de filtrado manual de datos.
1383_Filter_Slack_Create_Webhook.json | Filtered Slack Creation | Filtra los datos de una solicitud Webhook antes de crear un recurso en Slack.
1414_Filter_Summarize_Automation_Triggered.json | Filtered Data Summarization | Filtra datos y los resume con el nodo Summarize.
1562_Filter_Manual_Import_Webhook.json | Manual Filtered Import | Filtra datos importados manualmente antes de procesarlos.
1570_Filter_Summarize_Automation_Triggered.json | Filtered Data Summarization (variante) | Variante del flujo de filtrado y resumen de datos.
1667_Filter_Summarize_Automation_Triggered.json | Filtered Data Summarization (variante) | Otra variante del flujo de filtrado y resumen de datos.
1751_Filter_Schedule_Automation_Scheduled.json | Scheduled Filtered Automation | Filtra datos de forma programada como parte de un flujo de automatizacion.
1772_Filter_Rssfeedread_Monitor_Scheduled.json | RSS Feed Filtering and Notification | Filtra las entradas de un feed RSS y notifica o registra las que cumplen la condicion en Jira o Gmail.
1791_Filter_Summarize_Create_Triggered.json | Filtered Data Summarization (variante) | Otra variante del flujo de filtrado y resumen de datos.
2006_Filter_Manual_Automation_Webhook.json | Manual Filtered Automation | Filtra datos como parte de un flujo de automatizacion disparado manualmente o por Webhook.
