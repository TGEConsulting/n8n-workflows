# Workflows de Google Analytics

## Objetivo

Esta carpeta agrupa workflows de n8n que extraen metricas de Google Analytics de forma periodica o manual, las procesan con codigo personalizado y las envian a otros sistemas como Baserow o Gmail. El objetivo es automatizar la generacion de reportes de analitica web sin necesidad de revisar el panel manualmente.

## Estructura

Cada workflow parte de un disparador Schedule Trigger o Manual Trigger que activa el nodo Google Analytics para obtener los datos de trafico o eventos. Un nodo Code transforma y da formato a la informacion recibida, y el flujo continua hacia HTTP Request y Baserow para almacenar los resultados, o hacia Gmail para enviar un reporte por correo. Los nodos Sticky Note documentan el proposito de cada seccion del flujo.

## Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de Google Analytics y de los servicios de destino (Baserow, Gmail, etc.). Paso 3: Ajustar la vista o propiedad de Google Analytics de la que se deben extraer los datos. Paso 4: Activar el workflow o configurar la periodicidad del Schedule Trigger segun la frecuencia de reporte deseada. Paso 5: Verificar en el historial de ejecuciones de n8n que las metricas se extraen y se almacenan o envian correctamente.

## Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0475_Googleanalytics_Code_Automate_Scheduled.json | Code Automate Scheduled | Extrae metricas de Google Analytics de forma programada o manual, las transforma con Code y envia un reporte por Gmail.
1480_Googleanalytics_Code_Automation_Webhook.json | Code Automation Webhook | Extrae datos de Google Analytics, los procesa con Code y los guarda en Baserow mediante HTTP Request.
1529_Googleanalytics_Code_Automation_Webhook.json | Code Automation Webhook (variante) | Variante del flujo de extraccion de Google Analytics con almacenamiento en Baserow.
1652_Googleanalytics_Code_Automation_Webhook.json | Code Automation Webhook (variante) | Otra variante del mismo patron de extraccion de Google Analytics y almacenamiento en Baserow.
