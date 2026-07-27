Workflows de Cron

Objetivo

Esta carpeta agrupa los workflows de n8n que utilizan el nodo Cron para ejecutar tareas de forma periodica. El objetivo de este workflow es ingresar datos de manera programada en una base de datos Postgres, transformandolos previamente con un nodo Function, evitando la carga manual y repetitiva de informacion.

Estructura

El workflow de esta carpeta se dispara mediante un nodo Cron configurado con una expresion horaria especifica. Un nodo Function procesa o genera los datos que se desean insertar, y el nodo Postgres los inserta en la base de datos de destino. El nodo Error Handler (Stop And Error) detiene la ejecucion de forma controlada ante fallos inesperados.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de Postgres, indicando la base de datos y la tabla de destino. Paso 3: Revisar y adaptar el codigo del nodo Function a la estructura de datos que se desea insertar. Paso 4: Ajustar la expresion del nodo Cron segun la frecuencia con la que se debe ejecutar la ingesta de datos. Paso 5: Activar el workflow y verificar en el historial de ejecuciones de n8n que los datos se insertan correctamente en Postgres.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0822_Cron_Postgres_Automation_Scheduled.json | Postgres Data Ingestion | Ejecuta de forma programada la insercion de datos transformados en una base de datos Postgres.
