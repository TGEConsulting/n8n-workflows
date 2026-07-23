# Workflows de Acuity Scheduling

## Objetivo
Esta carpeta agrupa los workflows de n8n que se integran con Acuity Scheduling, la plataforma de gestion de citas y reservas online. El objetivo es reaccionar automaticamente cuando ocurre un evento de agendamiento (por ejemplo una nueva cita programada, reprogramada o cancelada) para disparar procesos posteriores en n8n sin depender de revisiones manuales del calendario.

## Estructura
El workflow de esta carpeta sigue un patron de disparador mas manejo de errores. El nodo Acuity Scheduling Trigger escucha eventos en tiempo real mediante un webhook que n8n registra automaticamente en la cuenta de Acuity al activar el workflow. El nodo Error Handler (Stop And Error) detiene la ejecucion de forma controlada si el flujo llega a un estado no esperado, lo que facilita la depuracion durante pruebas.

## Metodo de aplicacion
Paso 1: Importar el archivo JSON del workflow en n8n usando la opcion Import from File o pegando el contenido en el editor de workflows.
Paso 2: Configurar las credenciales de Acuity Scheduling (usuario y API Key, u OAuth segun corresponda) en el nodo Acuity Scheduling Trigger.
Paso 3: Activar el workflow para que n8n registre el webhook correspondiente en Acuity Scheduling.
Paso 4: Sustituir o ampliar los nodos posteriores al disparador segun el proceso de negocio que se quiera automatizar, por ejemplo notificar al equipo o crear un registro en otro sistema.
Paso 5: Probar generando el evento real en Acuity Scheduling (crear o modificar una cita) y verificar la ejecucion correcta en el historial de ejecuciones de n8n.

## Workflows incluidos
| Archivo | Nombre del workflow | Descripcion |
|---|---|---|
| 1002_Acuityscheduling_Automate_Triggered.json | Acuityschedulingtrigger Workflow | Escucha en tiempo real eventos de agendamiento en Acuity Scheduling mediante el nodo Acuity Scheduling Trigger y permite disparar acciones posteriores en n8n. |
