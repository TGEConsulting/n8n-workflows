# Workflows de APITemplate.io

## Objetivo
Esta carpeta agrupa el workflow de n8n que se integra con APITemplate.io, un servicio que genera documentos e imagenes (PDF, imagenes de certificados, reportes, etc.) a partir de plantillas predefinidas. El objetivo es generar automaticamente un documento personalizado cada vez que se recibe informacion nueva, por ejemplo a partir de las respuestas de un formulario.

## Estructura
El workflow sigue un patron de disparador mas generacion de documento mas manejo de errores. El nodo Typeform Trigger recibe las respuestas de un formulario en tiempo real mediante un webhook, y el nodo APITemplate.io toma esos datos para generar el documento o imagen final utilizando una plantilla previamente configurada en la plataforma. El nodo Error Handler (Stop And Error) detiene la ejecucion de forma controlada si el flujo llega a un estado no esperado.

## Metodo de aplicacion
Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows.
Paso 2: Configurar las credenciales de Typeform en el nodo Typeform Trigger y seleccionar el formulario que se desea escuchar.
Paso 3: Configurar las credenciales de APITemplate.io (API Key) en el nodo correspondiente y seleccionar la plantilla de documento previamente creada en la plataforma.
Paso 4: Mapear los campos de la respuesta del formulario hacia las variables que espera la plantilla del documento.
Paso 5: Activar el workflow y probarlo enviando una respuesta de prueba en Typeform, verificando en el historial de ejecuciones de n8n que el documento se genere correctamente.

## Workflows incluidos
| Archivo | Nombre del workflow | Descripcion |
|---|---|---|
| 1224_Apitemplateio_Typeform_Automation_Triggered.json | Production Workflow | Recibe una respuesta de un formulario en Typeform y utiliza APITemplate.io para generar automaticamente un documento o imagen personalizada con esos datos. |
