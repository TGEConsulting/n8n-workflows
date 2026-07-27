Workflows de Baserow

Objetivo

Esta carpeta agrupa los workflows de n8n que se integran con Baserow, la plataforma de bases de datos colaborativas tipo hoja de calculo. El objetivo de este workflow es convertir automaticamente contenido en formato markdown a HTML dentro de los registros de Baserow, ya sea para un registro individual o para todos los registros de una tabla, evitando la conversion manual del formato.

Estructura

El workflow de esta carpeta se dispara mediante un nodo Webhook. Un nodo If (Check if it's 1 record or all records) determina si la solicitud corresponde a un unico registro o a todos los registros de la tabla. Segun el resultado, se obtiene el registro correspondiente con un nodo Baserow (Get single record o Get all records), se convierte el contenido markdown a HTML con un nodo Markdown y finalmente se actualiza el registro o los registros en Baserow mediante un nodo Baserow con la operacion update. Un nodo Sticky Note documenta el proposito del flujo dentro del propio editor.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de Baserow Cloud en los nodos correspondientes, indicando la base y la tabla que se desea sincronizar. Paso 3: Activar el workflow para que n8n exponga la URL del Webhook. Paso 4: Enviar una solicitud al Webhook indicando si se desea procesar un registro individual o todos los registros de la tabla. Paso 5: Verificar en el historial de ejecuciones de n8n que el contenido markdown se convierte a HTML y se actualiza correctamente en Baserow.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
1822_Baserow_Stickynote_Automation_Webhook.json | Baserow Markdown to HTML Sync | Convierte el contenido markdown de uno o varios registros de Baserow a HTML y actualiza los registros mediante un Webhook.
