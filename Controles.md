# Indicadores y auditoría técnica

Los indicadores establecen criterios de aceptación para evaluar el sistema diseñado. Cada estándar se vincula con una forma de control y un responsable dentro del modelo del caso.

| Indicador | Definición | Estándar | Frecuencia y evidencia | Responsable propuesto |
|---|---|---|---|---|
| K01 Catálogo | Cantidad de productos o insumos activos cargados y recuperables. | Al menos 200. | Carga de prueba antes del piloto. Exportación y consulta de control. | Equipo técnico |
| K02 Consulta | Tiempo desde solicitar stock hasta presentar la respuesta completa. | Cada consulta de la muestra < 3 s. | Elegir 10 consultas de distintos productos y ubicaciones, medir cada una y anotar equipo y cantidad de productos. | Equipo técnico |
| K03 Alerta | Casos correctos / casos ejecutados × 100. Casos disponible mínimo - 1, mínimo y mínimo + 1. | 100 %: alerta en los dos primeros y ausencia en el tercero. | Por cambio de regla y antes del piloto; captura o registro de prueba. | Administración y equipo |
| K04 Coincidencia | Pares producto y ubicación con igualdad exacta entre físico contado y registrado / pares contados × 100. | Al menos 95 % en el piloto. | Comparar sistema y conteo en el mismo momento; anotar cantidades y diferencias en una planilla. | Administración |
| K05 Integridad | Operaciones revisadas cuyo movimiento coincide con el cambio de stock / operaciones revisadas × 100. | 100 % de operaciones correctas; transferencias con ambos lugares actualizados. | Antes del piloto; comparar stock antes y después con el movimiento registrado. | Equipo técnico |
| K06 Colaboración | PR documental resuelto con revisión identificable de un par. | Al menos 1, con rama secundaria y commits descriptivos. | Al cierre del hito: URL de PR, revisión, resolución e historial reales. | Ambos integrantes |

## Protocolo

Para medir la consulta, cargaremos al menos 200 productos o insumos de prueba y elegiremos 10 consultas de distintos productos y ubicaciones. Anotaremos fecha, responsable, equipo, cantidad de productos y tiempo de cada consulta, desde que se solicita hasta que se muestra completa. Cada una debe tardar menos de 3 segundos: 3 segundos o más no cumple. Este control comprueba esos diez casos, no todos los equipos o situaciones posibles.

Para comprobar la coincidencia, elegiremos antes del conteo qué productos y ubicaciones se revisan en el piloto. Compararemos la cantidad física del sistema con lo contado en el mismo momento y en la misma unidad. Calcularemos coincidencias / pares revisados × 100. Por ejemplo, si de 100 pares coinciden 95, el resultado es 95 %: es un ejemplo, no una medición realizada. Incluiremos también los faltantes y las diferencias. Si revisamos solo una parte del stock, aclararemos ese alcance. Una reserva no cambia el físico que debemos comparar.

Si un indicador incumple, registrar incidencia con versión y evidencia, asignar responsable, corregir en rama secundaria y repetir el caso afectado antes de aprobar. El conteo no autoriza modificar existencias sin respaldo. Administración valida el desvío y el equipo técnico corrige reglas o carga según su causa. Gerencia recibe la información para decidir reposición o capacitación. Estas responsabilidades son propuestas para el caso académico.

## Casos de control

| Caso | Datos o acción | Resultado esperado |
|---|---|---|
| CP01 Entrada válida | Físico 10; entrada 4. | Físico 14 y un movimiento de entrada. |
| CP02 Salida sin disponible | Físico 20, reserva 5; salida 16. | Rechazo; físico 20, reserva 5 y sin movimiento. |
| CP03 Transferencia | Origen 20, destino 8; traslado 4. | Origen 16, destino 12, total 28; ambos o ninguno. |
| CP04 Alta y cancelación | Físico 20; reservar 5 y luego cancelar. | Alta: 20/5/15; cancelación: 20/0/20 (físico/reservado/disponible). |
| CP05 Límite de alerta | Mínimo 10; disponibles 9, 10 y 11. | Alerta en 9 y 10; sin alerta en 11. |
| CP06 Entrega de reserva | Físico 20; reserva activa 5. Entregar y repetir. | Primera: 15/0/15 y una venta; segunda rechazada. |
| CP07 Datos inválidos | Intentar cantidad 0, producto inexistente y transferencia al mismo lugar. | Rechazo con motivo y sin modificar stock en los tres casos. |
| CP08 Rendimiento | Catálogo >= 200; medir 10 consultas de productos y ubicaciones distintos. | Cada consulta < 3 s; anotar los 10 tiempos. |
| CP09 Conteo piloto | Corte acordado y muestra definida antes del conteo. | K04 >= 95 %; conservar desvíos y causas. |

Cada caso relaciona datos de entrada con un resultado esperado. El registro de auditoría identifica la evaluación, su versión, la fecha, el responsable y la evidencia correspondiente.

## Formato de registro de auditoría

| Caso o indicador | Versión | Fecha real | Responsable real | Resultado medido | Cumple | Evidencia | Acción |
|---|---|---|---|---|---|---|---|
|  |  |  |  |  |  |  |  |
