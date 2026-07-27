# Workflows de Gmail Tool

## Objetivo

Esta carpeta agrupa workflows de n8n que utilizan el nodo Gmail Tool, es decir, Gmail expuesto como herramienta dentro de agentes de IA u otros flujos automatizados, para que un agente pueda leer o enviar correos como parte de sus acciones. El objetivo es permitir que procesos automatizados o agentes conversacionales interactuen con Gmail sin intervencion manual.

## Estructura

Los workflows combinan el nodo Gmail Tool con disparadores muy variados (Webhook, Execute Workflow Trigger, Notion Trigger o Manual), y con otras herramientas como Google Calendar Tool, Airtable, WordPress Tool o clientes MCP, permitiendo que un agente decida cuando usar Gmail dentro de una cadena de acciones. Nodos como Set y No Operation preparan o finalizan el flujo, y un nodo Stop And Error detiene la ejecucion ante fallos.

## Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de Gmail y de los demas servicios integrados como herramientas (Google Calendar, Airtable, WordPress, MCP, etc.). Paso 3: Revisar la configuracion del agente o del disparador (Webhook, Notion Trigger, Manual) que activa el uso de la herramienta Gmail. Paso 4: Activar el workflow segun el modo de ejecucion correspondiente. Paso 5: Verificar en el historial de ejecuciones de n8n que el agente utiliza correctamente la herramienta Gmail para leer o enviar correos.

## Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0677_Gmailtool_Splitout_Create_Webhook.json | Splitout Create Webhook | Recibe datos por webhook, los divide con Split Out y permite que un agente use Gmail y Google Calendar como herramientas.
1142_Gmailtool_Stickynote_Automation_Triggered.json | Stickynote Automation Triggered | Agente disparado por Notion que usa Gmail, WordPress y MCP como herramientas para automatizar tareas.
1248_Gmailtool_Splitout_Automation_Webhook.json | Splitout Automation Webhook | Variante que procesa datos por webhook con Split Out y expone Gmail como herramienta de automatizacion.
1613_Gmailtool_Stickynote_Automation_Triggered.json | Stickynote Automation Triggered (variante) | Variante del agente disparado por Notion que utiliza Gmail como herramienta.
1795_Gmailtool_Executeworkflow_Send_Triggered.json | Executeworkflow Send Triggered | Ejecutado como sub-workflow, utiliza Gmail Tool para enviar correos dentro de un flujo mayor.
1909_Gmailtool_Automation_Triggered.json | Automation Triggered | Flujo disparado manualmente que expone Gmail como herramienta basica de automatizacion.
