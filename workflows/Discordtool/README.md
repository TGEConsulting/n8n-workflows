Workflows de Discord Tool

Objetivo

Esta carpeta agrupa los workflows de n8n que utilizan el nodo Discord Tool para exponer acciones de Discord como herramientas invocables por un agente de IA. El objetivo es permitir que un asistente conversacional interactue con un servidor de Discord (por ejemplo enviando mensajes o gestionando canales) como parte de sus capacidades, en lugar de usar el nodo Discord de forma aislada en un flujo lineal.

Estructura

El primer workflow define un Discord Agent que puede ejecutarse como sub-workflow desde otro flujo (Execute Workflow Trigger) o mediante un Chat Trigger; un AI Agent con modelo OpenAI Chat Model y memoria de buffer (Window Buffer Memory) tiene disponibles varios nodos Discord Tool para realizar acciones en el servidor segun la tarea recibida. El segundo workflow amplia este concepto con un conjunto mas amplio de nodos Discord Tool (envio de mensajes, gestion de canales y otras acciones) junto con un HTTP Request Tool adicional, disponibles para que un agente los use segun la instruccion del usuario. Ambos workflows incluyen nodos Sticky Note que documentan cada seccion y un nodo Error Handler (Stop And Error) para el manejo de fallos.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow deseado en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales del bot o Webhook de Discord en cada nodo Discord Tool, indicando el servidor y los canales sobre los que el agente podra actuar. Paso 3: Configurar las credenciales de OpenAI para el nodo AI Agent. Paso 4: Activar el Chat Trigger o invocar el workflow desde otro flujo, segun corresponda. Paso 5: Enviar una instruccion de prueba al agente y verificar en el historial de ejecuciones de n8n que las herramientas de Discord se invocan correctamente.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
1242_Discordtool_Stickynote_Automation_Triggered.json | Discord Agent | Agente de IA con memoria que utiliza herramientas de Discord para actuar sobre un servidor, invocable como sub-workflow o por chat.
1913_Discordtool_Stickynote_Automation_Webhook.json | Discord Agent Toolkit (ampliado) | Conjunto ampliado de herramientas de Discord y HTTP disponibles para que un agente de IA gestione un servidor de Discord.
