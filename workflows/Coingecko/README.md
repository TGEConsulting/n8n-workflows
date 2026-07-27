Workflows de CoinGecko

Objetivo

Esta carpeta agrupa los workflows de n8n que se integran con CoinGecko, el servicio de precios y datos de mercado de criptomonedas. El objetivo de este workflow es actualizar periodicamente el valor de un portafolio de criptomonedas almacenado en Airtable, consultando los precios actuales en CoinGecko y registrando la evolucion del valor total a lo largo del tiempo.

Estructura

El workflow de esta carpeta se dispara con un nodo Cron programado para ejecutarse al inicio de cada hora. Primero obtiene la lista de activos del portafolio desde Airtable, despues consulta en CoinGecko el precio actual de cada criptomoneda mediante el nodo CoinGecko. Un nodo Function determina el valor total del portafolio combinando las cantidades con los precios obtenidos, y los nodos Airtable actualizan el valor de cada activo y anaden un nuevo registro historico con el valor total del portafolio. El nodo Error Handler (Stop And Error) detiene la ejecucion de forma controlada ante fallos inesperados.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de Airtable, indicando la base y las tablas de portafolio e historico de valores. Paso 3: Configurar el nodo CoinGecko con los identificadores de las criptomonedas que se desean consultar. Paso 4: Ajustar la expresion del nodo Cron segun la frecuencia con la que se desea actualizar el valor del portafolio. Paso 5: Activar el workflow y verificar en el historial de ejecuciones de n8n que los precios se actualizan y el valor total se registra correctamente en Airtable.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
0177_Coingecko_Cron_Update_Scheduled.json | CoinGecko Portfolio Value Tracker | Actualiza periodicamente los precios de un portafolio de criptomonedas en Airtable y registra el valor total historico.
