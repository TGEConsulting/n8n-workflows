# Workflows de Google Docs

## Objetivo

Esta carpeta agrupa workflows de n8n que se integran con Google Docs para automatizar la creacion, extraccion y procesamiento de documentos, conectando la herramienta con servicios como Google Drive, Google Sheets, Slack o Gmail. El objetivo es evitar la manipulacion manual de documentos y facilitar su generacion o consulta a partir de datos externos.

## Estructura

Los workflows utilizan disparadores variados como Webhook, Manual Trigger o Google Drive Trigger para iniciar el proceso, seguidos de nodos como Extract From File o Code para leer y transformar el contenido, y el nodo Google Docs para crear o modificar documentos. El flujo puede continuar hacia Google Sheets o Google Drive para almacenar resultados, o hacia Slack y Gmail para notificar. Algunos workflows exponen Google Drive, Gmail o Google Sheets como herramientas dentro de un agente. Un nodo Stop And Error detiene la ejecucion ante fallos.

## Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de Google Docs y de los demas servicios integrados (Google Drive, Google Sheets, Slack, Gmail, etc.). Paso 3: Ajustar la plantilla o el documento de Google Docs que debe crearse o procesarse. Paso 4: Activar el workflow o configurar el disparador (Webhook, Manual, Google Drive Trigger) segun el modo de ejecucion deseado. Paso 5: Verificar en el historial de ejecuciones de n8n que los documentos se generan o procesan correctamente.

## Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0524_Googledocs_Webhook_Create_Webhook.json | Webhook Create Webhook | Recibe archivos por webhook, extrae su contenido y crea documentos en Google Docs, notificando por Slack y Gmail.
1134_Googledocs_Code_Create_Webhook.json | Code Create Webhook | Genera documentos en Google Docs a partir de datos procesados con Code y los convierte en archivos con Convert To File.
1279_Googledocs_Manual_Automate_Triggered.json | Manual Automate Triggered | Procesa documentos de Google Docs en lotes y sincroniza la informacion con Google Sheets y Google Drive.
1287_Googledocs_Googledrivetool_Monitor_Triggered.json | Googledrivetool Monitor Triggered | Monitorea Google Drive para detectar nuevos archivos, extrae su contenido y permite que un agente use Gmail, Drive y Sheets como herramientas junto con Google Docs.
1335_Googledocs_Webhook_Process_Webhook.json | Webhook Process Webhook | Procesa solicitudes recibidas por webhook para generar o actualizar documentos en Google Docs.
1858_Googledocs_Manual_Automate_Triggered.json | Manual Automate Triggered (variante) | Variante del flujo de procesamiento manual de documentos en Google Docs con sincronizacion en Sheets y Drive.
