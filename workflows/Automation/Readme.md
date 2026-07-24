# Workflows de Automation

## Objetivo
Esta carpeta agrupa workflows genericos de n8n bajo el nombre "Automation", que al igual que la carpeta Automate no corresponden a una integracion externa especifica sino que sirven como plantillas base y pruebas de concepto para nuevas automatizaciones. Incluye un agente conversacional de IA con capacidad de busqueda en internet junto con varias plantillas minimas reutilizables.

## Estructura
Se identifican dos patrones: un flujo de agente de IA que combina un modelo de chat de OpenAI, memoria de conversacion y la herramienta SerpAPI para responder preguntas realizando busquedas en internet; y cinco flujos minimos identicos compuestos unicamente por un disparador manual y un manejador de errores, pensados como plantilla base para nuevos workflows.

## Metodo de aplicacion
Paso 1: Revisar el nombre y el contenido de cada archivo para identificar si se trata del agente de IA con busqueda o de una de las plantillas minimas.
Paso 2: Importar el archivo JSON elegido en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows.
Paso 3: En el caso del agente de IA, configurar las credenciales de OpenAI para el modelo de chat y las credenciales de SerpAPI para habilitar la busqueda en internet.
Paso 4: En el caso de las plantillas minimas, adaptar el flujo agregando los nodos necesarios segun la automatizacion que se desee construir.
Paso 5: Activar el workflow y probarlo ejecutando el disparador manual (o enviando un mensaje de chat en el caso del agente de IA), verificando el resultado en el historial de ejecuciones de n8n.

## Workflows incluidos
| Archivo | Nombre del workflow | Descripcion |
|---|---|---|
| 1250_Automation.json | Unnamed Workflow | Plantilla minima compuesta por un disparador manual y un manejador de errores, pensada como punto de partida para nuevos workflows. |
| 1265_Automation_Triggered.json | Lmchatopenai Workflow | Agente de IA conversacional que utiliza un modelo de chat de OpenAI, memoria de conversacion y la herramienta SerpAPI para responder consultas realizando busquedas en internet. |
| 1290_Automation.json | Unnamed Workflow | Plantilla minima identica a la anterior, compuesta por un disparador manual y un manejador de errores. |
| 1497_Automation.json | Unnamed Workflow | Plantilla minima identica a la anterior, compuesta por un disparador manual y un manejador de errores. |
| 1634_Automation.json | Unnamed Workflow | Plantilla minima identica a la anterior, compuesta por un disparador manual y un manejador de errores. |
| 2047_Automation.json | Unnamed Workflow | Plantilla minima identica a la anterior, compuesta por un disparador manual y un manejador de errores. |
