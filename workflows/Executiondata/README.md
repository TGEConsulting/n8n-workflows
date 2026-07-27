Workflows de Execution Data

Objetivo

Esta carpeta agrupa los workflows de n8n que utilizan el nodo Execution Data para guardar metadatos personalizados dentro del historial de ejecuciones de n8n. El objetivo es registrar informacion relevante de cada ejecucion (por ejemplo el origen de una solicitud o el resultado de una validacion) para facilitar su busqueda y analisis posterior, complementando la notificacion a Slack o el registro en Airtable.

Estructura

El primer workflow se dispara con un Slack Trigger, guarda datos relevantes de la interaccion mediante el nodo Execution Data y responde al usuario con nodos Slack. El segundo workflow recibe una solicitud por Webhook, organiza los datos con un nodo Set, los guarda en el nodo Execution Data, evalua una condicion con un nodo If y registra la informacion en Airtable.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow deseado en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de Slack o del Webhook segun el workflow. Paso 3: Ajustar los campos que se desean guardar en el nodo Execution Data para adaptarlos a la informacion relevante del proceso. Paso 4: Para el segundo workflow, configurar tambien las credenciales de Airtable. Paso 5: Ejecutar el workflow y revisar en el historial de ejecuciones de n8n que los datos personalizados quedan guardados junto con cada ejecucion.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
1754_Executiondata_Slack_Automate_Webhook.json | Slack Interaction with Execution Data Logging | Registra datos personalizados en el historial de ejecuciones a partir de una interaccion con un bot de Slack.
1972_Executiondata_Stickynote_Automation_Webhook.json | Webhook to Execution Data and Airtable Logging | Guarda datos de una solicitud Webhook en el historial de ejecuciones y los registra en Airtable.
