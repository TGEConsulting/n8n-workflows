# Workflows de Aggregate

## Objetivo
Esta carpeta reune workflows de ejemplo que muestran distintas formas de usar el nodo Aggregate de n8n, el cual combina varios elementos de una lista en un unico item de datos. El objetivo de esta coleccion es servir de referencia para consolidar informacion proveniente de multiples ejecuciones, mensajes o registros (Gmail, Telegram, Airtable, JotForm, Typeform, Google Sheets, HTTP, entre otros) antes de continuar el procesamiento dentro de un workflow.

## Estructura
La mayoria de los workflows sigue el patron disparador (trigger de Gmail, Telegram, formulario, webhook, calendario o ejecucion manual) seguido de nodos de transformacion como Split Out, If o Switch, luego el nodo Aggregate que consolida los datos, y finalmente una accion de salida (enviar un mensaje, escribir en una hoja de calculo, llamar a una API, etc.). Varios workflows incluyen nodos Sticky Note a modo de documentacion visual dentro del propio lienzo, y un nodo Error Handler (Stop And Error) para detener la ejecucion de forma controlada ante estados inesperados.

## Metodo de aplicacion
Paso 1: Revisar el nombre de cada archivo para identificar que integracion utiliza como disparador y como accion de salida antes de importarlo.
Paso 2: Importar el archivo JSON elegido en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows.
Paso 3: Configurar las credenciales especificas que requiera ese workflow (por ejemplo Gmail, Telegram, Airtable o Google Sheets) en los nodos correspondientes.
Paso 4: Ajustar la configuracion del nodo Aggregate (campos a combinar y modo de agregacion) segun la estructura real de los datos de entrada.
Paso 5: Activar el workflow y probarlo generando el evento disparador correspondiente, verificando en el historial de ejecuciones de n8n que los datos se combinen correctamente.

## Workflows incluidos
| Archivo | Disparador principal | Descripcion |
|---|---|---|
| 0472_Aggregate_Gmail_Create_Triggered.json | Gmail Trigger | Se dispara al recibir un correo en Gmail, separa y agrega elementos del mensaje y utiliza Gmail para acciones de salida. |
| 0480_Aggregate_Telegram_Automate_Triggered.json | Telegram Trigger | Se dispara con un mensaje de Telegram, agrega datos y responde por Telegram. |
| 0681_Aggregate_HTTP_Create_Webhook.json | Execute Workflow Trigger | Subflujo reutilizable que combina logica condicional, Airtable y peticiones HTTP, agregando los resultados obtenidos. |
| 0691_Aggregate_Jotform_Create_Triggered.json | JotForm Trigger | Se dispara al enviarse un formulario en JotForm, agrega las respuestas y las envia a Klicktipp. |
| 0695_Aggregate_Stickynote_Create_Webhook.json | Webhook | Se dispara mediante un webhook generico, agrega los datos recibidos y los envia a Klicktipp. |
| 0697_Aggregate_Typeform_Create_Triggered.json | Typeform Trigger | Se dispara al enviarse un formulario en Typeform, agrega las respuestas y las envia a Klicktipp. |
| 0762_Aggregate_Stickynote_Create_Triggered.json | Execute Workflow Trigger | Subflujo que ejecuta otro workflow y agrega los resultados devueltos. |
| 0800_Aggregate_Telegram_Automate_Triggered.json | Telegram Trigger | Se dispara con un mensaje de Telegram, agrega datos provenientes de Google Sheets y responde por Telegram. |
| 1324_Aggregate_Gmail_Send_Triggered.json | Gmail Trigger | Se dispara al recibir un correo en Gmail, agrega los elementos y envia una respuesta por Gmail. |
| 1374_Aggregate_Stickynote_Create_Triggered.json | Manual Trigger | Flujo de prueba manual que limita y agrega un conjunto de datos de ejemplo. |
| 1404_Aggregate_Telegram_Automation_Triggered.json | Telegram Trigger | Se dispara con un mensaje de Telegram y usa Airtable, incluyendo una herramienta de IA, para agregar y consultar datos. |
| 1413_Aggregate_Telegram_Automation_Triggered.json | Telegram Trigger | Variante del workflow anterior, con el mismo patron de Telegram, Airtable y agregacion de datos. |
| 1430_Aggregate_Schedule_Send_Scheduled.json | Schedule Trigger | Se ejecuta en un horario programado, agrega datos y envia un correo por Gmail. |
| 1506_Aggregate_Telegram_Automation_Triggered.json | Telegram Trigger | Se dispara con un mensaje de Telegram, agrega datos y responde por Telegram. |
| 1544_Aggregate_Schedule_Send_Scheduled.json | Schedule Trigger | Variante programada que agrega datos y envia un correo por Gmail. |
| 1576_Aggregate_Stickynote_Automate_Webhook.json | Manual Trigger | Flujo de prueba manual que combina codigo personalizado, peticiones HTTP y agregacion de datos. |
