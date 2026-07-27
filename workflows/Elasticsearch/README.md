Workflows de Elasticsearch

Objetivo

Esta carpeta agrupa los workflows de n8n que se integran con Elasticsearch, el motor de busqueda y analisis de datos. El objetivo de este workflow es monitorear periodicamente un indice de Elasticsearch y crear automaticamente un elemento de trabajo (work item) cuando los resultados de la consulta superan un umbral definido, evitando la revision manual de alertas.

Estructura

El workflow de esta carpeta se dispara mediante un nodo Cron programado. El nodo Elasticsearch ejecuta una consulta sobre el indice configurado y un nodo If (Check for Alerts) evalua si el valor obtenido es mayor que el umbral establecido. Si se cumple la condicion, un nodo HTTP Request crea un elemento de trabajo en el sistema de destino; en caso contrario, el flujo finaliza sin realizar ninguna accion (No Operation).

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de Elasticsearch y la consulta que se desea ejecutar sobre el indice correspondiente. Paso 3: Ajustar el umbral de comparacion en el nodo If segun el criterio de alerta deseado. Paso 4: Configurar el nodo HTTP Request con la URL y las credenciales del sistema donde se creara el elemento de trabajo. Paso 5: Activar el workflow y verificar en el historial de ejecuciones de n8n que las alertas se detectan y los elementos de trabajo se crean correctamente.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0616_Elasticsearch_Cron_Create_Webhook.json | Elasticsearch Alert to Work Item | Consulta un indice de Elasticsearch de forma periodica y crea un elemento de trabajo cuando se supera un umbral definido.
