Workflows de Clockify

Objetivo

Esta carpeta agrupa los workflows de n8n que se integran con Clockify, la herramienta de control de tiempo y seguimiento de horas de trabajo. El objetivo de estos workflows es sincronizar tickets externos y clientes de Notion con Clockify, ademas de reaccionar a los eventos propios de Clockify, evitando el registro manual de tiempos y clientes.

Estructura

El primer workflow recibe mediante un Webhook los datos de un ticket proveniente de Syncro y crea una entrada de tiempo en Clockify con el nombre del ticket. El segundo workflow sigue un patron simple de disparador mas manejo de errores mediante el nodo Clockify Trigger, que escucha los eventos de la cuenta de Clockify. El tercer workflow utiliza un Notion Trigger que detecta la creacion de un nuevo cliente en una base de datos de Notion y crea automaticamente el cliente correspondiente en Clockify (resource client). Todos los workflows incluyen un nodo Error Handler (Stop And Error) para detener la ejecucion de forma controlada ante fallos inesperados.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow deseado en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de Clockify (API Key) en los nodos correspondientes. Paso 3: Para el workflow de Syncro, configurar el Webhook en la plataforma de origen para que envie los datos del ticket a la URL generada por n8n. Paso 4: Para el workflow de clientes, configurar las credenciales de Notion Trigger indicando la base de datos de clientes a monitorear. Paso 5: Activar el workflow correspondiente y verificar en el historial de ejecuciones de n8n que las entradas de tiempo o los clientes se crean correctamente en Clockify.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0750_Clockify_Webhook_Sync_Webhook.json | Syncro to Clockify Time Entry Sync | Recibe un ticket de Syncro mediante Webhook y crea una entrada de tiempo correspondiente en Clockify.
1005_Clockify_Automate_Triggered.json | Clockify Events Automation | Escucha en tiempo real los eventos de una cuenta de Clockify y permite disparar acciones posteriores en n8n.
1923_Clockify_Stickynote_Create_Triggered.json | Notion to Clockify Client Sync | Crea automaticamente en Clockify los clientes que se anaden a una base de datos de Notion.
