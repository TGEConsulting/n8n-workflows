# Workflows de Airtable

## Objetivo
Esta carpeta agrupa workflows de n8n que utilizan Airtable como base de datos central para almacenar, leer o actualizar informacion dentro de distintos procesos automatizados: captura de datos manuales, procesamiento de documentos, aprendizaje de idiomas y envio de campanas de outreach.

## Estructura
Cada workflow combina el nodo Airtable con un disparador y, en algunos casos, con otras integraciones de valor agregado. Los patrones encontrados son: disparo manual mas escritura en Airtable, webhook mas extraccion de datos de un documento mas guardado en Airtable, ejecucion programada mas consulta a una fuente externa mas traduccion mas guardado en Airtable mas envio de SMS, y disparo manual mas lectura de Airtable mas envio a una plataforma de email outreach. La mayoria incluye un nodo Error Handler (Stop And Error) para detener la ejecucion ante estados inesperados.

## Metodo de aplicacion
Paso 1: Revisar el nombre de cada archivo para identificar el disparador y las integraciones adicionales que utiliza antes de importarlo.
Paso 2: Importar el archivo JSON elegido en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows.
Paso 3: Configurar las credenciales de Airtable (API Key o token de acceso personal) y las de las demas integraciones que use ese workflow especifico (por ejemplo Mindee, Vonage o Lemlist).
Paso 4: Ajustar en el nodo Airtable la base y la tabla de destino segun tu propia estructura de datos.
Paso 5: Activar el workflow y probarlo generando el evento correspondiente, verificando en el historial de ejecuciones de n8n que los registros se creen o actualicen correctamente en Airtable.

## Workflows incluidos
| Archivo | Disparador principal | Descripcion |
|---|---|---|
| 0756_Airtable_Create_Triggered.json | Manual Trigger | Flujo de prueba manual que prepara un set de datos y crea un registro en Airtable. |
| 1120_Airtable_Mindee_Automate_Webhook.json | Webhook | Recibe un documento via webhook, usa Mindee para extraer los datos del documento (por ejemplo una factura) y guarda la informacion en Airtable. |
| 1138_Airtable_Vonage_Automation_Scheduled.json | Schedule (Cron) | Se ejecuta diariamente, obtiene articulos de Hacker News, los traduce con LingvaNex, guarda el resultado en Airtable y lo envia por SMS mediante Vonage. |
| 1220_Airtable_Lemlist_Automate.json | Manual Trigger | Lee contactos o registros desde Airtable y los envia a una campana de Lemlist para outreach por correo. |
