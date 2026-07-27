Workflows de Chargebee

Objetivo

Esta carpeta agrupa los workflows de n8n que se integran con Chargebee, la plataforma de gestion de suscripciones y facturacion recurrente. El objetivo de este workflow es reaccionar a eventos que ocurren dentro de una cuenta de Chargebee para disparar procesos automatizados dentro de n8n, evitando la revision manual de la actividad de suscripciones y facturas.

Estructura

El workflow de esta carpeta sigue un patron de disparador mas manejo de errores. El nodo Chargebee Trigger escucha eventos en tiempo real mediante un webhook que n8n registra automaticamente en la cuenta de Chargebee al activar el workflow. El nodo Error Handler (Stop And Error) detiene la ejecucion de forma controlada si el flujo llega a un estado no esperado, lo que facilita la depuracion durante pruebas.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de Chargebee (site y API Key) en el nodo Chargebee Trigger. Paso 3: Seleccionar los eventos de Chargebee que deben disparar el workflow (por ejemplo creacion de suscripcion, pago o cancelacion). Paso 4: Activar el workflow para que n8n registre el webhook correspondiente en Chargebee. Paso 5: Anadir los nodos posteriores al disparador segun el proceso de negocio que se quiera automatizar y verificar en el historial de ejecuciones de n8n que los eventos se reciben correctamente.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0041_Chargebee_Update_Triggered.json | Chargebee Events Automation | Escucha en tiempo real los eventos de una cuenta de Chargebee y permite disparar acciones posteriores en n8n.
