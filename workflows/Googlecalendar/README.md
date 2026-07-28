# Workflows de Google Calendar

## Objetivo

Esta carpeta agrupa workflows de n8n que se integran con Google Calendar para automatizar la creacion, consulta y notificacion de eventos, conectando el calendario con formularios, hojas de calculo, Slack, Gmail o webhooks. El objetivo es evitar la gestion manual de la agenda y sincronizar automaticamente los eventos con otras herramientas.

## Estructura

Los workflows utilizan distintos disparadores segun el caso: Form Trigger para crear eventos a partir de formularios, Schedule Trigger para revisar la agenda periodicamente, Google Sheets Trigger o Typeform Trigger para sincronizar datos, y Webhook para crear eventos bajo demanda. Tras el disparador, el nodo Google Calendar gestiona el evento, y el flujo puede continuar hacia Gmail o Slack para notificar, o hacia Google Sheets y Google Drive para registrar la informacion. Nodos como If, Filter y Remove Duplicates depuran los datos, y un nodo Stop And Error detiene la ejecucion ante fallos.

## Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de Google Calendar y de los servicios adicionales integrados (Gmail, Slack, Google Sheets, etc.). Paso 3: Seleccionar el calendario correspondiente y ajustar los campos del formulario o la hoja de calculo de origen. Paso 4: Activar el workflow o configurar el disparador (Form, Schedule, Webhook) segun el modo de ejecucion deseado. Paso 5: Verificar en el historial de ejecuciones de n8n que los eventos se crean y las notificaciones se envian correctamente.

## Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0647_GoogleCalendar_Form_Create_Triggered.json | Form Create Triggered | Crea eventos en Google Calendar a partir de datos enviados en un formulario y notifica por Gmail.
0783_GoogleCalendar_Schedule_Create_Scheduled.json | Schedule Create Scheduled | Revisa periodicamente el calendario, filtra y depura eventos duplicados, y envia notificaciones por Gmail.
1116_GoogleCalendar_GoogleSheets_Create_Triggered.json | GoogleSheets Create Triggered | Crea eventos en Google Calendar a partir de respuestas de Typeform y registra la informacion en Google Sheets y Mattermost.
1346_GoogleCalendar_GoogleSheets_Automate_Triggered.json | GoogleSheets Automate Triggered | Escucha cambios en Google Sheets y crea o actualiza eventos en Google Calendar automaticamente.
1361_GoogleCalendar_Webhook_Create_Webhook.json | Webhook Create Webhook | Crea eventos en Google Calendar a partir de una llamada webhook y responde con Respond to Webhook.
1573_GoogleCalendar_Slack_Create_Webhook.json | Slack Create Webhook | Crea eventos en Google Calendar a partir de un webhook y notifica el resultado en Slack.
1620_GoogleCalendar_Form_Automation_Triggered.json | Form Automation Triggered | Variante del flujo de creacion de eventos a partir de formularios, con notificacion por Gmail.
1668_GoogleCalendar_Filter_Automation_Triggered.json | Filter Automation Triggered | Escucha correos de Gmail, filtra la informacion relevante y crea eventos correspondientes en Google Calendar.
