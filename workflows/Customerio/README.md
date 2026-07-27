Workflows de Customer.io

Objetivo

Esta carpeta agrupa los workflows de n8n que se integran con Customer.io, la plataforma de mensajeria y automatizacion de marketing basada en el comportamiento de los usuarios. El objetivo de este workflow es reaccionar en tiempo real cuando un suscriptor se da de baja en Customer.io, para disparar procesos automatizados dentro de n8n, evitando la revision manual de las bajas.

Estructura

El workflow de esta carpeta sigue un patron de disparador mas manejo de errores. El nodo Customer.io Trigger escucha en tiempo real los eventos de baja de suscriptores mediante un webhook que n8n registra automaticamente en la cuenta de Customer.io al activar el workflow. El nodo Error Handler (Stop And Error) detiene la ejecucion de forma controlada si el flujo llega a un estado no esperado, lo que facilita la depuracion durante pruebas.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de Customer.io (Site ID y API Key) en el nodo Customer.io Trigger. Paso 3: Seleccionar el evento de baja de suscriptor que debe disparar el workflow. Paso 4: Activar el workflow para que n8n registre el webhook correspondiente en Customer.io. Paso 5: Anadir los nodos posteriores al disparador segun el proceso de negocio que se quiera automatizar y verificar en el historial de ejecuciones de n8n que las bajas se reciben correctamente.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0738_Customerio_Update_Triggered.json | Customer.io Unsubscribe Automation | Escucha en tiempo real cuando un suscriptor se da de baja en Customer.io y permite disparar acciones posteriores en n8n.
