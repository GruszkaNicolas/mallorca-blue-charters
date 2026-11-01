# Indicadores de control (KPIs) y estándares de desempeño

Derivados de las metas cuantitativas de la Entrega 2 y de las historias de usuario del backlog.
Donde no hay datos históricos, el estándar se fija como **línea base de la temporada 1** y se revisa con la Dirección.

| ID | Indicador | Fórmula | Estándar | Fuente / frecuencia / responsable | HU |
|----|-----------|---------|----------|-----------------------------------|----|
| KPI-1 | Tiempo de respuesta (disponibilidad y confirmación de pago) | Consultas con respuesta < 1,5 s / total de consultas × 100 | ≥ 95 % (meta 1, Entrega 2) | Logs del módulo; semanal; Dirección de TI | HU-01 |
| KPI-2 | Tasa de overbooking | Reservas confirmadas con franja solapada / reservas confirmadas × 100 | 0 % (meta 2) | Tabla `RESERVA`; continuo con alerta; Dir. TI y Dir. Operaciones | HU-01 |
| KPI-3 | Latencia de bloqueo posterior a la devolución | Instante del bloqueo de limpieza/mantenimiento − instante del check-out | < 30 s (meta 2) | Logs del módulo; por evento; Dirección de TI | HU-02 |
| KPI-4 | Participación del canal directo | Reservas por web propia / reservas totales × 100 | ≥ 35 % a los 6 meses (meta 3) | `RESERVA.canal_origen`; mensual; Dir. Comercial | HU-03 |
| KPI-5 | Reducción de comisiones a terceros | (Comisiones período base − actual) / base × 100 | ≥ 20 % (meta 3) | Liquidaciones de OTAs; mensual; Dir. Comercial | HU-03 |
| KPI-6 | Tasa de ocupación de flota | Horas reservadas / horas disponibles × 100, por embarcación | Línea base temporada 1 | `RESERVA` y `EMBARCACION`; mensual; Dir. Comercial | HU-03 |
| KPI-7 | Tasa de averías | Órdenes con `es_preventivo = False` / total de órdenes × 100 | Tendencia decreciente sobre la línea base | `ORDEN_MANTENIMIENTO`; mensual; Jefatura de Mantenimiento | HU-02 |

**Auditoría técnica:** revisión mensual (continua para KPI-2 y KPI-3). Todo desvío se registra como un nuevo *issue* en el tablero, con responsable asignado.

## Ajustes propuestos al diccionario de datos (v1.1)

| Entidad | Campo nuevo | Tipo | Justificación |
|---------|-------------|------|---------------|
| RESERVA | `fecha_fin` (o `duracion_horas`) | DATETIME / INTEGER | Detectar solapamientos y calcular ocupación |
| RESERVA | `canal_origen` | STRING / ENUM (`Directo`, `OTA`) | Medir canal propio y comisiones |
| EMBARCACION | `horas_motor_acumuladas` | DECIMAL | Base de las alertas preventivas (HU-02) |
| EMBARCACION | `umbral_mantenimiento_horas` | INTEGER | Umbral que dispara la orden preventiva |
