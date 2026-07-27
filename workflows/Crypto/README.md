Workflows de Crypto

Objetivo

Esta carpeta agrupa los workflows de n8n que utilizan el nodo Crypto para generar hashes (SHA256) como parte de servicios expuestos mediante Webhook. El objetivo de estos workflows es construir un acortador de enlaces con seguimiento de clics respaldado por Airtable y generar tokens o identificadores unicos a partir de datos recibidos, evitando el calculo manual de hashes.

Estructura

El primer workflow implementa un acortador de URLs completo: un Webhook recibe la URL larga, el nodo Crypto genera un hash SHA256 que sirve como identificador corto, y varios nodos Airtable buscan si el enlace ya existe, lo crean si es nuevo, y gestionan la redireccion, el conteo de clics y un panel de estadisticas mediante Webhooks adicionales y nodos If y Set. El segundo workflow es mas simple: un Webhook recibe una solicitud, el nodo Crypto genera un hash SHA256 que se usa como token de respuesta, y un nodo Set devuelve el resultado. El nodo Error Handler (Stop And Error) detiene la ejecucion de forma controlada ante fallos inesperados.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow deseado en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Para el acortador de URLs, configurar las credenciales de Airtable e indicar la base y tabla donde se almacenaran los enlaces, sus identificadores y el conteo de clics. Paso 3: Activar el workflow para que n8n exponga las URLs de los Webhooks correspondientes (creacion, redireccion y estadisticas). Paso 4: Enviar una solicitud de prueba con una URL larga o con los datos a hashear segun el workflow. Paso 5: Verificar en el historial de ejecuciones de n8n que el hash se genera correctamente y que, en el caso del acortador, el enlace se guarda y redirige correctamente en Airtable.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0042_Crypto_Airtable_Update_Webhook.json | URL Shortener with Airtable and Click Tracking | Acorta URLs generando un hash con Crypto, las almacena en Airtable y gestiona la redireccion y el conteo de clics.
0164_Crypto_Webhook_Automate_Webhook.json | Webhook Token Generator | Recibe una solicitud por Webhook y genera un token mediante un hash SHA256 con el nodo Crypto.
