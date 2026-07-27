Workflows de Emelia

Objetivo

Esta carpeta agrupa los workflows de n8n que se integran con Emelia, la plataforma de campanas de correo en frio (cold email) y prospeccion. El objetivo de este workflow es crear una campana y anadir contactos a ella de forma automatizada, evitando la configuracion manual repetitiva de campanas en Emelia.

Estructura

El workflow de esta carpeta parte de un Manual Trigger y encadena varios nodos Emelia: uno crea una nueva campana (operation create) y los siguientes anaden contactos a esa campana (operation addContact). El nodo Error Handler (Stop And Error) detiene la ejecucion de forma controlada ante fallos inesperados.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de Emelia (API Key) en cada nodo Emelia. Paso 3: Ajustar los parametros de la campana a crear (nombre, plantilla) y los datos de los contactos que se desean anadir. Paso 4: Ejecutar el workflow manualmente o sustituir el Manual Trigger por un disparador automatico segun el proceso de negocio. Paso 5: Verificar en el historial de ejecuciones de n8n y en la plataforma de Emelia que la campana y los contactos se crean correctamente.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
1214_Emelia_Automate.json | Emelia Campaign and Contacts Automation | Crea una campana en Emelia y anade contactos a ella de forma automatizada.
