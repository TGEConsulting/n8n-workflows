Workflows de Date & Time

Objetivo

Esta carpeta agrupa un conjunto amplio y diverso de workflows de n8n cuyo elemento comun es el uso del nodo Date & Time para calcular, formatear o comparar fechas dentro del flujo. Cubren casos de uso muy variados, desde reportes programados y sincronizacion de calendarios hasta seguridad de correo y generacion de contenido, unidos por la necesidad de procesar fechas como parte de su logica.

Estructura

Cada workflow combina un disparador (Cron, Schedule, Webhook o Manual) con uno o mas nodos Date & Time que calculan rangos, formatean marcas de tiempo o determinan si una fecha cumple una condicion, y con los nodos propios de la aplicacion externa involucrada en cada caso (Slack, Google Calendar, Notion, Todoist, ServiceNow, MySQL, Pipedrive, Dropbox, WordPress, Google Sheets, entre otros). Varios workflows incluyen ademas nodos de logica (If, Switch, Compare Datasets) para decidir que accion tomar segun la fecha calculada, y la mayoria cuenta con un nodo Error Handler (Stop And Error) para el manejo de fallos.

Metodo de aplicacion

Paso 1: Localizar el archivo JSON del workflow especifico segun su nombre y la descripcion de la tabla siguiente. Paso 2: Importarlo en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 3: Configurar las credenciales de las aplicaciones externas que utilice el workflow. Paso 4: Revisar y ajustar las expresiones de fecha en los nodos Date & Time segun la zona horaria y el rango deseado. Paso 5: Activar o ejecutar el workflow y verificar en el historial de ejecuciones de n8n que las fechas se calculan correctamente y que la integracion produce el resultado esperado.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0087_Datetime_Slack_Automate_Scheduled.json | Shopify Order Report to Slack | Revisa pedidos de Shopify de forma programada, calcula datos de fecha y envia un reporte a Slack y Google Sheets.
0159_Datetime_Functionitem_Create_Webhook.json | Website to RSS Feed Generator | Extrae publicaciones de un sitio web, formatea sus fechas y genera un feed RSS accesible por Webhook.
0168_Datetime_GoogleCalendar_Send_Scheduled.json | Monthly Payroll Attendance Report | Calcula los dias de vacaciones o baja del mes anterior desde Google Calendar y envia el resumen a nomina por correo.
0311_Datetime_Schedule_Create_Webhook.json | Gmail to Notion Task Sync | Sincroniza correos etiquetados de Gmail con tareas en Notion y elimina la etiqueta al marcarlas como completadas.
0316_Datetime_Schedule_Create_Webhook.json | Outlook Calendar to Notion Sync | Sincroniza los eventos de un rango de dias del calendario de Outlook con paginas de una base de datos de Notion.
0348_Datetime_GoogleCalendar_Automation_Scheduled.json | Google Calendar to Zoom Meeting Creator | Revisa diariamente el calendario de Google y crea una reunion de Zoom cuando corresponde.
0396_Datetime_Schedule_Automation_Scheduled.json | n8n Workflows Backup to Dropbox | Respalda periodicamente los workflows de n8n en Dropbox y purga las copias mas antiguas que el numero de dias configurado.
0444_Datetime_Todoist_Create_Webhook.json | Todoist Task Snooze Scheduler | Mueve tareas de Todoist a un proyecto de pospuestas y las devuelve al proyecto original en la fecha calculada.
0682_Datetime_Schedule_Create_Scheduled.json | ServiceNow Incidents to Slack | Revisa cada 5 minutos los incidentes nuevos de ServiceNow y los publica ordenados en un canal de Slack.
1092_Datetime_Schedule_Sync_Scheduled.json | MySQL to Pipedrive CRM Sync | Compara registros de MySQL con Pipedrive de forma programada y crea o actualiza los datos que difieren.
1272_Datetime_Webhook_Create_Webhook.json | Google Sheets to WordPress Publisher | Convierte filas de Google Sheets en contenido Markdown y publica articulos en WordPress, notificando por Slack.
1273_Datetime_Webhook_Create_Webhook.json | Google Sheets to WordPress Publisher (variante) | Variante del mismo flujo de publicacion de articulos en WordPress desde Google Sheets.
1296_Datetime_Splitout_Process.json | DMARC Report Parser and Alerting | Descomprime y analiza reportes DMARC recibidos por correo, los guarda en MySQL y alerta por Slack ante problemas de DKIM o SPF.
1510_Datetime_Code_Automation_Webhook.json | Intelligent Web Query and Semantic Re-Ranking | Recibe una consulta por Webhook y reordena los resultados de busqueda mediante reordenamiento semantico con IA.
1523_Datetime_Code_Automation_Scheduled.json | Scheduled Condition Alerting | Evalua una condicion calculada con codigo y fechas, y notifica el resultado por Slack o correo electronico.
1755_Datetime_Code_Automation_Webhook.json | HTTP Data to Google Sheets Processor | Obtiene datos mediante HTTP Request, los procesa con fechas y codigo personalizado y los guarda en Google Sheets.
2003_Datetime_Code_Automation_Webhook.json | AI Chat Webhook Assistant | Expone un asistente conversacional de IA mediante Webhook, apoyado en calculos de fecha y hora.
2050_Datetime_Code_Automation_Webhook.json | HTTP Data to Google Sheets Processor (variante) | Variante del mismo flujo de obtencion de datos por HTTP y almacenamiento en Google Sheets.
