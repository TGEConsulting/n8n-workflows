Workflows de Beeminder

Objetivo

Esta carpeta agrupa los workflows de n8n que se integran con Beeminder, la herramienta de seguimiento de objetivos personales mediante compromisos cuantificables. El objetivo de este workflow es registrar automaticamente un punto de datos (datapoint) en Beeminder cada vez que se registra una nueva actividad en Strava, evitando el registro manual del progreso hacia la meta.

Estructura

El workflow de esta carpeta sigue un patron de disparador mas manejo de errores. El nodo Strava Trigger escucha en tiempo real la creacion de nuevas actividades en la cuenta de Strava del usuario. Cuando se detecta una nueva actividad, el nodo Beeminder crea un datapoint en la meta configurada para reflejar el progreso alcanzado. El nodo Error Handler (Stop And Error) detiene la ejecucion de forma controlada si el flujo llega a un estado no esperado.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de Strava en el nodo Strava Trigger para escuchar las nuevas actividades. Paso 3: Configurar las credenciales de Beeminder (usuario y token de API) en el nodo Beeminder, indicando la meta a la que se anadira el datapoint. Paso 4: Activar el workflow para que n8n registre la suscripcion a los eventos de Strava. Paso 5: Registrar una actividad de prueba en Strava y verificar en el historial de ejecuciones de n8n que el datapoint se crea correctamente en Beeminder.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0403_Beeminder_Strava_Create_Triggered.json | Strava to Beeminder Datapoint Automation | Anade un datapoint en Beeminder automaticamente cada vez que se registra una nueva actividad en Strava.
