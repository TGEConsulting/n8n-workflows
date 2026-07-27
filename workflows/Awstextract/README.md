Workflows de AWS Textract

Objetivo

Esta carpeta agrupa los workflows de n8n que se integran con AWS Textract, el servicio de extraccion de texto y datos de documentos de Amazon Web Services. El objetivo de este workflow es recibir documentos enviados por Telegram, almacenarlos en AWS S3, extraer su contenido con Textract y registrar la informacion resultante en Airtable, evitando la digitalizacion manual de documentos.

Estructura

El workflow de esta carpeta parte de un Telegram Trigger que recibe el documento enviado por un usuario en un chat de Telegram. El archivo se sube a un bucket de AWS S3 mediante un nodo AWS S3 y despues se procesa con el nodo AWS Textract para extraer el texto contenido en el documento. El resultado se guarda como un nuevo registro en Airtable mediante un nodo Airtable con la operacion append. El nodo Error Handler (Stop And Error) detiene la ejecucion de forma controlada ante fallos inesperados.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales del bot de Telegram en el nodo Telegram Trigger. Paso 3: Configurar las credenciales de AWS (Access Key y Secret Key) en los nodos AWS S3 y AWS Textract, indicando el bucket de destino. Paso 4: Configurar las credenciales de Airtable y seleccionar la base y tabla donde se guardara el texto extraido. Paso 5: Activar el workflow y enviar un documento al bot de Telegram para verificar en el historial de ejecuciones de n8n que el texto se extrae y se registra correctamente en Airtable.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0148_Awstextract_Telegram_Automate_Triggered.json | Telegram to AWS Textract to Airtable Automation | Recibe un documento por Telegram, lo sube a AWS S3, extrae su texto con AWS Textract y guarda el resultado en Airtable.
