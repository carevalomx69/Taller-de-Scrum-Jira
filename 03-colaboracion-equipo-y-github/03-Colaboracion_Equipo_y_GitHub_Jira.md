# Colaboración en Equipo y Conexión con GitHub
### Taller de Jira — tercera sesión

Ya tienen, de las sesiones anteriores: su sitio de Jira en equipo, historias escritas, y al menos un sprint corrido. Del taller de Git ya tienen también: su repositorio compartido con el proyecto de práctica del sistema de inscripción. Esta sesión conecta ambas cosas.

## 1. Conectando Jira con GitHub

Un integrante del equipo (con permisos de administrador tanto del sitio de Jira como de la organización/cuenta de GitHub del repositorio) instala la app gratuita **"GitHub for Jira"**:

- Desde Jira: configuración del proyecto → Apps → buscar "GitHub for Jira".
- Sigan el flujo de autorización — les va a pedir confirmar acceso al repositorio de GitHub del equipo.

Esto se hace **una sola vez por equipo**.

## 2. La convención que lo conecta todo: la clave de Jira en el nombre de la rama

Cada historia en Jira tiene una clave única (ej. `SIE-13` — la tuya puede ser distinta, según cómo hayan nombrado su proyecto). Cuando nombran su rama incluyendo esa clave:

```bash
git checkout -b SIE-13-tabla-alumnos
```

...esa rama, sus commits y su Pull Request aparecen **automáticamente** dentro de esa historia en Jira, en un panel llamado **"Development"** — sin captura manual, sin mantener dos tableros sincronizados a mano.

## 3. Práctica: recreen sus 4 tareas del taller de Git, ahora con trazabilidad completa

Van a repetir el mismo ejercicio de branches que ya hicieron (tabla de alumnos, lista de materias, validación del formulario, paleta de colores) — pero esta vez, cada tarea nace primero como historia en Jira.

1. **Cada integrante crea su historia correspondiente en el Backlog de Jira**, con el formato que ya conocen: *"Como \<rol\>, quiero \<acción\>, para \<beneficio\>"*. Por ejemplo: *"Como administrador, quiero ver una tabla de alumnos, para consultar rápidamente quién está inscrito."*
2. **Anoten la clave** que Jira le asigna automáticamente a cada historia (ej. `SIE-13`, `SIE-14`, `SIE-15`, `SIE-16`). **Dónde encontrarla:** aparece sola, a la izquierda del texto de la historia, en la misma fila de la lista del Backlog — no hay que generarla ni buscarla en ningún otro lado. También la ven arriba del todo si abren la historia (clic sobre su texto), y al final de la URL del navegador cuando la tienen abierta (termina en algo como `.../browse/SIE-13`). En varias vistas, al pasar el mouse sobre la clave aparece un ícono de copiar — mejor usarlo que transcribirla a mano, para evitar errores de dedo (si la clave no coincide exactamente entre la rama y Jira, el panel Development se queda vacío).
3. **Creen su rama usando esa clave** al inicio del nombre:
   ```bash
   git checkout main
   git pull
   git checkout -b SIE-13-tabla-alumnos
   ```
4. Trabajen, hagan commit y suban su rama exactamente como ya saben:
   ```bash
   git add .
   git commit -m "SIE-13 agrega tabla de alumnos de ejemplo"
   git push origin SIE-13-tabla-alumnos
   ```
5. **En cuanto suban (`push`) su rama, ya pueden verla reflejada en Jira** — no hace falta esperar al Pull Request. Abran la historia con **clic izquierdo directo sobre su texto** (no clic derecho — ese solo abre un menú de acciones rápidas como mover o copiar clave, nunca el panel de Development). En la vista completa de la historia, en el panel lateral, van a ver una sección **"Desarrollo"** con su rama ya listada.
6. Abran el Pull Request en GitHub, como siempre.
7. **Regresen a esa misma sección "Desarrollo" de la historia** — ahora también debe aparecer el Pull Request, junto a la rama.

**Otra forma de verificar, a nivel de todo el equipo:** en la barra superior del espacio de Jira, agreguen la pestaña **"Desarrollo"** con el botón `+` (si no aparece por default). Ahí, en la sub-pestaña "Solicitudes de extracción", verán todos los Pull Requests vinculados de las últimas semanas, de todas las historias del equipo — útil para que alguien del equipo revise de un vistazo el avance de todos, no historia por historia.

**Si no ven nada en ninguna de las dos vistas:** lo más común es que la clave (`SIE-13`) no haya quedado exactamente igual en el nombre de la rama o en el mensaje del commit — revisen que no haya espacios ni errores de dedo. También recuerden que la rama aparece primero (en cuanto hacen `push`); el Pull Request tarda un paso más en reflejarse, así que si acaban de subir la rama y todavía no ven el PR, es normal — ábranlo y esperen unos segundos.

## 4. Cerrando el ciclo completo

Cuando el Pull Request se fusione (con revisión de un compañero, como ya practicaron), regresen a Jira y muevan esa historia a **"Done"** en el tablero. Ese movimiento es, literalmente, el Incremento de esa historia quedando reflejado.

## 5. Opcional, si les da tiempo: agreguen a su cliente real

Como el plan gratuito permite hasta 10 usuarios por sitio, si su equipo es de 4-6 integrantes, todavía hay margen para invitar a su cliente real como colaborador — viendo y priorizando el Backlog directamente, no solo en la Sprint Review.

### ✅ Checkpoint de esta sesión

Cada equipo debe poder mostrar al menos una historia en Jira cuyo panel "Development" muestre la rama, el commit y el Pull Request correspondientes, ya vinculados.

---

*Con esto se cierra el recorrido completo: la intención del cliente (historia en Jira) hasta el código real (GitHub) y de vuelta a un incremento verificable.*
