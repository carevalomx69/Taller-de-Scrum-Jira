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

**¿Qué es un story point, realmente?** Es una medida de tamaño **relativo**, no de tiempo. Un story point no equivale a "tantas horas" — combina a la vez tres cosas: cuánto trabajo hay que hacer, qué tan complicado es, y cuánta incertidumbre o riesgo tiene. Por eso dos historias con "la misma cantidad de código" pueden merecer puntos distintos, si una es rutinaria y la otra tiene partes que nadie del equipo ha hecho antes.

**La pregunta correcta no es "¿cuántas horas me va a tomar?"**, sino **"¿qué tan grande es esto, comparado con otra historia que ya calificamos?"** — es una comparación relativa entre historias, no una medición absoluta de tiempo. Por ejemplo: si ya le pusieron 2 puntos a "agregar un campo al formulario de contacto", y la historia nueva se siente aproximadamente el doble de trabajo/complejidad/riesgo, probablemente es un 5, no un 4 (ver el siguiente punto sobre por qué).

Jira usa por default una escala tipo Fibonacci (1, 2, 3, 5, 8, 13...) **y no números consecutivos, a propósito**: entre más grande es una historia, más difícil es estimarla con precisión — los huecos crecientes entre los números reflejan esa incertidumbre real, en vez de fingir que pueden distinguir con exactitud entre un 11 y un 12.

**No le dediquen más de un par de minutos a estimar cada historia** — ese exceso de precisión es exactamente el tipo de "teatro ágil" que este curso busca evitar. Lo que de verdad calibra al equipo con el tiempo no es la estimación en sí, sino su **Velocity** real (cuántos puntos completan por sprint, sprint tras sprint, sección 8) — eso aterriza la escala a la realidad de su propio equipo, no una tabla de conversión a horas.

## 4. Antes de planear: la Definition of Done (DoD)

Antes de iniciar su primer sprint, el equipo debe acordar explícitamente **qué significa "terminado"** — sin esto, cada integrante puede tener una idea distinta de cuándo una historia realmente está lista, y la columna "Done" del tablero pierde su significado.

**Ejercicio (una sola vez por equipo, antes del primer Sprint Planning):** en conjunto, escriban una lista corta y concreta de 4-6 condiciones que TODA historia debe cumplir antes de moverse a "Done". Ejemplo (aplica igual sin importar cuál de los 4 clientes les tocó):
- El código está en `main` (fusionado vía Pull Request, no en una rama suelta)
- Se probó manualmente al menos una vez, sin errores visibles
- Un compañero distinto al autor revisó el Pull Request antes de aprobarlo
- No rompe ninguna funcionalidad que ya existía

**Ojo — no confundir DoD con Criterios de Aceptación.** Son dos cosas distintas, y es un error común mezclarlas:

| | Definition of Done | Criterios de Aceptación |
|---|---|---|
| ¿Cuántas hay? | Una sola, para todo el proyecto | Una distinta por cada historia |
| ¿Dónde vive? | Un solo lugar, compartido | Dentro de la descripción de cada historia |
| ¿Qué responde? | "¿Está terminado, en general?" | "¿Esta historia específica hace lo que debía?" |

Por ejemplo, para la historia del Cliente 2 (Papelería) — *"Como encargado de tienda, quiero ver la lista de productos con su cantidad disponible, para saber qué hay en existencia"* — los criterios de aceptación (correctamente escritos dentro de esa historia) podrían ser: *"1. El sistema muestra los productos registrados. 2. Cada producto muestra su cantidad disponible. 3. La cantidad corresponde al inventario actual. 4. Si no hay productos, el sistema lo indica claramente."* Eso es específico de esa historia — no se repite igual en la historia de "registrar una venta".

**Dónde vive la DoD en Jira, sin brincar a otra herramienta:** en la pestaña **"Documentos"** de su espacio (junto a Resumen, Backlog, Tablero, Calendario, Cronograma) — una sola página, fija, que todas las historias comparten por igual. Ahí también puede vivir una página por sprint con las notas de la Sprint Review (qué se mostró, qué feedback dio el Product Owner, qué queda pendiente) — igual que la DoD, ni la Review ni la Retrospectiva tienen pantalla propia dedicada en Jira, pero sus notas sí tienen un lugar natural ahí.

**Por qué importa:** sin DoD explícita, es común que una historia se marque "Done" con código a medias, sin probar, o sin revisar — perdiendo el valor real de tener una columna "Done" en primer lugar.

## 5. El Sprint Goal — un objetivo, no una lista de tareas

El Sprint Goal se captura al hacer clic en **"Iniciar sprint"** (o después, vía el menú "···" → "Editar sprint", si se les pasó ponerlo al inicio). Es una sola oración medible, no la lista de historias del sprint — esas ya están en el tablero, repetirlas como objetivo no aporta nada.

**Ejemplo por cada uno de los 4 clientes:**
- **Veterinaria Huellitas:** *"Al final del sprint, recepción puede agendar, ver y cancelar citas del día sin usar el cuaderno."*
- **Papelería El Rincón Escolar:** *"Al final del sprint, el encargado puede ver el inventario actual y recibe una alerta cuando un producto está por agotarse."*
- **Taller Mecánico El Buen Motor:** *"Al final del sprint, cualquier compañero puede consultar el estado de una orden por placa o nombre del cliente."*
- **Despacho Contable Núñez y Asociados:** *"Al final del sprint, el contador ve de un vistazo qué clientes ya entregaron sus documentos del mes y cuáles no."*

**Advertencia sobre la interfaz:** por el mismo rediseño de navegación que ya vivieron antes en otras pantallas de Jira, el Sprint Goal **no siempre aparece visible de un vistazo** en el tablero activo. Si un equipo dice "no le pusimos objetivo a nuestro sprint", confirmen primero en "Editar sprint" antes de asumir que de verdad no existe.

## 6. Antes de planear, también: Convenciones Técnicas del Equipo

Hay decisiones que el equipo necesita acordar **una sola vez**, al mismo tiempo que la Definition of Done — no porque generen valor visible para el cliente, sino porque sin ellas los commits de distintas personas no van a combinar bien entre sí. Dos ejemplos típicos: la estética del frontend, y las entidades base de la base de datos.

**Esto no contradice trabajar por historias — lo hace posible.** Así como construir "cuarto por cuarto" (en vez de por capas completas) sí requiere acordar de antemano cosas estructurales compartidas (por dónde entra la tubería, la altura de techo), trabajar por historias también requiere un puñado de acuerdos mínimos compartidos antes del primer "cuarto" — sin diseñar cada cuarto a detalle por adelantado.

**Estética del frontend:** usen las variables CSS en `:root` (`--color-primario`, `--color-secundario`, etc.) que ya vieron en el proyecto de práctica de Git. El equipo decide la paleta y tipografía en un par de minutos, y **una sola Task** ("Crear archivo base de estilos con paleta acordada") deja el archivo listo — cada historia después solo usa esas variables, no inventa colores nuevos.

**Entidades base de la base de datos — la pregunta que más genera dudas:**

Es normal sentir que esto choca con lo que enseña un curso clásico de Bases de Datos ("diseña, normaliza y modela todo primero"). No es una contradicción real, una vez que se separan dos preguntas distintas:

- **Normalización** responde *"¿qué tan bien diseñada está esta tabla?"* — una cuestión de calidad, siempre vigente.
- **Ágil** responde *"¿cuándo y cuánto diseñamos de una vez?"* — una cuestión de momento y alcance, no de rigor.

Esta forma de trabajar tiene nombre propio en la ingeniería de software: **diseño evolutivo de bases de datos** (Scott Ambler, *Agile Database Techniques*; también descrito por Martin Fowler como *database refactoring*). La idea: el esquema evoluciona con cambios controlados y normalizados, uno a la vez — no se congela desde el día uno, pero tampoco se improvisa sin cuidado.

En la práctica, el equipo sí debe acordar por adelantado un **modelo conceptual ligero**: las 3-5 entidades principales y sus relaciones más obvias (para la veterinaria: Cliente, Mascota, Cita — una Mascota pertenece a un Cliente). Eso es, literalmente, la primera mitad de lo que ya enseña su curso de BD — el diagrama entidad-relación conceptual. Lo que **no** se hace por adelantado es el modelo relacional completo, ya normalizado, con cada atributo definido — eso se construye historia por historia, con el mismo rigor de siempre, solo que aplicado a un pedazo a la vez, no al sistema completo de una sentada.

Es la misma idea que ya vieron en el Manifiesto Ágil (Unidad I): *"no es 'no documentar', es documentar lo suficiente"* — aquí es *"no es 'no diseñar la base de datos', es diseñar lo suficiente para arrancar, dejando que el detalle se resuelva historia por historia."*

## 7. Sprint Planning — iniciar el sprint

1. En el Backlog, arrastren 2-4 historias desde el bloque "Backlog" hacia el bloque de sprint (ej. "Sprint 1").
2. Denle clic a **"Iniciar sprint"** — les va a pedir duración (una o dos semanas está bien) y, opcionalmente, un Sprint Goal (una oración que resuma el propósito de este sprint).

## 8. Trabajando el sprint — el Tablero

Durante el sprint, cada integrante mueve sus propias tarjetas por las columnas del tablero (To Do → In Progress → Done) conforme avanza. El tablero es el reflejo visual del Daily Scrum — no lo sustituye.

## 9. Cerrando el sprint — la pantalla de "Completar sprint"

Al terminar la duración (o cuando decidan cerrarlo), denle clic a **"Completar sprint"**. Si queda alguna historia sin terminar, Jira les va a preguntar a dónde moverla:

- **"Nuevo sprint"** — la manda directo al siguiente sprint, ya comprometida, sin pasar por revisión de prioridad.
- **"Backlog"** — la regresa a la bolsa general, donde vuelve a competir por prioridad en el próximo Sprint Planning.

**Recomendación (y por qué):** manden las historias incompletas a **Backlog**, no a "Nuevo sprint". En Scrum, el Sprint Backlog debe ser siempre una decisión explícita del equipo en cada Planning — no algo que se arrastra automáticamente de un sprint a otro. Si una historia salta directo al siguiente sprint sin pasar por el Backlog, se le quita al Product Owner la oportunidad de reconsiderar si, dado lo que pasó, esa historia sigue siendo lo más valioso para trabajar ahora.

En la práctica real, algunos equipos sí eligen "Nuevo sprint" por pragmatismo — no es una regla absoluta, es una decisión de equipo que vale la pena discutir explícitamente en su primera Retrospectiva.

## 10. Leyendo los Reportes

En el menú del proyecto, busquen **Reports**:

- **Burndown Chart** — trabajo restante del sprint, día a día. Una línea que baja constante y pareja es buen ritmo; una línea plana varios días y una caída brusca al final sugiere que el equipo dejó todo para el último momento.
- **Velocity Chart** — compara story points completados por sprint, a lo largo de varios sprints. Sirve para calibrar cuánto planear la próxima vez — no para comparar ni castigar equipos entre sí.

### ✅ Checkpoint de esta sesión

Cada equipo debe poder mostrar: su Definition of Done ya escrita y acordada, al menos un sprint completo (iniciado y cerrado), con la decisión de qué hacer con lo pendiente ya discutida como equipo, y su Burndown Chart, aunque los datos sean de práctica.

---

*Siguiente sesión: colaboración en equipo real y conexión con GitHub — el mismo repositorio que ya usan, ahora enlazado a sus historias de Jira.*
