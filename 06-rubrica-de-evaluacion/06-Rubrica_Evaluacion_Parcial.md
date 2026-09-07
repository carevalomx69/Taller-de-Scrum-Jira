# Rúbrica de Evaluación — Examen Parcial
### Métodos de Desarrollo Ágil — evaluación basada en evidencia + entrevista individual

## Principio de evaluación

Esta evaluación reemplazará el examen teórico tradicional por evidencia de trabajo: lo que su equipo construyó en Jira y GitHub durante el sprint simulado de prueba. La evaluacíón es bajo dos ideas centrales:

1. **Cantidad no es calidad.** Contar commits o líneas de código para calificar es el mismo error que medir productividad de software por LOCs (lines of code) en los métodos tradicionales, ya que es fácil de "inflar", pero es injusto con quien piensa mucho y teclea poco. Por eso los logs **no otorgan puntos directamente** en esta rúbrica, pero si  funcionan como verificación, no como métrica de desempeño.
2. **El componente de calificación individual se obtiene explicando, no acumulando.** Es decir, quien entiende bien lo que se le asingó y decidió su propio trabajo puede explicarlo bajo pregunta directa, sin importar cuántos commits tenga a su nombre.

## Estructura general — 100 puntos

| Dimensión | Puntos | Se califica por equipo o individual |
|---|---|---|
| A. Proceso de equipo | 40 | Igual para todos los integrantes del equipo |
| B. Contribución individual (entrevista) | 60 | Individual, con verificación de trazabilidad como filtro previo |

---

## Dimensión A — Proceso de Equipo (40 puntos)

Todos los integrantes de un mismo equipo reciben esta puntuación por igual — evalúa la aplicación correcta de la metodología, no el desempeño de una persona.

| Criterio | Puntos | Evidencia a revisar |
|---|---|---|
| Backlog bien construido | 10 | Historias con formato correcto ("Como... quiero... para..."); tareas técnicas registradas como "Task", no forzadas a formato de historia; sin señales de "rebanado horizontal" |
| Definition of Done existe y se respetó | 10 | DoD documentada (visible en el espacio de Jira o README); Pull Requests realmente revisados por alguien distinto al autor antes de fusionar |
| Sprint ejecutado con disciplina | 10 | Sprint Goal definido; movimiento del tablero distribuido en los días del sprint (no todo el último día); Sprint Review y Retrospectiva con evidencia de haber ocurrido |
| Flujo de Git respetado | 10 | `main` sin commits directos (solo vía merge de PR); ramas nombradas con la clave de Jira correspondiente; panel "Development" poblado en las historias trabajadas |

> **Sobre "Backlog bien construido" — dos cosas distintas que buscar:**
>
> **1. Tareas técnicas forzadas a formato de historia**
> - ❌ *"Como desarrollador, quiero configurar la conexión a la base de datos, para que el sistema funcione"* — nadie "quiere" configurar una base de datos; es trabajo necesario, no una funcionalidad con valor de negocio.
> - ✅ Lo mismo, registrado como issue tipo **Task**, con título plano: *"Configurar conexión inicial a base de datos"* — sin forzar el "Como \<rol\>...".
>
> **2. Dividir el trabajo por capa completa, en vez de por funcionalidad completa**
>
> Piénsalo como construir una casa: pueden construir **cuarto por cuarto** (una recámara completa — piso, paredes, techo, luz — ya se puede usar aunque el resto de la casa no exista) o pueden construir **por capas completas de toda la casa** (primero todos los cimientos, luego todas las paredes, luego todos los techos) — en este segundo caso, nadie puede vivir en ningún cuarto hasta que absolutamente todo esté terminado.
>
> - ❌ Historias como *"Como desarrollador, quiero crear todas las tablas de la base de datos"* o *"Como desarrollador, quiero construir toda la API"* — son capas completas, no funcionalidades. No hay demo real posible hasta que las tres "capas" (base de datos, lógica, interfaz) estén listas juntas, casi al final del sprint.
> - ✅ Una historia como *"Como recepcionista, quiero agendar una cita con nombre, mascota y horario, para evitar que se me olvide"* — ya necesita un poco de base de datos, un poco de lógica y un poco de interfaz, pero **solo lo justo para esa funcionalidad**. Es un "cuarto completo", no una "capa completa".
>
> **Prueba rápida al revisar cualquier historia:** *"Si la completo hoy, ¿le puedo mostrar algo funcionando a un usuario?"* Si la respuesta es "no, porque todavía falta la otra capa", ahí está la señal de alerta. (El término formal en la literatura de Scrum es "rebanada vertical vs. horizontal" — si les sirve más la imagen de la casa, úsenla; ambas describen lo mismo.)


**Niveles de desempeño por criterio:**
- **Completo (100% de los puntos):** la evidencia está presente y es consistente de principio a fin.
- **Parcial (50%):** la práctica se aplicó de forma inconsistente (ej. algunas historias sí tienen buen formato, otras no).
- **Ausente (0%):** no hay evidencia de que la práctica se haya aplicado.

---

## Dimensión B — Contribución Individual (60 puntos)

### Paso 0 — Verificación de trazabilidad (filtro previo, sin puntos propios)

Antes de la entrevista con el profesor, revise cada quien de manera individual:
```bash
git log --author="Nombre del alumno"
git shortlog -sn
```
...y las historias de Jira asignadas a esa persona.

Esto **no se cuantifica directamente**, es información de referencia que el profesor usa para decidir en qué commit o historia específica va a preguntar durante la entrevista, y como referencia de contraste: si el alumno describe trabajo que no aparece en ningún lado, y no logra explicarlo de forma convincente en la entrevista, **esto es una señal de alerta** (ver "Integridad académica" al final).

### Entrevista individual (2-3 minutos por persona)

**Se elige un commit, Pull Request o historia específica** que aparezca atribuida a la persona, y se hacen preguntas en tres niveles. 

**Nivel 1 — Comprensión (hasta 15 puntos)**
*¿Puede explicar qué hace su propio código?*

Preguntas ejemplo:
- "Explícame qué hace este fragmento línea por línea."
- "¿Qué historia de usuario resuelve este cambio?"
- "¿Por qué esta rama se llama así?"

**Nivel 2 — Justificación (hasta 20 puntos)**
*¿Puede defender por qué lo resolvió de esa manera?*

Preguntas ejemplo:
- "¿Por qué decidiste resolverlo así, y no de otra forma?"
- "¿Qué alternativa consideraste y por qué la descartaste?"
- "Si tu compañero hubiera hecho esta parte, ¿crees que la habría resuelto igual? ¿Por qué sí o no?"

**Nivel 3 — Metacognición (hasta 25 puntos)**
*¿Puede reflexionar sobre su propio proceso de aprendizaje?*

Preguntas ejemplo:
- "¿Cuál fue el momento más difícil de tu parte del sprint, y cómo lo resolviste?"
- "Si empezaras este sprint de nuevo, ¿qué harías distinto?"
- "¿Qué aprendiste haciendo esto que no sabías al iniciar el semestre?"
- (Si vivió un conflicto de fusión o un error real): "Cuéntame qué pasó y qué entendiste después de resolverlo."

### Escala de desempeño por nivel

| Nivel | Insuficiente | Suficiente | Excelente |
|---|---|---|---|
| 1. Comprensión (máx. 15) | 0–5 pts — No puede explicar su propio código | 6–10 pts — Explica qué hace, con ayuda o dudando | 11–15 pts — Explica con seguridad y precisión |
| 2. Justificación (máx. 20) | 0–6 pts — No puede argumentar por qué lo hizo así | 7–13 pts — Da una razón genérica, poco específica | 14–20 pts — Argumenta con criterio propio, considera alternativas reales |
| 3. Metacognición (máx. 25) | 0–8 pts — Respuestas vagas o memorizadas ("todo bien", "aprendí Git") | 9–16 pts — Identifica algo aprendido, aunque superficial | 17–25 pts — Reflexión genuina y específica sobre su propio proceso |

---

## Sobre integridad académica

Si la entrevista revela una discrepancia grave, como por ejemplo, un alumno no puede explicar en absoluto trabajo que la trazabilidad le atribuye, o al contrario, dice haber hecho algo que no existe evidencia de que hizo, se tratará como una conversación aparte del puntaje numérico, no solo como una resta de puntos. Puede ser un malentendido de asignación de tareas dentro del equipo, y no necesariamente mala fe. Es decir, hay oportunidad de aclarar con el profesor antes de restar puntos.
