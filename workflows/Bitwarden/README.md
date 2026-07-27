Workflows de Bitwarden

Objetivo

Esta carpeta agrupa los workflows de n8n que se integran con Bitwarden, el gestor de contrasenas y plataforma de administracion de accesos. El objetivo de este workflow es automatizar la gestion de grupos y miembros dentro de una organizacion de Bitwarden, permitiendo crear grupos, consultar miembros y actualizar la pertenencia a grupos sin necesidad de hacerlo manualmente desde la consola de administracion.

Estructura

El workflow de esta carpeta parte de un Manual Trigger para pruebas y encadena varias llamadas al nodo Bitwarden. Primero se crea un grupo (resource group, operation create), despues se obtienen todos los miembros de la organizacion (resource member, operation getAll), a continuacion se actualizan los miembros del grupo creado (operation updateMembers) y finalmente se consultan los miembros actuales del grupo (operation getMembers) para confirmar el resultado. El nodo Error Handler (Stop And Error) detiene la ejecucion de forma controlada ante fallos inesperados.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de Bitwarden (API Key y URL de la organizacion) en los nodos Bitwarden. Paso 3: Ajustar el nombre del grupo y los identificadores de los miembros que se desean asociar en cada nodo segun la organizacion de destino. Paso 4: Ejecutar el workflow manualmente o sustituir el Manual Trigger por un disparador automatico segun el proceso de negocio. Paso 5: Verificar en el historial de ejecuciones de n8n que el grupo se crea, los miembros se actualizan y la consulta final refleja los cambios en Bitwarden.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0003_Bitwarden_Automate.json | Bitwarden Groups and Members Automation | Crea un grupo en Bitwarden, obtiene los miembros de la organizacion, actualiza la pertenencia al grupo y confirma los miembros resultantes.
