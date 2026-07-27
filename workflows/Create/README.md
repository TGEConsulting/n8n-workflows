Workflows de Create (Function)

Objetivo

Esta carpeta agrupa dos workflows de n8n de caracter educativo que muestran como generar datos de prueba (mock data) y construir estructuras JSON personalizadas mediante el nodo Function. El objetivo de estos workflows es servir como ejemplo de referencia para crear items o arreglos de objetos de forma programatica dentro de n8n, sin depender de una fuente de datos externa.

Estructura

Ambos workflows parten de un Manual Trigger y utilizan un primer nodo Function llamado Mock Data para generar datos ficticios de ejemplo. A partir de esos datos, un segundo nodo Function construye la estructura final: en un caso crea items en formato JSON y en el otro crea un arreglo de objetos. El nodo Error Handler (Stop And Error) detiene la ejecucion de forma controlada ante fallos inesperados.

Metodo de aplicacion

Paso 1: Importar el archivo JSON del workflow deseado en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows. Paso 2: Revisar el codigo del nodo Mock Data y ajustarlo segun la estructura de datos de ejemplo que se necesite. Paso 3: Revisar el codigo del segundo nodo Function y adaptarlo para generar el formato de salida deseado (items JSON o arreglo de objetos). Paso 4: Ejecutar el workflow manualmente. Paso 5: Verificar en el historial de ejecuciones de n8n que los datos generados tienen la estructura esperada antes de integrarlos en un flujo mayor.

Workflows incluidos

Archivo | Nombre del workflow | Descripcion
--- | --- | ---
1124_Create.json | Create JSON Items Example | Genera datos de prueba y los transforma en items JSON mediante un nodo Function.
1125_Create.json | Create Array of Objects Example | Genera datos de prueba y los transforma en un arreglo de objetos mediante un nodo Function.
