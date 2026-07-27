# Workflows de GitHub

## Objetivo

Esta carpeta agrupa workflows de n8n que se integran con GitHub para automatizar tareas relacionadas con repositorios, issues, pull requests y notificaciones, conectando la plataforma con herramientas como Slack, Notion, GitLab o servicios via HTTP Request. El objetivo es reducir el trabajo manual de vigilancia y sincronizacion sobre la actividad de los repositorios.

## Estructura

La mayoria de los workflows utiliza el nodo GitHub Trigger para reaccionar a eventos del repositorio (issues, pull requests, estrellas, etc.), aunque tambien hay variantes disparadas por Cron o de forma Manual. Tras el disparador, nodos como If, Switch o Function evaluan y transforman la informacion recibida, y el flujo continua hacia nodos de integracion como GitHub, Slack, Notion, GitLab, Aggregate o HTTP Request. Un nodo Stop And Error se encarga de detener la ejecucion y reportar fallos.

## Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de GitHub y de los demas servicios integrados (Slack, Notion, GitLab, etc.) segun corresponda. Paso 3: Ajustar el repositorio y los eventos que debe escuchar el GitHub Trigger, o el disparador Cron/Manual segun el workflow. Paso 4: Activar el workflow para que quede escuchando eventos o ejecutandose de forma programada. Paso 5: Verificar en el historial de ejecuciones de n8n que las acciones sobre GitHub y los servicios integrados se completan correctamente.

## Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0135_GitHub_Cron_Create_Scheduled.json | Cron Create Scheduled | Compara periodicamente informacion entre GitHub y GitLab mediante Cron, Merge y Function, deteniendo el flujo si hay errores.
0264_GitHub_Stickynote_Create_Triggered.json | Stickynote Create Triggered | Reacciona a eventos de GitHub y crea o actualiza paginas en Notion segun condiciones evaluadas con Switch e If.
0289_GitHub_Stickynote_Update_Triggered.json | Stickynote Update Triggered | Variante que actualiza contenido en Notion a partir de eventos de GitHub.
0876_GitHub_Aggregate_Create_Webhook.json | Aggregate Create Webhook | Ejecutado como sub-workflow, agrega datos con Aggregate y los envia a GitHub mediante HTTP Request.
0973_GitHub_Slack_Create_Triggered.json | Slack Create Triggered | Escucha eventos de GitHub y envia notificaciones a Slack cuando se cumple una condicion evaluada con If.
0997_GitHub_Automate_Triggered.json | Automate Triggered | Flujo base que escucha eventos de GitHub y detiene la ejecucion ante errores.
1068_GitHub_Slack_Automation_Triggered.json | Slack Automation Triggered | Envia notificaciones a Slack en respuesta a eventos de GitHub.
1149_GitHub_Manual_Create_Scheduled.json | Manual Create Scheduled | Sincroniza datos con GitHub en lotes usando Split In Batches, con disparo manual o programado por Cron.
1988_GitHub_Manual_Automate_Triggered.json | Manual Automate Triggered | Automatiza acciones sobre GitHub combinando disparo manual, condiciones If y ejecucion de otros workflows de n8n.
