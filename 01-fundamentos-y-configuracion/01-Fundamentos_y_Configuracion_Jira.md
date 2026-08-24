# Fundamentos y Configuración
### Taller de Jira — primera sesión

## ¿Qué es Jira, realmente?

La forma más común de describirlo es "un gestor de proyectos" — pero es una simplificación. **Jira nació como un rastreador de errores (bug tracker)**, y con los años se generalizó para rastrear cualquier tipo de unidad de trabajo.

El modelo mental correcto: **Jira es un motor genérico de seguimiento de trabajo y flujos configurables — no "es" Scrum.** Lo que van a usar como "Proyecto Scrum" es una **plantilla** construida encima de ese motor: le pone nombres familiares (Backlog, Sprint, Board) a algo más simple y neutral por debajo — elementos rastreables ("issues") moviéndose entre estados.

Por qué les conviene saber esto desde ya:
- Los roles (Product Owner, Scrum Master, Equipo) **no se imponen técnicamente** — es una convención de equipo, no una restricción del sistema.
- El tablero es **configurable** — las columnas que van a ver no son "las columnas de Scrum", son solo un punto de partida.
- La herramienta permite tanta configuración que invita a complicarse de más — la simplicidad la pone el equipo, no la fuerza Jira.

## Antes de empezar: la estructura correcta para su equipo

**Un solo integrante del equipo crea el sitio de Jira — no se unan al de otro equipo ni al de su profesor.** Ese integrante después invita a sus compañeros como usuarios de ese mismo sitio.

Por qué importa: el plan gratuito permite hasta 10 usuarios **por sitio**. Cada equipo necesita el suyo propio, del mismo modo que cada equipo creó su propio repositorio en GitHub — no uno compartido entre todos.

## Paso 1 — Crear la cuenta y el proyecto (un integrante por equipo)

1. Vayan a [atlassian.com/software/jira](https://www.atlassian.com/software/jira) → "Obtener gratis" → creen la cuenta con un correo del equipo.
2. Al crear el primer proyecto, elijan la plantilla **Scrum**.
3. Cuando pregunte si el proyecto es "gestionado por el equipo" o "por la empresa", elijan **gestionado por el equipo** — es más simple y no requiere configuración adicional.
4. Pónganle nombre a su espacio (ej. "Equipo 3 — Sistema de Inscripción").

## Paso 2 — Invitar a los compañeros

Desde el sitio recién creado, inviten al resto del equipo por correo. Cada quien necesita su propia cuenta — no compartan un solo usuario entre varios, porque eso rompería la trazabilidad de autoría que buscamos (el mismo principio que ya vieron con Git: cada quien con su propia identidad).

## Paso 3 — Tour rápido de las pestañas

- **Resumen** — panorama general del proyecto.
- **Backlog** — el Product Backlog: aquí viven las historias que aún no están en ningún sprint.
- **Tablero** — el Board del sprint activo.
- **Calendario / Cronograma** — vistas de fechas; no las necesitan todavía para lo básico.

## Paso 4 — La pregunta "¿Cómo darán seguimiento a su trabajo?"

Al crear el proyecto, Jira pregunta por las columnas del tablero. **Dejen las tres que vienen por default (To Do / In Progress / Done) y avancen.** No agreguen columnas de más antes de haber corrido un solo sprint — si más adelante sienten que necesitan una columna extra (por ejemplo, "En revisión" para reflejar el Pull Request), la agregan cuando la necesidad aparezca de verdad, no antes. Esto se puede editar en cualquier momento desde el menú del tablero.

## Paso 5 — Dónde nace su primera historia

Van a ver **tres bloques apilados** en la vista Backlog: un "Sprint 0" con tareas de bienvenida que Jira genera automáticamente, un espacio para "Sprint 1" (vacío), y hasta abajo un bloque llamado **"Backlog"**.

**Cuidado aquí — es fácil confundirse:** los tres bloques tienen su propio botón "+ Crear", y se ven casi idénticos. Para su primera historia real, usen el **"+ Crear" del bloque de hasta abajo** (el que dice "Backlog", no el de "Sprint 0"). Si por error termina en el lugar equivocado, no pasa nada — se arrastra de un bloque a otro con el mouse, igual que se mueve una tarjeta entre columnas del tablero.

Pueden ignorar o completar rápido las 3 tareas de bienvenida del "Sprint 0" — no son parte de su proyecto real.

### ✅ Checkpoint de esta sesión

Cada integrante del equipo debe poder mostrar:
- Su propia cuenta, dentro del sitio de su equipo (no de otro equipo).
- Al menos una historia creada en el bloque correcto de **Backlog** (no en Sprint 0).

---

*Siguiente sesión: construcción completa del Backlog, Sprint Planning, y ejecución de un sprint de principio a fin.*
