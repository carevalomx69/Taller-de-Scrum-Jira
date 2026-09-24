# Guía de la Primera Entrevista con su Empresa
### Proyecto de Desarrollo de Software para Empresas — Métodos de Desarrollo Ágil

## Antes de empezar

Esta es la reunión más importante del proyecto. Lo que se entienda bien (o mal) aquí define el resto del semestre. No es un interrogatorio ni un examen — es una conversación para entender un negocio real, con alguien que lo vive todos los días y probablemente nunca ha hablado con un desarrollador de software.

**Recomendaciones para el equipo:**

- Vayan **todos los integrantes** del equipo, si es posible. Quien no pregunte, toma notas.
- **Nombren a una sola persona que dirija la conversación** — evita que la empresa reciba la misma pregunta de dos personas distintas.
- Lleven esta guía impresa o abierta, pero **no la lean palabra por palabra** — es un mapa, no un guion. Usen sus propias palabras.
- **No usen jerga técnica** con el cliente: nada de "historia de usuario", "backlog", "sprint", "MVP". Pregunten en el lenguaje del negocio; ustedes traducen esas respuestas a Jira después, no durante la llamada.
- **Graben la sesión (con permiso) o tomen notas detalladas.** Van a necesitar citar ejemplos concretos más adelante, tanto para construir el sistema como para su propia evaluación del curso.
- Recuerden mencionar, aunque sea brevemente, lo que ya se dijo en la sesión de apertura: la información que compartan se usa únicamente para el desarrollo del proyecto, no se comparte con terceros ni con otros equipos.

**Duración sugerida:** 45–60 minutos. Si se alarga más, probablemente ya se está discutiendo el "cómo" en vez de seguir explorando el "qué" — está bien, pero anótenlo como pendiente para la siguiente llamada.

---

## 1. Entendiendo el negocio (10 min)

Antes de hablar del sistema, hay que entender la empresa. No asuman nada, aunque el giro les parezca obvio.

- Cuéntenos, en sus palabras, ¿a qué se dedica la empresa día a día?
- ¿Quiénes son sus clientes o usuarios principales?
- ¿Cuántas personas trabajan aquí, y quiénes usarían este sistema en el día a día?
- ¿Hay algo de su negocio que sea muy particular o distinto a otras empresas del mismo giro? (Esto casi siempre revela una regla de negocio importante que no es obvia desde fuera.)

---

## 2. El problema, no la solución (10 min)

Es normal que el cliente ya traiga en la cabeza una idea de "quiero una app que haga X". El trabajo del equipo es entender el problema de fondo antes de aceptar la solución que proponen.

- ¿Qué proceso les quita más tiempo, o les genera más errores, hoy en día?
- Si esa parte del negocio dejara de ser un dolor de cabeza, ¿qué cambiaría para ustedes?
- ¿Cómo resuelven esto **hoy**, sin ningún sistema? (Papel, Excel, WhatsApp, memoria, otra herramienta.) — esta pregunta casi siempre es la más reveladora de toda la entrevista.
- Si tuvieran que elegir **una sola cosa** que el sistema debe hacer bien sí o sí, ¿cuál sería?

> **Por qué importa esta última pregunta:** es la forma en lenguaje llano de identificar qué funcionalidad va primero en el proyecto. La respuesta aquí es, casi literalmente, su primera historia de usuario prioritaria.

---

## 3. Funcionalidades y prioridades (15 min)

Aquí es donde surgen las futuras historias de usuario. Dejen que el cliente hable libremente primero, y solo después ayúdenlo a aterrizar cada idea con estas preguntas:

- ¿Qué le gustaría poder **hacer** en el sistema? (Pidan que lo describan como una acción: "registrar", "consultar", "generar", "avisar" — no como una pantalla.)
- Para cada cosa que mencionen: ¿quién la haría — el dueño, un empleado, un cliente externo?
- ¿Con qué frecuencia pasaría eso — todos los días, una vez al mes?
- De todo lo que me ha platicado, si solo pudiéramos construir **tres cosas** en las primeras semanas, ¿cuáles elegiría usted?

**Técnica útil — "cuarto por cuarto, no capa por capa":** si el cliente describe una funcionalidad enorme ("quiero controlar todo mi inventario"), pregúntenle por el caso más simple y frecuente primero ("¿cuál es la operación que hacen todos los días con el inventario?"). Esa versión pequeña y completa es la que se construye primero — no una base de datos completa sin nada encima todavía.

> Anoten cada respuesta con el formato: **"[Quién] necesita [hacer qué], para [qué logra con eso]."** No hace falta decírselo al cliente así — pero si ustedes ya la anotan en esa forma, la historia de usuario en Jira prácticamente se escribe sola después.

---

## 4. Datos: qué hay que guardar (10 min)

Esta es la parte más concreta, y la que menos se presta a malentendidos.

- ¿Nos pueden compartir un ejemplo real de cómo registran esta información hoy? (Un formato en papel, un Excel, una factura, una libreta — lo que sea que ya usen.)
- De la información que manejan, ¿cuál es sensible o confidencial y necesitamos tener especial cuidado con ella?
- ¿Hay datos que necesiten obtener de otro sistema que ya usen (por ejemplo, un sistema de facturación, un banco, otra app)?
- ¿Qué reportes o resúmenes les gustaría poder ver? (Esto ayuda a saber qué datos hay que poder consultar, no solo registrar.)

**Pídanles el ejemplo real en el momento, o que se los envíen por el canal de comunicación después de la llamada** — es la evidencia más útil que van a tener para diseñar bien la base de datos.

---

## 5. Cómo lo hacen hoy — el proceso (10 min)

Entender el paso a paso actual evita construir un sistema que no encaja con cómo realmente trabajan.

- Camínenos paso a paso: ¿qué pasa desde que [inicia el proceso] hasta que [termina]? (Adapten esto al negocio: desde que llega un pedido hasta que se entrega, desde que se agenda una cita hasta que se atiende, etc.)
- ¿En qué parte de ese proceso se les complica más, o se les olvida algo seguido?
- ¿Hay pasos que dependen de que una persona en específico esté disponible? (Esto es una señal de un cuello de botella que el sistema podría aliviar.)

---

## 6. Alcance y expectativas — con honestidad (10 min)

Esta parte es incómoda pero necesaria. Mejor una expectativa clara desde el día uno que una decepción en diciembre.

- Cuéntenle al cliente, en sus palabras: vamos a construir el sistema por partes, empezando por lo más importante para ustedes, y les vamos a mostrar avances funcionando conforme vayan estando listos — no van a ver el sistema completo hasta el final.
- El semestre termina a mediados de diciembre — esa es la fecha límite para la entrega, aunque el equipo intentará terminar antes si es posible.
- Pregunten directamente: **de todo lo que platicamos hoy, ¿qué es lo que definitivamente debe estar listo, y qué estaría bien tener pero no es indispensable?** (Esto ya delimita el alcance real del proyecto, dicho por el propio cliente.)
- Sean honestos si algo que pide el cliente suena como que va a tomar más tiempo del que hay disponible — es mejor decirlo ahora que a mitad de noviembre.

---

## 7. Cerrando la entrevista (5 min)

- Confirmen quién será el contacto principal de la empresa para las siguientes semanas.
- Acuerden el canal de comunicación (WhatsApp y/o videollamada) y la frecuencia — mínimo una vez por semana.
- Agenden, si se puede, la fecha de la siguiente llamada antes de despedirse.
- Agradezcan su tiempo y la información compartida.

---

## 8. Después de la entrevista — trabajo del equipo (no con el cliente)

Con las notas ya tomadas, el equipo:

1. Redacta cada funcionalidad identificada como historia de usuario: *"Como [rol], quiero [acción], para [beneficio]."*
2. Registra por separado cualquier trabajo técnico necesario (configurar el proyecto, preparar la base de datos, etc.) como **Task**, no como historia.
3. Prioriza las historias con base en lo que el propio cliente marcó como indispensable en la Sección 6.
4. Sube el Backlog inicial a Jira y agenda con el equipo cuándo será la Sprint Planning de la primera semana de trabajo.
5. Si algo quedó ambiguo o a medias, **no lo adivinen** — es mejor una pregunta corta de seguimiento por WhatsApp que construir sobre un supuesto equivocado.

---

## Ejemplo aplicado (a modo de referencia)

Supongamos que la empresa es una veterinaria y el dueño responde así a la pregunta de la Sección 2:

> *"Hoy anotamos las citas en un cuaderno, y varias veces se nos empalman dos mascotas a la misma hora porque cada quien anota por su lado."*

De ahí, el equipo ya tiene:
- **Problema real:** citas duplicadas por falta de un registro centralizado.
- **Primera historia de usuario candidata:** *"Como recepcionista, quiero agendar una cita con nombre, mascota y horario, para evitar que se empalme con otra cita."*
- **Dato clave a capturar:** cliente, mascota, horario, y probablemente el motivo de la consulta.
- **Proceso actual:** cuaderno físico, sin validación de horarios — el sistema ya tiene una primera ventaja clara que ofrecer.

Esa misma lógica —de la respuesta del cliente a una historia concreta— es la que el equipo debe repetir con cada empresa real que le toque.
