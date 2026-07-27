Workflows de Edit Image

Objetivo

Esta carpeta agrupa los workflows de n8n que utilizan el nodo Edit Image para redimensionar imagenes como parte de un proceso de analisis de curriculums (CV) con inteligencia artificial. El objetivo es descargar el curriculum de un candidato desde Google Drive, convertirlo de PDF a imagen, ajustarlo de tamano y analizarlo con un modelo de IA para decidir si el candidato debe avanzar a la siguiente etapa del proceso de seleccion.

Estructura

Ambos workflows de esta carpeta siguen la misma estructura. Un Manual Trigger inicia el proceso descargando el curriculum en PDF desde Google Drive. Una API externa (PDF-to-Image API) convierte el PDF en una o varias imagenes, y el nodo Edit Image redimensiona la imagen resultante (operation resize) para optimizarla antes del analisis. La imagen se envia a un modelo de Google Gemini (Candidate Resume Analyser) que evalua el contenido del curriculum, y un Structured Output Parser junto con un nodo If determinan si el candidato debe proceder a la segunda etapa del proceso de seleccion.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de Google Drive para acceder a la carpeta donde se almacenan los curriculums. Paso 3: Configurar las credenciales de la API de conversion de PDF a imagen y ajustar los parametros de formato y resolucion (dpi) segun sea necesario. Paso 4: Configurar las credenciales de Google Gemini (PaLM) API para el analisis del curriculum. Paso 5: Ejecutar el workflow manualmente con un curriculum de prueba y verificar en el historial de ejecuciones de n8n que la evaluacion y la decision de avance se generan correctamente.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0575_Editimage_Manual_Update_Webhook.json | AI Resume Screening from PDF | Convierte un curriculum de PDF a imagen, la redimensiona y la analiza con IA para decidir si el candidato avanza de etapa.
1369_Editimage_Manual_Automation_Webhook.json | AI Resume Screening from PDF (variante) | Variante del mismo flujo de analisis de curriculums mediante conversion de PDF a imagen y evaluacion con IA.
