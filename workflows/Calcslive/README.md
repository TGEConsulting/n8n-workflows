Workflows de CalcsLive

Objetivo

Esta carpeta agrupa los workflows de n8n que se integran con CalcsLive, el servicio de calculos de ingenieria basado en unidades fisicas. El objetivo de este workflow es demostrar como ejecutar calculos de ingenieria (geometricos, cinematicos y de masa) directamente desde n8n y enviar los resultados por correo electronico, evitando el uso de hojas de calculo o calculadoras externas.

Estructura

El workflow de esta carpeta parte de un Manual Trigger de demostracion y encadena tres nodos CalcsLive independientes: uno calcula area y volumen de un cilindro a partir del diametro y la altura, otro calcula la velocidad a partir de una distancia y un tiempo, y otro calcula la masa a partir de la densidad y el volumen. Los valores de entrada (por ejemplo distancia y tiempo con sus unidades) se definen mediante un nodo Set antes de enviarse a CalcsLive. El resultado final se envia por correo mediante un nodo Gmail (Send Email) y el nodo Error Handler (Stop And Error) detiene la ejecucion de forma controlada ante fallos inesperados.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Configurar las credenciales de CalcsLive API en cada uno de los nodos CalcsLive. Paso 3: Ajustar los valores y unidades de entrada (distancia, tiempo, diametro, altura, densidad, volumen) segun el calculo que se desee realizar. Paso 4: Configurar las credenciales de Gmail para el envio del correo con los resultados. Paso 5: Ejecutar el workflow manualmente y verificar en el historial de ejecuciones de n8n que los calculos se realizan correctamente y el correo se envia con los resultados.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
2058_Calcslive_Engineering_Calculations_Manual.json | CalcsLive Engineering Calculations Demo | Ejecuta calculos de ingenieria (cilindro, velocidad y masa) con CalcsLive y envia los resultados por correo electronico.
