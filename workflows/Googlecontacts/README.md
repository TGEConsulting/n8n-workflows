# Workflows de Google Contacts

## Objetivo

Esta carpeta agrupa workflows de n8n que se integran con Google Contacts para revisar periodicamente la lista de contactos y notificar a traves de Slack cuando se cumplen determinadas condiciones. El objetivo es evitar la revision manual de la agenda de contactos y mantener al equipo informado automaticamente.

## Estructura

El workflow parte de un Schedule Trigger que activa el nodo Google Contacts para obtener la lista de contactos, un nodo Filter y un nodo If evaluan la informacion recibida, y el resultado se envia como notificacion a Slack. Un nodo Stop And Error detiene la ejecucion ante fallos y los nodos Sticky Note documentan el flujo.

## Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de Google Contacts y de Slack. Paso 3: Ajustar los criterios de filtrado y la condicion evaluada por el nodo If segun las necesidades del equipo. Paso 4: Activar el workflow y configurar la periodicidad del Schedule Trigger. Paso 5: Verificar en el historial de ejecuciones de n8n que los contactos se revisan y las notificaciones se envian correctamente a Slack.

## Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
1239_Googlecontacts_Schedule_Send_Scheduled.json | Schedule Send Scheduled | Revisa periodicamente los contactos de Google, filtra la informacion relevante y envia notificaciones a Slack.
