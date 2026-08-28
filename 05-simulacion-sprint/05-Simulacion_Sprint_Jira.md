# Mini-Proyecto de Práctica — Sprint de Calentamiento
### Antes de los clientes reales

## Por qué este ejercicio

En una semana o semana y media va a resolverse la convocatoria de vinculación, y sus equipos van a tener un cliente real. Este mini-proyecto es la última práctica seguro-sin-consecuencias: van a vivir el ciclo completo (backlog → sprint → colaboración en Git/GitHub → Jira conectado) una vez más, esta vez con un cliente ficticio que no conocen de antemano — para que el "momento de la verdad" no sea la primera vez que enfrentan un brief ambiguo de principio a fin.

## Duración y expectativas

**Un solo sprint, de aproximadamente semana y media.** No es tiempo para un sistema completo — es tiempo para un MVP genuinamente mínimo: 3-4 historias bien escritas, completadas de verdad (con su Definition of Done cumplida), es mucho más valioso que 8 historias a medias.

**Product Owner: el profesor, para los 4 equipos.** A diferencia de un cliente real ocupado, estas sesiones están dedicadas por completo a este ejercicio — no hay clase normal en paralelo — así que la disponibilidad para resolver dudas de priorización es alta *durante el tiempo de clase*. Aprovechen esas sesiones para consultar directamente; fuera de ellas, avancen con supuestos razonables y confirmen después, tal como tendrían que hacerlo con cualquier cliente que no está disponible las 24 horas.

**Scrum Master: cada equipo designa el suyo.** Ya que el papel de Product Owner queda fijo esta vez, aprovechen para practicar la rotación en el rol de Scrum Master — facilita las ceremonias, lleva el pulso del tablero, y es quien debe detectar y escalar impedimentos ante el Product Owner durante las sesiones dedicadas.

---

## Los 4 clientes ficticios (uno por equipo)

Cada brief está escrito deliberadamente con algo de ambigüedad — como hablaría un cliente real, no como una lista de requerimientos ya masticada. Parte del ejercicio es que el equipo (con su PO) traduzca esto a historias bien formadas, no solo copiar las sugeridas tal cual.

### Cliente 1 — Clínica Veterinaria "Huellitas"

> *"Somos una clínica veterinaria pequeña. Ahorita llevamos las citas en un cuaderno y a veces se nos empalman horarios, o se nos olvida contactar al dueño de la mascota para recordarle su cita. Queremos algo simple para agendar y saber qué mascotas vienen cada día."*

**Backlog inicial sugerido** (el equipo puede ajustar, agregar o dividir):
- Como recepcionista, quiero ver el calendario de citas del día, para saber qué mascotas llegan y a qué hora.
- Como recepcionista, quiero agendar una nueva cita con nombre del dueño, mascota y horario, para evitar que se me olvide o se empalme con otra.
- Como recepcionista, quiero cancelar o reprogramar una cita existente, para ajustar cambios de último momento.
- *(a definir con su Product Owner: ¿qué pasa si dos personas intentan agendar el mismo horario?)*

### Cliente 2 — Papelería "El Rincón Escolar"

> *"Se nos acaba el producto sin darnos cuenta, y a veces compramos de más de algo que ya teníamos harto. Queremos saber qué tenemos y cuánto, para no quedarnos sin lo que más se vende."*

**Backlog inicial sugerido:**
- Como encargado de tienda, quiero ver la lista de productos con su cantidad disponible, para saber qué hay en existencia.
- Como encargado de tienda, quiero registrar una venta y que descuente del inventario automáticamente, para mantener el conteo actualizado.
- Como encargado de tienda, quiero ver una alerta cuando un producto esté por agotarse, para reabastecer a tiempo.
- *(a definir con su Product Owner: ¿qué se considera "por agotarse" — un número fijo, o distinto por producto?)*

### Cliente 3 — Taller Mecánico "El Buen Motor"

> *"Cuando un carro entra al taller, a veces se nos pierde de vista en qué va — si ya lo revisamos, si estamos esperando una pieza, o si ya quedó listo. El cliente llama a preguntar y no siempre tenemos la respuesta a la mano."*

**Backlog inicial sugerido:**
- Como mecánico, quiero registrar un carro que entra al taller con el problema reportado, para llevar control de qué se recibió.
- Como mecánico, quiero cambiar el estado de una orden (En revisión / En reparación / Listo), para reflejar el avance real.
- Como recepcionista, quiero consultar el estado de la orden de un cliente por su nombre o placa, para responderle rápido cuando llame.
- *(a definir con su Product Owner: ¿el cliente necesita ver su propio estado, o solo el personal del taller?)*

### Cliente 4 — Despacho Contable "Núñez y Asociados"

> *"Tenemos varios clientes que nos deben entregar documentos cada mes (facturas, comprobantes), y se nos complica llevar cuenta de quién ya entregó y quién no."*

**Backlog inicial sugerido:**
- Como contador, quiero ver una lista de mis clientes con el estatus de sus documentos del mes (pendiente/entregado), para saber a quién dar seguimiento.
- Como contador, quiero marcar un documento como recibido, para actualizar el estatus del cliente.
- Como contador, quiero agregar un nuevo documento requerido a un cliente específico, para casos que no son iguales todos los meses.
- *(a definir con su Product Owner: ¿los documentos se repiten igual cada mes, o cada cliente tiene requisitos distintos?)*

---

## Recordatorios de mecánica — aplicando todo lo visto

- **Historias bien escritas:** formato completo, con su "para..." — no solo tareas técnicas disfrazadas de historia.
- **Definition of Done acordada antes de arrancar** — no empiecen a programar sin ella.
- **Un ciclo completo de Scrum:** Sprint Planning → trabajo diario con el tablero → Sprint Review (demo real al profesor, como Product Owner) → Retrospectiva.
- **Ramas nombradas con la clave de Jira**, Pull Requests revisados por un compañero distinto al autor, nunca *push* directo a `main`.

### Tareas técnicas vs. historias — el caso de la base de datos

La base de datos **no es una historia aparte** — se construye junto con cada historia, solo lo necesario para esa historia (rebanada vertical, no horizontal). Con el Cliente 1 (veterinaria), por ejemplo:

- **Una tarea técnica única, al arrancar** (issue tipo "Task", no historia): *"Configurar repositorio y conexión inicial a base de datos vacía"* — sin tablas todavía.
- **La historia "Ver calendario de citas del día"** es donde nace la tabla `citas`, con exactamente los campos que esa historia necesita — no más.
- **La historia "Agendar nueva cita"** probablemente no necesita tabla nueva, pero sí la validación de traslape de horarios — eso se construye ahí, no antes.

Si un equipo nota que casi cada historia "necesita primero una tarea técnica", es señal de que están rebanando horizontal en vez de vertical.

### El despliegue — sí va en el backlog, al final

Agréguenlo como **tarea técnica** (Task, no historia con formato "Como \<rol\>..."), ya que no hay negociación real de prioridad — es trabajo que debe pasar sí o sí antes de la Sprint Review. Prográmenlo al final del sprint, una vez que las historias principales ya funcionan localmente, y no lo dejen fuera del tablero solo "porque no es una historia" — si no está trackeado, es fácil subestimarlo y que se les eche encima el último día.

## Entregable al final del sprint

- Una demo funcional en la Sprint Review (aunque sea pequeña — MVP real, no aparatoso).
- Retrospectiva documentada: qué mejorarían para cuando llegue el cliente real.
- Su tablero de Jira y repositorio de GitHub como evidencia del proceso completo.
