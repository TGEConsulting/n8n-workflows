# Workflows de Google Calendar Tool

## Objetivo

Esta carpeta agrupa workflows de n8n que utilizan el nodo Google Calendar Tool, es decir, Google Calendar expuesto como herramienta dentro de agentes de IA u otros flujos automatizados, para que un agente pueda consultar o gestionar eventos como parte de sus acciones. El objetivo es permitir que procesos automatizados o agentes conversacionales interactuen con la agenda sin intervencion manual.

## Estructura

Los workflows combinan el nodo Google Calendar Tool con disparadores Manual o Execute Workflow Trigger, dejando que el agente decida cuando consultar o modificar el calendario dentro de una cadena de acciones. Nodos como Set y No Operation preparan o finalizan el flujo, y un nodo Stop And Error detiene la ejecucion ante fallos.

## Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de Google Calendar para que puedan ser utilizadas por la herramienta. Paso 3: Revisar la configuracion del agente o del disparador (Manual, Execute Workflow) que activa el uso de la herramienta Google Calendar. Paso 4: Activar el workflow o invocarlo desde otro workflow segun corresponda. Paso 5: Verificar en el historial de ejecuciones de n8n que el agente utiliza correctamente la herramienta Google Calendar.

## Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
1071_Googlecalendartool_Stickynote_Create_Triggered.json | Stickynote Create Triggered | Flujo disparado manualmente que expone Google Calendar como herramienta basica de consulta o creacion de eventos.
1247_Googlecalendartool_Stickynote_Automation_Triggered.json | Stickynote Automation Triggered | Variante que automatiza el uso de Google Calendar como herramienta dentro de un agente.
1792_Googlecalendartool_Executeworkflow_Automation_Triggered.json | Executeworkflow Automation Triggered | Ejecutado como sub-workflow, expone Google Calendar como herramienta para otros flujos.
1872_Googlecalendartool_Automation_Triggered.json | Automation Triggered | Flujo disparado manualmente que utiliza Google Calendar como herramienta de automatizacion.
1928_Googlecalendartool_Stickynote_Automation_Triggered.json | Stickynote Automation Triggered (variante) | Otra variante del agente que utiliza Google Calendar como herramienta.
