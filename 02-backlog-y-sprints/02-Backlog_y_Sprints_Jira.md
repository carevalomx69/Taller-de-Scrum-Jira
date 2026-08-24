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

## 2. Épicas — agrupar historias relacionadas (opcional, útil si tienen muchas historias)

Una Épica es un cuerpo de trabajo grande que agrupa varias historias afines (ej. "Módulo de Inscripción"). Créenla desde el Backlog y arrastren historias relacionadas debajo. No es obligatorio para un proyecto pequeño, pero ayuda a no perderse si el Backlog crece.

## 3. Story Points — estimación rápida, sin obsesionarse

Jira usa por default una escala tipo Fibonacci (1, 2, 3, 5, 8...). Asígnenle un número a cada historia como referencia de tamaño relativo — no como ciencia exacta.

**No le dediquen más de un par de minutos a estimar cada historia** — ese exceso de precisión es exactamente el tipo de "teatro ágil" que este curso busca evitar.

## 4. Sprint Planning — iniciar el sprint

1. En el Backlog, arrastren 2-4 historias desde el bloque "Backlog" hacia el bloque de sprint (ej. "Sprint 1").
2. Denle clic a **"Iniciar sprint"** — les va a pedir duración (una o dos semanas está bien) y, opcionalmente, un Sprint Goal (una oración que resuma el propósito de este sprint).

## 5. Trabajando el sprint — el Tablero

Durante el sprint, cada integrante mueve sus propias tarjetas por las columnas del tablero (To Do → In Progress → Done) conforme avanza. El tablero es el reflejo visual del Daily Scrum — no lo sustituye.

## 6. Cerrando el sprint — la pantalla de "Completar sprint"

Al terminar la duración (o cuando decidan cerrarlo), denle clic a **"Completar sprint"**. Si queda alguna historia sin terminar, Jira les va a preguntar a dónde moverla:

- **"Nuevo sprint"** — la manda directo al siguiente sprint, ya comprometida, sin pasar por revisión de prioridad.
- **"Backlog"** — la regresa a la bolsa general, donde vuelve a competir por prioridad en el próximo Sprint Planning.

**Recomendación (y por qué):** manden las historias incompletas a **Backlog**, no a "Nuevo sprint". En Scrum, el Sprint Backlog debe ser siempre una decisión explícita del equipo en cada Planning — no algo que se arrastra automáticamente de un sprint a otro. Si una historia salta directo al siguiente sprint sin pasar por el Backlog, se le quita al Product Owner la oportunidad de reconsiderar si, dado lo que pasó, esa historia sigue siendo lo más valioso para trabajar ahora.

En la práctica real, algunos equipos sí eligen "Nuevo sprint" por pragmatismo — no es una regla absoluta, es una decisión de equipo que vale la pena discutir explícitamente en su primera Retrospectiva.

## 7. Leyendo los Reportes

En el menú del proyecto, busquen **Reports**:

- **Burndown Chart** — trabajo restante del sprint, día a día. Una línea que baja constante y pareja es buen ritmo; una línea plana varios días y una caída brusca al final sugiere que el equipo dejó todo para el último momento.
- **Velocity Chart** — compara story points completados por sprint, a lo largo de varios sprints. Sirve para calibrar cuánto planear la próxima vez — no para comparar ni castigar equipos entre sí.

### ✅ Checkpoint de esta sesión

Cada equipo debe poder mostrar: al menos un sprint completo (iniciado y cerrado), con la decisión de qué hacer con lo pendiente ya discutida como equipo, y su Burndown Chart, aunque los datos sean de práctica.

---

*Siguiente sesión: colaboración en equipo real y conexión con GitHub — el mismo repositorio que ya usan, ahora enlazado a sus historias de Jira.*
