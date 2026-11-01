# mallorca-blue-charters
Trabajo Práctico Integrador - Organización Empresarial (UTN TUP AD) - Mallorca Blue Charters S.L.

# 🛥️ Mallorca Blue Charters S.L. - Sistema Integral de Gestión de Flota y Reservas

**Asignatura:** Organización Empresarial  
**Carrera:** Tecnicatura Universitaria en Programación a Distancia (TUP AD)  
**Institución:** Universidad Tecnológica Nacional (UTN)  
**Trabajo Práctico Integrador (TPI) - Versión Consolidada Final**

---

## 👥 Autor
* **Nombre y Apellido:** Nicolas Gruszka


---

## 🔗 Enlaces Directos del Proyecto
* 📦 **Repositorio Público de GitHub:** https://github.com/GruszkaNicolas/mallorca-blue-charters.git
* 📋 **Tablero Ágil (GitHub Projects):** https://github.com/users/GruszkaNicolas/projects/1

---

## 📌 Descripción del Proyecto
El proyecto consiste en el análisis organizacional y el diseño de un sistema de software centralizado para **Mallorca Blue Charters S.L.**, una empresa dedicada al alquiler y chárter náutico en las Islas Baleares.

El sistema resuelve dos grandes problemáticas del negocio:
1. **Gestión Comercial:** Automatización de reservas en tiempo real para evitar sobreventas (*overbooking*).
2. **Gestión Operativa:** Control y alertas automáticas para el mantenimiento preventivo y correctivo de la flota de embarcaciones.

---

## 🛠️ Estructura del Trabajo Práctico Integrador

### 1. Marco Organizacional y Diagnóstico (Entregas 1 y 2)
* **Organización:** Mallorca Blue Charters S.L.
* **Diagnóstico Sistémico:** Definición de entradas, procesos, salidas y entorno del sistema.
* **Matriz FODA y Objetivos SMART:** Planeación estratégica y hoja de ruta mediante diagrama de Gantt.

### 2. Estructura Formal y Datos (Entrega 3)
* **Organigrama Normalizado:** Estructura jerárquica vertical respetando áreas operativas, comerciales y la Dirección de TI.
* **Diccionario de Datos Inicial:** Definición de entidades clave (`Embarcacion`, `Reserva`, `OrdenMantenimiento`).

### 3. Procesos, Gestión Ágil y Control (Entrega 4)
* **Diagrama de Procesos BPMN:** Flujo punta a punta de alquiler de embarcaciones y mantenimiento en la marina (Pools, Lanes y compuertas lógicas).
* **Historias de Usuario (Backlog):** Carga y seguimiento de tareas en GitHub Projects (Kanban).
* **Tablero de Indicadores de Control (KPIs):** Definición de métricas para evaluar la ocupación, tasa de averías y tiempo de respuesta.

---

## 🗺️ Diagrama BPMN (Entrega 4)
Proceso *Reserva, ejecución y mantenimiento de flota* con Pools (Cliente, Pasarela de pago, Mallorca Blue Charters), Lanes (Sistema, Atención al Cliente, Patrones y Tripulación, Jefatura de Mantenimiento) y 4 compuertas XOR para excepciones.

![BPMN](docs/bpmn-reserva-mantenimiento.png)

📄 Versión vectorial: [`docs/bpmn-reserva-mantenimiento.pdf`](docs/bpmn-reserva-mantenimiento.pdf)

---

## 📋 Backlog ágil (GitHub Projects)
| Issue | Historia de usuario | Estado |
|-------|---------------------|--------|
| [#1 HU-01](../../issues/1) | Como cliente turístico quiero consultar disponibilidad de embarcaciones en tiempo real, para planificar y asegurar mi reserva de chárter. | Done |
| [#2 HU-02](../../issues/2) | Como Jefe de Mantenimiento quiero alertas automáticas basadas en horas de navegación del motor, para programar revisiones y evitar fallas imprevistas en la flota. | In Progress |
| [#3 HU-03](../../issues/3) | Como Director Comercial quiero ver un reporte mensual de ocupación de la flota y facturación, para evaluar el rendimiento comercial de la temporada. | To Do |

---

## 📊 Indicadores de control (KPIs)
Resumen: tiempo de respuesta < 1,5 s (≥ 95 %), overbooking 0 %, bloqueo post-devolución < 30 s, canal directo ≥ 35 % a 6 meses, reducción de comisiones ≥ 20 %, ocupación de flota y tasa de averías (línea base temporada 1). Detalle completo y ajustes al diccionario de datos en [`docs/KPIs.md`](docs/KPIs.md).

---

## 🔀 Flujo de trabajo Git
* `main`: rama estable. Cada cambio se desarrolla en una rama `feature/...` y se integra mediante Pull Request con revisión de pares.
* Commits con formato `tipo: descripción` (`docs:`, `feat:`, `fix:`), un cambio lógico por commit.

---

## 🤖 Declaración de Uso de IA
**Herramientas y propósito.** Entregas 1 a 3: Google Gemini (redacción técnica, formateo y vectorización del organigrama, según la declaración de cada entrega). Entrega 4: Claude (Anthropic) para auditar el repositorio contra la consigna, generar un borrador del BPMN, proponer la estructura de KPIs y redactar el README / consolidar el PDF.

