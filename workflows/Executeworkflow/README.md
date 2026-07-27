Workflows de Execute Workflow

Objetivo

Esta carpeta agrupa los workflows de n8n que utilizan el nodo Execute Workflow Trigger para funcionar como sub-workflows reutilizables, invocados desde otros flujos principales. El objetivo es modularizar tareas comunes (resumir datos, consultar Hacker News, notificar por Slack, gestionar Google Drive o Airtable, ejecutar comandos del sistema) para que puedan reutilizarse desde distintos workflows sin duplicar logica.

Estructura

Cada workflow de esta carpeta se dispara mediante un Execute Workflow Trigger, que recibe los datos de entrada del workflow que lo invoca. Segun el sub-workflow, la logica interna resume texto con el nodo Summarize, consulta noticias de Hacker News, envia mensajes a Slack de forma condicional, gestiona archivos y carpetas en Google Drive, expone herramientas de Airtable o de ejecucion de comandos del sistema para un agente de IA, o implementa un bot de Telegram con menus (Switch) que a su vez invoca otros sub-workflows. Todos incluyen un nodo Error Handler (Stop And Error) para el manejo de fallos.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del sub-workflow deseado en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de las aplicaciones externas que utilice el sub-workflow (Slack, Google Drive, Airtable, Telegram, Google Sheets, segun corresponda). Paso 3: Desde el workflow principal, anadir un nodo Execute Workflow que apunte a este sub-workflow y mapear los datos de entrada necesarios. Paso 4: Ejecutar el workflow principal para invocar el sub-workflow. Paso 5: Verificar en el historial de ejecuciones de n8n que el sub-workflow recibe los datos correctamente y produce el resultado esperado.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0371_Executeworkflow_Summarize_Send_Triggered.json | Data Summarization Sub-workflow | Resume datos recibidos utilizando el nodo Summarize y devuelve el resultado al workflow que lo invoca.
0372_Executeworkflow_Hackernews_Create_Triggered.json | Hacker News Fetch Sub-workflow | Consulta noticias de Hacker News y formatea los resultados para el workflow que lo invoca.
0406_Executeworkflow_Slack_Send_Triggered.json | Slack Notification Sub-workflow | Envia un mensaje a Slack de forma condicional segun los datos recibidos.
0569_Executeworkflow_Telegram_Update_Triggered.json | Telegram Bot with Menu and Sub-workflows | Implementa un bot de Telegram con menus mediante nodos Switch, integrado con Google Sheets e invocando otros sub-workflows.
0872_Executeworkflow_Executecommandtool_Create_Triggered.json | System Command Tool for AI Agent | Expone herramientas de ejecucion de comandos del sistema para que un agente de IA las utilice.
0947_Executeworkflow_Stickynote_Automate_Triggered.json | Google Drive File Management Sub-workflow | Busca, crea o gestiona archivos y carpetas en Google Drive segun los datos recibidos.
1793_Executeworkflow_Airtabletool_Automation_Triggered.json | Airtable Tool for AI Agent | Expone operaciones de Airtable como herramienta para que un agente de IA las utilice.
1794_Executeworkflow_Automation_Webhook.json | Generic Sub-workflow Template | Plantilla generica de sub-workflow que procesa datos de entrada mediante nodos Set.
1918_Executeworkflow_Automation_Triggered.json | Numeric Routing Sub-workflow | Procesa y enruta datos numericos recibidos mediante nodos If y Switch.
