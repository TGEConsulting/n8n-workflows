# Workflows de Gmail

## Objetivo

Esta carpeta agrupa workflows de n8n que se integran con Gmail para automatizar el envio, la lectura y el procesamiento de correos electronicos, conectando la bandeja de entrada con servicios como Google Drive, Google Sheets, Google Calendar u Odoo. El objetivo es evitar la gestion manual de correos y adjuntos, sincronizandolos automaticamente con otras herramientas.

## Estructura

La mayoria de los workflows utiliza el nodo Gmail Trigger para reaccionar a la llegada de nuevos correos, aunque tambien hay variantes con disparo Manual. Segun el caso, el flujo continua hacia nodos como Google Drive o Google Sheets para almacenar adjuntos e informacion, hacia Odoo para sincronizar datos, o utiliza Move Binary Data y Spreadsheet File para procesar archivos adjuntos. Un nodo Stop And Error se encarga de detener la ejecucion y reportar fallos.

## Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de Gmail y de los demas servicios integrados (Google Drive, Google Sheets, Google Calendar, Odoo, etc.). Paso 3: Ajustar los filtros de busqueda de correo o las etiquetas que debe escuchar el Gmail Trigger. Paso 4: Activar el workflow para que quede escuchando nuevos correos en tiempo real. Paso 5: Verificar en el historial de ejecuciones de n8n que los correos y adjuntos se procesan correctamente.

## Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0036_Gmail_GoogleDrive_Import.json | GoogleDrive Import | Envia correos por Gmail e importa archivos relacionados en Google Drive de forma manual.
0221_Gmail_Movebinarydata_Send.json | Movebinarydata Send | Procesa adjuntos de Gmail con Move Binary Data y Spreadsheet File antes de enviarlos.
0319_Gmail_Googlecalendartool_Send_Triggered.json | Googlecalendartool Send Triggered | Reacciona a nuevos correos de Gmail y utiliza Google Calendar como herramienta para gestionar eventos.
0544_Gmail_GoogleDrive_Create_Triggered.json | GoogleDrive Create Triggered | Escucha nuevos correos de Gmail y guarda archivos adjuntos en Google Drive.
0852_Gmail_GoogleSheets_Create_Triggered.json | GoogleSheets Create Triggered | Escucha nuevos correos de Gmail y registra la informacion correspondiente en Google Sheets.
1479_Gmail_Stickynote_Create_Triggered.json | Stickynote Create Triggered | Evalua los correos recibidos con un nodo If y responde o etiqueta mediante Gmail segun la condicion.
1565_Gmail_Stickynote_Create_Triggered.json | Stickynote Create Triggered (Odoo) | Escucha nuevos correos de Gmail y sincroniza la informacion con registros en Odoo.
1914_Gmail_Stickynote_Send_Triggered.json | Stickynote Send Triggered | Escucha nuevos correos de Gmail y envia una respuesta o notificacion automatica por Gmail.
