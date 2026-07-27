Workflows de Dropbox

Objetivo

Esta carpeta agrupa los workflows de n8n que se integran con Dropbox, el servicio de almacenamiento de archivos en la nube. El objetivo de este workflow es mantener un inventario de todos los workflows de una instancia de n8n en Airtable y respaldar sus archivos asociados en Dropbox, evitando el seguimiento manual de los workflows existentes y sus copias de seguridad.

Estructura

El workflow de esta carpeta parte de un Manual Trigger y obtiene todos los workflows de la instancia de n8n mediante HTTP Request a la API de n8n. Un nodo Function y varios nodos Set preparan los datos relevantes de cada workflow (nombre, identificador, estado activo, configuracion de Cron, fecha de creacion y actualizacion). Con un Split In Batches se procesa cada workflow de forma individual, se verifica en Airtable si ya existe un registro para ese workflow (IF Airtable record exists) y se crea o actualiza segun corresponda. Ademas, el workflow mueve datos binarios y los sube a Dropbox, obteniendo despues el enlace del archivo. El nodo Error Handler (Stop And Error) detiene la ejecucion de forma controlada ante fallos inesperados.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de la API de n8n (Authorization) para consultar los workflows existentes. Paso 3: Configurar las credenciales de Airtable, indicando la base y tabla donde se registrara el inventario de workflows. Paso 4: Configurar las credenciales de Dropbox para el almacenamiento de los archivos asociados. Paso 5: Ejecutar el workflow manualmente y verificar en el historial de ejecuciones de n8n que el inventario se actualiza en Airtable y los archivos se suben correctamente a Dropbox.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0969_Dropbox_Manual_Automate_Webhook.json | n8n Workflow Inventory to Airtable and Dropbox | Registra el inventario de workflows de n8n en Airtable y respalda sus archivos asociados en Dropbox.
