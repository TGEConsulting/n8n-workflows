# Workflows de GetResponse

## Objetivo

Esta carpeta agrupa workflows de n8n que se integran con GetResponse para reaccionar automaticamente a eventos de la plataforma de email marketing, como la suscripcion de un nuevo contacto, sincronizando esa informacion con otros sistemas. El objetivo es evitar el traspaso manual de contactos entre GetResponse y herramientas como Airtable.

## Estructura

El workflow utiliza el nodo GetResponse Trigger para escuchar eventos de la cuenta de GetResponse, un nodo Set para dar forma a los datos recibidos y un nodo Airtable para crear o actualizar el registro correspondiente. Un nodo Stop And Error se encarga de detener la ejecucion y reportar errores en caso de que falle la importacion.

## Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de GetResponse y de Airtable en los nodos correspondientes. Paso 3: Seleccionar la base y tabla de Airtable donde se importaran los contactos. Paso 4: Activar el workflow para que el trigger de GetResponse quede escuchando eventos en tiempo real. Paso 5: Verificar en el historial de ejecuciones de n8n que los nuevos contactos se importan correctamente en Airtable.

## Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
1202_Getresponse_Airtable_Import_Triggered.json | Airtable Import Triggered | Escucha eventos de GetResponse y crea los registros correspondientes en Airtable, con manejo de errores.
