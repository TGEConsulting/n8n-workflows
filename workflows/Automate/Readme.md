# Workflows de Automate

## Objetivo
Esta carpeta agrupa workflows genericos de n8n bajo el nombre "Automate", que no corresponden a una integracion externa especifica sino que funcionan como plantillas base, pruebas de concepto y esqueletos reutilizables para construir nuevas automatizaciones. Incluye desde un chatbot funcional para la gestion de pedidos hasta flujos minimos pensados como punto de partida.

## Estructura
Se identifican tres patrones distintos: un flujo completo de chatbot con agente de IA que consulta y gestiona pedidos usando una hoja de calculo como fuente de datos; un flujo de prueba que aplica una funcion personalizada sobre datos simulados (mock data) con manejo de errores; y tres flujos minimos identicos compuestos unicamente por un disparador manual y un manejador de errores, pensados como plantilla base para nuevos workflows. Todos incluyen un Manual Trigger como punto de entrada, salvo el chatbot, que ademas incorpora un disparador de chat.

## Metodo de aplicacion
Paso 1: Revisar el nombre y el contenido de cada archivo para identificar si se trata del chatbot de pedidos, el flujo de prueba con Function, o una de las plantillas minimas.
Paso 2: Importar el archivo JSON elegido en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows.
Paso 3: En el caso del chatbot, configurar las credenciales de OpenAI para el modelo de chat y las credenciales de la hoja de calculo (u origen de datos equivalente) usada para consultar productos y pedidos.
Paso 4: En el caso del flujo de Function, revisar y adaptar el codigo del nodo Function segun la logica que se necesite aplicar sobre los datos simulados.
Paso 5: Activar el workflow y probarlo ejecutando el disparador manual (o enviando un mensaje de chat en el caso del chatbot), verificando el resultado en el historial de ejecuciones de n8n.

## Workflows incluidos
| Archivo | Nombre del workflow | Descripcion |
|---|---|---|
| 1060_Automate_Webhook.json | POC - Chatbot Order by Sheet Data | Chatbot con agente de IA (OpenAI) y memoria de conversacion que consulta productos y gestiona pedidos a partir de datos almacenados en una hoja de calculo. |
| 1123_Automate.json | Function Workflow | Flujo de prueba que genera datos simulados (Mock Data) y les aplica una transformacion personalizada mediante un nodo Function, con manejo de errores. |
| 1271_Automate.json | Unnamed Workflow | Plantilla minima compuesta por un disparador manual y un manejador de errores, pensada como punto de partida para nuevos workflows. |
| 1326_Automate.json | Unnamed Workflow | Plantilla minima identica a la anterior, compuesta por un disparador manual y un manejador de errores. |
| 1911_Automate.json | Unnamed Workflow | Plantilla minima identica a la anterior, compuesta por un disparador manual y un manejador de errores. |
