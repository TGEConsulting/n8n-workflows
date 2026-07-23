# Workflows de Airtable Tool (uso con Agentes de IA)

## Objetivo
Esta carpeta agrupa workflows de n8n que utilizan Airtable no como simple almacenamiento, sino como herramienta (Tool) conectada a un Agente de IA. El objetivo es que un modelo de lenguaje pueda leer y escribir datos en Airtable de forma autonoma dentro de un flujo de trabajo, por ejemplo para generar y guardar contenido de redes sociales de forma asistida por IA.

## Estructura
El patron general es: un disparador de Airtable (Airtable Trigger) o similar inicia el flujo, un nodo Wait o Set prepara el contexto, y un Agente de IA utiliza el nodo Airtable Tool para consultar o actualizar registros como parte de su razonamiento. Se incluyen nodos Sticky Note como documentacion visual dentro del lienzo y un nodo Error Handler (Stop And Error) para detener la ejecucion ante estados inesperados.

## Metodo de aplicacion
Paso 1: Importar el archivo JSON elegido en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows.
Paso 2: Configurar las credenciales de Airtable (API Key o token de acceso personal) tanto en el nodo Airtable como en el nodo Airtable Tool.
Paso 3: Configurar las credenciales del modelo de lenguaje que utilice el Agente de IA (por ejemplo OpenAI) en el nodo correspondiente.
Paso 4: Ajustar la base y la tabla de Airtable que usara el agente, y revisar el prompt o las instrucciones del agente para adaptarlo al caso de uso deseado.
Paso 5: Activar el workflow y probarlo generando el evento disparador, verificando en el historial de ejecuciones de n8n que el agente consulte o actualice Airtable correctamente.

## Workflows incluidos
| Archivo | Nombre del workflow | Descripcion |
|---|---|---|
| 1261_Airtabletool_Stickynote_Automation_Triggered.json | AI Social Media Caption Creator | Usa un Agente de IA con la herramienta Airtable Tool para generar descripciones (captions) de redes sociales y guardarlas o consultarlas en Airtable. |
| 1723_Airtabletool_Stickynote_Automation_Triggered.json | AI Social Media Caption Creator | Variante del mismo workflow de generacion de captions con IA apoyado en Airtable Tool. |
