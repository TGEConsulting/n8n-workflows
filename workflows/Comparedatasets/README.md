Workflows de Compare Datasets

Objetivo

Esta carpeta agrupa un workflow de n8n que utiliza el nodo Compare Datasets para identificar diferencias entre dos conjuntos de datos. El objetivo de este workflow es sincronizar una lista de canciones obtenida de YouTube con una playlist de Spotify, anadiendo unicamente las canciones que todavia no estan presentes en la playlist, evitando duplicados y el trabajo manual de comparacion.

Estructura

El workflow parte de un Manual Trigger y obtiene por un lado las canciones de una lista de YouTube y por otro las canciones que ya existen en la playlist de Spotify. El nodo Compare Datasets contrasta ambos conjuntos para determinar que canciones son nuevas. Las canciones nuevas se buscan en Spotify mediante el nodo Spotify para obtener su identificador exacto, se procesan una a una con un nodo Loop Over Items (Split In Batches) y finalmente se anaden a la playlist de Spotify. El nodo Error Handler (Stop And Error) detiene la ejecucion de forma controlada ante fallos inesperados.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de YouTube para acceder a la lista o playlist de origen. Paso 3: Configurar las credenciales de Spotify e indicar la playlist de destino donde se anadiran las canciones nuevas. Paso 4: Ejecutar el workflow manualmente y revisar el resultado del nodo Compare Datasets para confirmar que solo se detectan las canciones nuevas. Paso 5: Verificar en el historial de ejecuciones de n8n que las canciones nuevas se anaden correctamente a la playlist de Spotify.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0623_Comparedatasets_Manual_Create_Triggered.json | YouTube to Spotify Playlist Sync | Compara una lista de YouTube con una playlist de Spotify y anade unicamente las canciones nuevas a la playlist.
