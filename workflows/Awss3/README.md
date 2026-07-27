Workflows de AWS S3

Objetivo

Esta carpeta agrupa los workflows de n8n que se integran con AWS S3, el servicio de almacenamiento de objetos de Amazon Web Services. El objetivo de estos workflows es automatizar la subida, descarga, transcripcion y compresion de archivos almacenados en buckets de S3, conectando este almacenamiento con otras herramientas como Google Drive, AWS Transcribe y Google Sheets.

Estructura

Las tres automatizaciones de esta carpeta cubren casos de uso distintos sobre AWS S3. La primera se dispara con un Google Drive Trigger, sube el archivo a S3, lo transcribe con AWS Transcribe, espera el resultado con un nodo Wait y registra la transcripcion en Google Sheets. La segunda tambien parte de un Google Drive Trigger, combina los datos con un nodo Merge y descarga o sube el archivo correspondiente en S3. La tercera utiliza un Manual Trigger para listar y descargar todos los archivos de una carpeta en S3, agregarlos en un solo item con Aggregate y comprimirlos en un archivo ZIP. Todos los workflows incluyen un nodo Error Handler (Stop And Error) para detener la ejecucion ante fallos inesperados.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow deseado en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de AWS (Access Key y Secret Key) en los nodos AWS S3, y en su caso, AWS Transcribe. Paso 3: Configurar las credenciales de Google Drive y Google Sheets OAuth2 en los nodos correspondientes cuando el workflow los utilice. Paso 4: Ajustar el bucket y la carpeta de S3 en cada nodo segun el entorno de destino. Paso 5: Activar el workflow o ejecutarlo manualmente segun su disparador y verificar en el historial de ejecuciones de n8n que los archivos se suben, transcriben o comprimen correctamente.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0149_Awss3_Wait_Automate_Triggered.json | Google Drive to S3 Transcription Automation | Sube un archivo de Google Drive a S3, lo transcribe con AWS Transcribe, espera el resultado y registra la transcripcion en Google Sheets.
0151_Awss3_GoogleDrive_Import_Triggered.json | Google Drive to S3 Import | Escucha nuevos archivos en Google Drive y los importa o sincroniza con un bucket de AWS S3.
0593_Awss3_Compression_Automate_Triggered.json | S3 Files Compression | Lista y descarga todos los archivos de una carpeta en S3, los agrega en un solo item y los comprime en un archivo ZIP.
