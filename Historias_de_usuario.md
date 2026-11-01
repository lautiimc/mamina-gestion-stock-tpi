# Historias de usuario

Las historias describen las necesidades del sistema de stock de Mamina mediante un rol, una funcionalidad y un beneficio. Sus criterios de aceptación relacionan cada necesidad con un comportamiento esperado.

| Historia | Funcionalidad | Prioridad |
|---|---|---|
| HU01 | Movimientos y transferencias | Alta |
| HU02 | Consultas y alertas | Alta |
| HU03 | Reservas para eventos | Alta |

## HU01 Registrar movimientos y transferencias

Como responsable de stock de mi área, quiero registrar las entradas, salidas y transferencias a mi cargo, para mantener actualizadas las existencias de mi ubicación.

Prioridad: Alta.

### Criterios de aceptación

- Dado un producto activo y una cantidad positiva en su unidad, cuando registro una entrada válida, entonces aumenta el físico del destino y queda un movimiento con fecha y responsable.
- Dado físico 20 y reservas activas 5, cuando solicito una salida de 16, entonces se rechaza sin modificar datos porque el disponible es 15.
- Dado un traslado de 4 entre ubicaciones distintas con saldo suficiente, cuando se confirma, entonces origen baja 4 y destino sube 4 juntos; no se puede confirmar solo uno de los dos cambios.
- Dado origen igual a destino, referencia inexistente o cantidad no positiva, cuando intento confirmar, entonces se rechaza con motivo.

### Relación con el diseño

Entidades: Producto, Ubicación, Existencia y Movimiento.
Proceso de movimientos en Procesos_Mamina.bpmn: m_validate, m_check, m_commit.
Casos planificados: CP01, CP02, CP03, CP07.


## HU02 Consultar stock y alertas por ubicación

Como encargado de sucursal, quiero consultar el stock físico, reservado y disponible con alertas de mínimo por ubicación, para anticipar faltantes y solicitar reposición.

Prioridad: Alta.

### Criterios de aceptación

- Dado físico 20 y reservas activas 5, cuando consulto la ubicación, entonces veo físico 20, reservado 5 y disponible 15 en la unidad del producto.
- Dado un mínimo de 15 y disponible de 15 o menos, cuando se consulta o termina una operación confirmada, entonces se presenta una alerta; con disponible 16 no se presenta.
- Dado un catálogo de al menos 200 productos o insumos de prueba, cuando se mide la consulta con el protocolo de auditoría acordado, entonces cada consulta de la muestra tarda menos de 3 segundos.
- Dada una reserva cancelada o entregada, cuando se calcula lo reservado, entonces no se incluye.

### Relación con el diseño

Entidades: Producto, Ubicación, Existencia y Reserva.
Proceso de movimientos en Procesos_Mamina.bpmn: m_alert; proceso de reservas: r_alert.
Casos planificados: CP04, CP05, CP08.


## HU03 Gestionar reservas de eventos sin doble descuento

Como responsable de logística y eventos, quiero crear, cancelar y entregar reservas de productos por ubicación, para comprometer pedidos sin vender dos veces el mismo stock.

Prioridad: Alta.

### Criterios de aceptación

- Dado físico 20 y ninguna reserva, cuando creo una reserva de 5 con saldo suficiente, entonces físico sigue en 20, reservado es 5 y disponible es 15.
- Dada una reserva activa de 5, cuando la cancelo, entonces se libera esa cantidad y el físico no cambia.
- Dada una reserva activa de 5 con físico 20, cuando se entrega, entonces se registra venta por 5 y la reserva pasa a entregada en la misma operación: físico 15, reservado 0 y disponible 15.
- Dada una reserva ya entregada o cancelada, cuando se intenta entregar otra vez, entonces se rechaza sin otro movimiento.
- Dadas reservas ajenas activas, cuando se entrega una reserva, entonces se usa solo su cantidad y se preserva lo comprometido a las demás.

### Relación con el diseño

Entidades: Reserva, Existencia y Movimiento.
Proceso de reservas en Procesos_Mamina.bpmn: r_validate, r_new, r_cancel, r_deliver.
Casos planificados: CP04, CP06, CP07.


## Gestión del backlog

Las historias se relacionan con las tareas de documentación, modelado y control. Por Hacer identifica una actividad no iniciada; En Progreso, una actividad en desarrollo; y Listo, una tarea que cumple su criterio de cierre. El cierre de una especificación considera la claridad de sus reglas y criterios; el de una implementación considera el comportamiento observado del sistema.
