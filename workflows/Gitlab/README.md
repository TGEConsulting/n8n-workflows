# Workflows de GitLab

## Objetivo

Esta carpeta agrupa workflows de n8n que se integran con GitLab para automatizar la vigilancia de repositorios, el procesamiento de archivos de codigo y el envio de notificaciones por correo, conectando la plataforma con servicios como Gmail o llamadas HTTP. El objetivo es evitar la revision manual de eventos y archivos dentro de los proyectos de GitLab.

## Estructura

Algunos workflows utilizan GitLab Trigger para reaccionar a eventos del repositorio, mientras que otros parten de un disparador Manual o Schedule Trigger para procesar archivos con nodos como Code, Extract From File o Filter. Nodos como If, Switch y Aggregate evaluan y agrupan la informacion antes de continuar hacia GitLab, Gmail o HTTP Request, y un nodo Stop And Error detiene el flujo ante fallos.

## Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de GitLab y de los servicios adicionales integrados (Gmail, HTTP, etc.). Paso 3: Ajustar el proyecto de GitLab y los eventos o archivos que debe procesar el workflow. Paso 4: Activar el workflow o configurar el disparador (GitLab Trigger, Schedule) segun el modo de ejecucion deseado. Paso 5: Verificar en el historial de ejecuciones de n8n que los datos se procesan y las notificaciones se envian correctamente.

## Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0557_Gitlab_Filter_Create_Scheduled.json | Filter Create Scheduled | Filtra y agrega periodicamente informacion de GitLab usando Filter, Aggregate e If, con disparo manual o programado.
0561_Gitlab_Code_Create_Triggered.json | Code Create Triggered | Procesa archivos de GitLab en lotes con Split In Batches, Code y Extract From File, evaluando el resultado con Switch.
0998_Gitlab_Automate_Triggered.json | Automate Triggered | Flujo base que escucha eventos de GitLab mediante GitLab Trigger y detiene la ejecucion ante errores.
1895_Gitlab_Code_Automation_Webhook.json | Code Automation Webhook | Reacciona a eventos de GitLab, transforma datos con Code y envia notificaciones por Gmail segun condiciones evaluadas con If.
