# Backlog y Sprints
### Taller de Jira — segunda sesión

Parte de donde quedó la sesión anterior: ya tienen cuenta, su equipo está creado, y al menos una historia vive en el Backlog. Aquí van a escribir historias de verdad y correr un sprint completo, de principio a fin.

## 1. Escribiendo buenas historias de usuario

**Formato estándar (Connextra):** *"Como \<rol\>, quiero \<acción\>, para \<beneficio\>"*

El **"para..."** (el beneficio) es la parte que más se omite — y la más importante: sin ella se pierde el propósito de por qué vale la pena construirla.

**Debe caber cómodamente en un sprint** — el criterio "Small" de INVEST, que ya conocen de Ingeniería de Requerimientos.

**Qué NO es una historia de usuario:**
- ❌ *"Como desarrollador, quiero refactorizar la base de datos"* — es una tarea técnica sin valor visible para el usuario final. Anti-patrón muy común en equipos que apenas empiezan.
- ✅ *"Como alumno, quiero inscribirme a mis materias del semestre, para asegurar mi lugar en clase"* — sí tiene un beneficio claro para alguien real.

Tampoco es un caso de uso detallado ni un mockup de interfaz — son artefactos válidos que pueden acompañar a la historia, pero no son la historia misma.

**¿Y el trabajo técnico que no es una historia de usuario? (bases de datos, configuración, investigación)**

No todo cabe en el formato de historia — y forzarlo no ayuda. Dos categorías más que van a necesitar:

- **Tareas técnicas (issue tipo "Task" en Jira):** trabajo de infraestructura sin un "para..." claro hacia el usuario final (ej. "Configurar esquema inicial de base de datos"). Se agregan al Backlog tal cual, sin forzar el formato "Como \<rol\>...".
- **Spikes:** una tarea de investigación acotada en tiempo, cuyo entregable es una decisión, no una funcionalidad (ej. "Investigar y decidir: MySQL vs. PostgreSQL — máximo 2 horas").

**Regla general para no crear tareas técnicas de más:** la base de datos, la interfaz y la lógica de una historia se construyen *juntas, poco a poco*, historia por historia — no como una fase aparte al principio ("primero toda la base de datos, luego todo el frontend"). Si se descubren necesitando una tarea técnica muy seguido, es señal de que están rebanando el trabajo de forma horizontal en vez de vertical.

Los requisitos no funcionales (rendimiento, seguridad) tampoco suelen ser historias ni tareas propias — si aplican a todo el proyecto, viven en la **Definition of Done** (siguiente sección); si aplican solo a una historia específica, van como criterio de aceptación de esa historia.

## 2. Épicas — agrupar historias relacionadas (opcional, útil si tienen muchas historias)

Una Épica es un cuerpo de trabajo grande que agrupa varias historias afines (ej. "Módulo de Inscripción"). Créenla desde el Backlog y arrastren historias relacionadas debajo. No es obligatorio para un proyecto pequeño, pero ayuda a no perderse si el Backlog crece.

## 3. Story Points — estimación rápida, sin obsesionarse

Jira usa por default una escala tipo Fibonacci (1, 2, 3, 5, 8...). Asígnenle un número a cada historia como referencia de tamaño relativo — no como ciencia exacta.

**No le dediquen más de un par de minutos a estimar cada historia** — ese exceso de precisión es exactamente el tipo de "teatro ágil" que este curso busca evitar.

## 4. Antes de planear: la Definition of Done (DoD)

Antes de iniciar su primer sprint, el equipo debe acordar explícitamente **qué significa "terminado"** — sin esto, cada integrante puede tener una idea distinta de cuándo una historia realmente está lista, y la columna "Done" del tablero pierde su significado.

**Ejercicio (una sola vez por equipo, antes del primer Sprint Planning):** en conjunto, escriban una lista corta y concreta de 4-6 condiciones que TODA historia debe cumplir antes de moverse a "Done". Ejemplos típicos para un proyecto como el suyo:
- El código está en `main` (fusionado vía Pull Request, no en una rama suelta)
- Se probó manualmente al menos una vez, sin errores visibles
- Un compañero distinto al autor revisó el Pull Request antes de aprobarlo
- No rompe ninguna funcionalidad que ya existía

**Dónde vive esto en Jira:** no hay una pantalla dedicada para la Definition of Done — anótenla en la descripción del proyecto, en un documento fijado en el espacio de su equipo, o en el README de su repositorio de GitHub. Lo importante no es dónde se guarda, sino que todo el equipo la conozca y la respete de la misma forma.

**Por qué importa:** sin DoD explícita, es común que una historia se marque "Done" con código a medias, sin probar, o sin revisar — perdiendo el valor real de tener una columna "Done" en primer lugar.

## 5. Sprint Planning — iniciar el sprint

1. En el Backlog, arrastren 2-4 historias desde el bloque "Backlog" hacia el bloque de sprint (ej. "Sprint 1").
2. Denle clic a **"Iniciar sprint"** — les va a pedir duración (una o dos semanas está bien) y, opcionalmente, un Sprint Goal (una oración que resuma el propósito de este sprint).

## 6. Trabajando el sprint — el Tablero

Durante el sprint, cada integrante mueve sus propias tarjetas por las columnas del tablero (To Do → In Progress → Done) conforme avanza. El tablero es el reflejo visual del Daily Scrum — no lo sustituye.

## 7. Cerrando el sprint — la pantalla de "Completar sprint"

Al terminar la duración (o cuando decidan cerrarlo), denle clic a **"Completar sprint"**. Si queda alguna historia sin terminar, Jira les va a preguntar a dónde moverla:

- **"Nuevo sprint"** — la manda directo al siguiente sprint, ya comprometida, sin pasar por revisión de prioridad.
- **"Backlog"** — la regresa a la bolsa general, donde vuelve a competir por prioridad en el próximo Sprint Planning.

**Recomendación (y por qué):** manden las historias incompletas a **Backlog**, no a "Nuevo sprint". En Scrum, el Sprint Backlog debe ser siempre una decisión explícita del equipo en cada Planning — no algo que se arrastra automáticamente de un sprint a otro. Si una historia salta directo al siguiente sprint sin pasar por el Backlog, se le quita al Product Owner la oportunidad de reconsiderar si, dado lo que pasó, esa historia sigue siendo lo más valioso para trabajar ahora.

En la práctica real, algunos equipos sí eligen "Nuevo sprint" por pragmatismo — no es una regla absoluta, es una decisión de equipo que vale la pena discutir explícitamente en su primera Retrospectiva.

## 8. Leyendo los Reportes

En el menú del proyecto, busquen **Reports**:

- **Burndown Chart** — trabajo restante del sprint, día a día. Una línea que baja constante y pareja es buen ritmo; una línea plana varios días y una caída brusca al final sugiere que el equipo dejó todo para el último momento.
- **Velocity Chart** — compara story points completados por sprint, a lo largo de varios sprints. Sirve para calibrar cuánto planear la próxima vez — no para comparar ni castigar equipos entre sí.

### ✅ Checkpoint de esta sesión

Cada equipo debe poder mostrar: su Definition of Done ya escrita y acordada, al menos un sprint completo (iniciado y cerrado), con la decisión de qué hacer con lo pendiente ya discutida como equipo, y su Burndown Chart, aunque los datos sean de práctica.

---

*Siguiente sesión: colaboración en equipo real y conexión con GitHub — el mismo repositorio que ya usan, ahora enlazado a sus historias de Jira.*
