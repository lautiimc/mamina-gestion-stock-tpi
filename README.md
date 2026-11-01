# Mamina Sistema de gestión de stock

Trabajo Práctico Integrador de Organización Empresarial, Tecnicatura Universitaria en Programación, UTN.

**Integrantes:** Lautaro Romero y Naiquen Aprile.

## Sistema propuesto

Proponemos centralizar el stock de planta, depósito y sucursales. El diseño contempla entradas, ventas, consumos, pérdidas, transferencias y reservas para eventos, consultas por ubicación y alertas de mínimo. Cada responsable registra las operaciones de su área, de acuerdo con la estructura propuesta en la Entrega 3.

Disponible = físico - reservas activas. Reservar no reduce el físico; entregar registra venta y cierre de reserva juntos. Las transferencias actualizan ambos lugares juntos. El alcance del trabajo es el diseño documental del sistema.

## Enlaces del proyecto

- [Repositorio público](https://github.com/lautiimc/mamina-gestion-stock-tpi).
- [Tablero de trabajo](https://github.com/users/lautiimc/projects/2).

## Documentación

- [Informe integrador](Informe_Mamina.pdf).
- [Modelo BPMN editable con ambos procesos](Procesos_Mamina.bpmn).
- [Proceso general](Proceso_Movimientos.png) y [reservas para eventos](Proceso_Reservas.png).
- [Historias de usuario](Historias_de_usuario.md).
- [Indicadores y criterios de auditoría](Controles.md).

El modelo BPMN contiene dos procesos y dos diagramas. Las imágenes representan sus vistas generales y de reservas.

## Metas del sistema

Gestionar al menos 200 productos o insumos, consultar el stock en menos de 3 segundos, alertar con disponible menor o igual al mínimo y alcanzar al menos 95 % de coincidencia con el conteo físico del piloto. Los indicadores y casos de control establecen cómo evaluar esas metas.

## Metodología de trabajo colaborativo

Trabajamos juntos de forma presencial en el desarrollo de este trabajo. Para documentarlo, utilizaremos un repositorio público, ramas secundarias, commits descriptivos y un tablero vinculado con las tres historias de usuario.

El circuito de versionado utilizará la rama principal main y ramas secundarias para cambios concretos. Lautaro se encargará de subir los archivos a una rama secundaria, registrar commits descriptivos y abrir un Pull Request hacia main. Por ejemplo, docs: agregar procesos BPMN y reglas de reservas describe el contenido de un cambio.

Naiquen revisará el cambio y podrá aprobarlo o solicitar ajustes antes de incorporar la versión final a main. La revisión considerará las reglas de stock, los diagramas, los criterios de las historias y la coherencia con la Entrega 3. Si solicita ajustes, Lautaro los realizará en la misma rama y Naiquen volverá a revisarlos. La incorporación a main se realizará después de la aprobación y de resolver las conversaciones de revisión.

El backlog vincula las tres historias con sus tareas. Por Hacer, En Progreso y Listo expresan el estado de cada actividad según su alcance y criterio de cierre. La trazabilidad relaciona historias, cambios, commits y revisión de pares.

## Declaración de Uso de IA

Utilizamos ChatGPT como apoyo para organizar y desarrollar los materiales del trabajo, incluidos borradores de diagramas BPMN, historias de usuario, indicadores y documentación. Tomamos como base el caso Mamina y las entregas anteriores.

Las indicaciones se centraron en mantener esa continuidad, respetar las reglas de stock y explicar los procesos y controles con ejemplos sencillos.
