Workflows de AWS Rekognition

Objetivo

Esta carpeta agrupa los workflows de n8n que se integran con AWS Rekognition, el servicio de analisis de imagenes de Amazon Web Services. El objetivo de estos workflows es procesar imagenes de forma automatizada, extraer texto u otra informacion visual y almacenar los resultados en herramientas externas como Google Sheets, evitando la revision manual de cada imagen.

Estructura

El workflow de esta carpeta parte de un nodo Manual Trigger para pruebas y utiliza el nodo AWS Rekognition con la operacion detectText para identificar el texto presente en una imagen. Antes y despues del analisis se emplean nodos HTTP Request para obtener la imagen de origen y, si aplica, enviar resultados a otros servicios. Un nodo Set organiza los datos relevantes (nombre de la imagen, enlace y texto detectado) y un nodo Function los transforma antes de escribirlos en Google Sheets. El nodo Error Handler (Stop And Error) detiene la ejecucion de forma controlada ante fallos inesperados.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de AWS (Access Key y Secret Key) en el nodo AWS Rekognition. Paso 3: Configurar las credenciales de Google Sheets OAuth2 en el nodo Google Sheets para definir la hoja de destino. Paso 4: Ajustar los nodos HTTP Request con la url de origen de las imagenes que se desean analizar. Paso 5: Ejecutar el workflow manualmente o sustituir el Manual Trigger por un disparador automatico y verificar en el historial de ejecuciones de n8n que el texto detectado se registra correctamente en Google Sheets.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0150_Awsrekognition_GoogleSheets_Automation_Webhook.json | AWS Rekognition to Google Sheets Automation | Detecta texto en una imagen mediante AWS Rekognition y guarda el nombre, enlace y texto extraido en una hoja de Google Sheets.
