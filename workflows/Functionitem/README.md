# Workflows de Function Item

## Objetivo

Esta carpeta agrupa workflows de n8n que utilizan el nodo Function Item (y nodos relacionados de transformacion de items) para aplicar logica personalizada de JavaScript sobre los datos que circulan por el flujo. El objetivo es centralizar ejemplos de transformacion, enriquecimiento y sincronizacion de datos entre distintos servicios (Dropbox, Telegram, Pipedrive, Zendesk, Raindrop, entre otros), evitando que estas manipulaciones deban programarse manualmente cada vez.

## Estructura

Cada workflow parte de un disparador (Webhook, Cron, Manual o Trigger especifico del servicio) que entrega los datos de entrada al nodo Function Item, donde se ejecuta el codigo JavaScript encargado de dar formato, filtrar o combinar la informacion. Segun el caso, el flujo continua hacia nodos de integracion como HTTP Request, Pipedrive, Zendesk o Execute Command, y en los flujos de sincronizacion se incorporan nodos Merge e If para comparar y decidir que registros deben actualizarse.

## Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Revisar y adaptar el codigo del nodo Function Item a la estructura de datos real que se va a procesar. Paso 3: Configurar las credenciales de los servicios externos utilizados (Dropbox, Telegram, Pipedrive, Zendesk, Raindrop, etc.) segun corresponda. Paso 4: Activar el workflow o configurar el disparador (Webhook, Cron) segun el modo de ejecucion deseado. Paso 5: Verificar en el historial de ejecuciones de n8n que los datos se transforman y sincronizan correctamente.

## Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0031_Functionitem_Dropbox_Automation_Webhook.json | Dropbox Automation Webhook | Recibe datos por webhook, los transforma con Function Item y los envia a Dropbox.
0068_Functionitem_Manual_Import_Scheduled.json | Manual Import Scheduled | Importa datos de forma programada y los procesa con Function Item antes de continuar el flujo.
0146_Functionitem_Telegram_Create_Webhook.json | Telegram Create Webhook | Procesa datos recibidos por webhook con Function Item y crea mensajes en Telegram.
0178_Functionitem_Executecommand_Automation_Webhook.json | Execute Command Automation Webhook | Transforma con Function Item la salida de un comando ejecutado y automatiza acciones posteriores.
0184_Functionitem_Itemlists_Automate.json | Item Lists Automate | Combina Function Item con Item Lists para transformar y reorganizar colecciones de datos.
0246_Functionitem_Pipedrive_Create_Scheduled.json | Pipedrive Create Scheduled | Ejecuta de forma programada la creacion de registros en Pipedrive tras procesar los datos con Function Item.
0247_Functionitem_HTTP_Create_Webhook.json | HTTP Create Webhook | Recibe datos por webhook, los transforma con Function Item y realiza una peticion HTTP de creacion.
0255_Functionitem_Manual_Create_Triggered.json | Manual Create Triggered | Flujo disparado manualmente que usa Function Item para preparar datos antes de crear un registro.
0266_Functionitem_Zendesk_Create_Webhook.json | Zendesk Create Webhook | Sincroniza registros entre Pipedrive y Zendesk mediante Cron, Function Item, Merge e If.
0267_Functionitem_Zendesk_Create_Scheduled.json | Zendesk Create Scheduled | Variante programada de la sincronizacion Pipedrive-Zendesk usando Function Item.
1067_Functionitem_Manual_Export_Webhook.json | Manual Export Webhook | Exporta datos procesados con Function Item a partir de una llamada webhook o ejecucion manual.
1140_Functionitem_Raindrop_Automation_Scheduled.json | Raindrop Automation Scheduled | Automatiza de forma programada la creacion o actualizacion de marcadores en Raindrop tras transformar los datos con Function Item.
1157_Functionitem_Executecommand_Update_Webhook.json | Execute Command Update Webhook | Actualiza datos combinando la salida de un comando ejecutado con logica personalizada en Function Item.
