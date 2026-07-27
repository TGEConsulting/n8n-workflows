Workflows de Code

Objetivo

Esta carpeta agrupa un numero muy amplio (mas de 180) de workflows de n8n cuyo elemento comun es el uso del nodo Code para ejecutar logica personalizada en JavaScript dentro del flujo. A diferencia de otras carpetas organizadas por un unico servicio externo, aqui los workflows cubren una gran variedad de disparadores e integraciones (Webhook, Schedule, formularios, Slack, GitHub, Google Calendar, Todoist, Discord, Strava, Pipedrive, edicion de imagenes, extraccion de archivos, Postgres, entre muchos otros), unidos por la necesidad de transformar, filtrar o calcular datos con codigo a medida en algun punto del flujo.

Estructura

Cada workflow de esta carpeta combina un disparador especifico (indicado en el nombre del archivo, por ejemplo Webhook, Schedule, Manual o el nombre de una aplicacion como Slack, GitHub o Strava) con uno o mas nodos Code que contienen la logica de negocio particular de ese flujo: desde limpiar y normalizar datos, hasta calcular fechas, generar identificadores o preparar el payload para el siguiente nodo. Muchos de estos workflows tambien incorporan nodos adicionales propios de la aplicacion referenciada en el nombre (por ejemplo Spotify, NocoDB, Postgres o Editimage) para completar la automatizacion, y con frecuencia incluyen un nodo Error Handler (Stop And Error) para el manejo de fallos.

Metodo de aplicacion

Paso 1: Localizar el archivo JSON del workflow especifico que se desea usar segun su nombre, que indica el disparador y, cuando aplica, la aplicacion externa involucrada. Paso 2: Importar el archivo en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 3: Revisar y adaptar el codigo del nodo o los nodos Code a las necesidades especificas del caso de uso, ya que la logica esta escrita a medida para cada flujo. Paso 4: Configurar las credenciales de las aplicaciones externas que utilice el workflow (por ejemplo Slack, GitHub, Google Calendar o Postgres). Paso 5: Activar o ejecutar el workflow segun su tipo de disparador y verificar en el historial de ejecuciones de n8n que la logica personalizada produce el resultado esperado.

Workflows incluidos

Esta carpeta contiene mas de 180 archivos de workflow, cada uno con un proposito especifico que combina el nodo Code con un disparador y, en muchos casos, una aplicacion externa distinta (por ejemplo 0034_Code_Filter_Create_Scheduled.json sincroniza playlists mensuales entre Spotify y NocoDB, 0182_Code_GitHub_Create_Scheduled.json automatiza tareas periodicas sobre GitHub, y 1819_Code_Discord_Send_Triggered.json envia mensajes a Discord). Dado el volumen y la diversidad de estos archivos, se recomienda abrir cada JSON individualmente en n8n para revisar su disparador, sus nodos Code y su proposito concreto antes de utilizarlo.
