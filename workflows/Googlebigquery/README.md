# Workflows de Google BigQuery

## Objetivo

Esta carpeta agrupa workflows de n8n que se integran con Google BigQuery para automatizar la consulta o carga de datos en el almacen de datos, permitiendo que sean utilizados como parte de flujos mayores. El objetivo es evitar la ejecucion manual de consultas SQL y facilitar la reutilizacion de esta logica en otros workflows.

## Estructura

El workflow se ejecuta como sub-workflow mediante un Execute Workflow Trigger, procesa los datos de entrada con un nodo Code y utiliza el nodo Google BigQuery para realizar la operacion correspondiente sobre el almacen de datos. Un nodo Stop And Error detiene la ejecucion y reporta fallos, y los nodos Sticky Note documentan el flujo.

## Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de Google BigQuery, incluyendo el proyecto y el dataset a utilizar. Paso 3: Ajustar la consulta o la operacion que debe ejecutar el nodo Google BigQuery segun las necesidades del proyecto. Paso 4: Activar el workflow o invocarlo desde otro workflow mediante Execute Workflow. Paso 5: Verificar en el historial de ejecuciones de n8n que las consultas o cargas de datos en BigQuery se completan correctamente.

## Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0806_Googlebigquery_Stickynote_Automate_Triggered.json | Stickynote Automate Triggered | Ejecutado como sub-workflow, procesa datos con Code y los consulta o carga en Google BigQuery.
