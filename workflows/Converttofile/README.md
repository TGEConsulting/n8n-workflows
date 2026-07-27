Workflows de Convert to File

Objetivo

Esta carpeta agrupa los workflows de n8n que utilizan el nodo Convert to File para transformar datos o imagenes generadas en archivos descargables. El objetivo de estos workflows es exportar el historial de ejecuciones de n8n a CSV y generar o remezclar imagenes con inteligencia artificial (OpenAI e Ideogram), guardando el resultado en Google Drive y registrando los enlaces en Google Sheets.

Estructura

El primer workflow parte de un Manual Trigger, obtiene todas las ejecuciones de la cuenta de n8n mediante el nodo n8n y las convierte a un archivo CSV con Convert to File. El segundo workflow lee URLs de imagenes desde Google Sheets, las descarga, las analiza con OpenAI usando un prompt de fotografia de producto, genera una nueva imagen, la convierte de Base64 a archivo con Convert to File, la sube a Google Drive y registra el enlace resultante en la hoja de calculo. El tercer workflow, un equipo de diseno grafico basado en IA, toma imagenes de Google Sheets, las remezcla con Ideogram segun distintos parametros (estilo, relacion de aspecto, prompt negativo) y sube las nuevas versiones a Google Drive.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow deseado en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Para el workflow de ejecuciones, configurar las credenciales de la API de n8n. Paso 3: Para los workflows de imagenes, configurar las credenciales de OpenAI o de Ideogram, asi como las de Google Sheets y Google Drive para el origen y destino de los archivos. Paso 4: Ajustar los prompts, estilos y parametros de generacion de imagen segun el resultado deseado. Paso 5: Ejecutar el workflow y verificar en el historial de ejecuciones de n8n que los archivos se generan y se guardan correctamente en Drive o se exportan en CSV.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0508_Converttofile_Manual_Process_Triggered.json | n8n Executions to CSV Export | Obtiene el historial de ejecuciones de n8n y lo convierte en un archivo CSV descargable.
0889_Converttofile_HTTP_Create_Webhook.json | AI Product Photography Generator | Analiza imagenes de producto con OpenAI, genera una nueva imagen y la guarda en Google Drive registrando el enlace en Google Sheets.
1985_Converttofile_HTTP_Automation_Webhook.json | AI Graphic Design Team with Ideogram | Remezcla imagenes con Ideogram segun distintos estilos y parametros, y sube las nuevas versiones a Google Drive.
