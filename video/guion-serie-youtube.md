# 🎥 Serie YouTube — “Git y GitHub para programadores Java (DSY1102)”

[⬅️ Índice](../README.md)

Guion de producción para una **lista de reproducción de 6 episodios** (~75 min en total). Cada episodio sigue un módulo del curso para que el estudiante pueda alternar entre leer y ver.

| Ep. | Título | Duración | Módulo |
|:---:|--------|:--------:|:------:|
| 1 | Qué es Git y cómo instalarlo | 8 min | 0 |
| 2 | Tus primeros commits (las 3 áreas) | 14 min | 1 |
| 3 | Ramas y conflictos sin miedo | 15 min | 2 |
| 4 | Sube tu proyecto a GitHub | 12 min | 3 |
| 5 | Trabajo en equipo con Pull Requests | 14 min | 4 |
| 6 | Git en IntelliJ + cómo deshacer errores | 12 min | 5, 6 |

---

## 🎬 Notas de producción (para todos los episodios)

- **Grabación:** OBS Studio, 1920×1080, 30 fps. Micrófono con filtro de ruido.
- **Terminal:** fuente 20–22 pt, tema oscuro de alto contraste, prompt corto (ej. `PS1='\W $(__git_ps1 "(%s)")\$ '` en Git Bash para mostrar la rama).
- **IntelliJ:** *Presentation Mode* (`View → Appearance → Enter Presentation Mode`) o fuente del editor ≥ 18 pt. Activa un plugin de atajos visibles (p. ej. *Presentation Assistant*) para que se vean los atajos en pantalla.
- **Layout recomendado:** terminal a la izquierda, IntelliJ o navegador a la derecha; webcam pequeña en esquina (opcional).
- **Proyecto demo:** `biblioteca-poo` (el mismo de los laboratorios). Prepara un repo de respaldo con cada estado listo por si algo falla en vivo.
- **Gráficos:** reutiliza los diagramas Mermaid del curso (expórtalos como PNG desde <https://mermaid.live>).
- **Cierre estándar de cada video:** “El material escrito y los laboratorios están en el repositorio del curso; el link está en la descripción. Nos vemos en el siguiente episodio.”
- **Accesibilidad:** sube subtítulos en español (revisa los automáticos de YouTube; corrigen mal “commit”, “merge”, “push”).

Formato de los guiones: **⏱ Tiempo · 🖥 En pantalla · 🎙 Narración**.

---

## Episodio 1 — Qué es Git y cómo instalarlo (8 min)

**Objetivo:** que el estudiante entienda para qué sirve Git, la diferencia con GitHub y lo deje instalado y configurado.

| ⏱ | 🖥 En pantalla | 🎙 Narración (guía, no textual) |
|---|----------------|--------------------------------|
| 0:00 | Carpeta con `Proyecto_final.zip`, `Proyecto_final_v2.zip`, `Proyecto_final_AHORASI.zip` | “¿Te ha pasado esto? Tienes cinco versiones de tu proyecto y no sabes cuál es la buena. Hoy eso se termina.” |
| 0:25 | Título animado de la serie | “Bienvenidos a la serie de Git y GitHub para DSY1102. En seis videos vas a pasar de cero a trabajar en equipo como en una empresa de software.” |
| 0:45 | Diagrama: cámara (Git) vs. álbum en la nube (GitHub) | “Primero, Git y GitHub no son lo mismo. Git es un programa en tu computador que saca ‘fotos’ de tu proyecto. GitHub es un sitio donde guardas y compartes esas fotos.” |
| 1:45 | Perfil de GitHub de ejemplo con gráfico de contribuciones | “Además, tu perfil de GitHub es tu portafolio: es lo primero que mira un reclutador técnico.” |
| 2:15 | Navegador en git-scm.com → instalador Windows | Instalación paso a paso. Detenerse en: editor por defecto y **nombre de rama inicial = main**. |
| 4:15 | Terminal macOS/Linux (rápido) | “Si usas Mac o Linux, es un solo comando.” Mostrar `brew install git` / `apt install git`. |
| 4:45 | Git Bash: `git --version` | “Comprobamos que quedó instalado.” |
| 5:15 | `git config --global user.name ...` / `user.email` / `init.defaultBranch main` | “Le decimos a Git quiénes somos. Ojo: usa el mismo correo que vas a usar en GitHub.” |
| 6:30 | github.com/signup; luego Settings → 2FA | “Creamos la cuenta. Elige un usuario profesional. Activa la verificación en dos pasos: GitHub la exige.” |
| 7:30 | Pantalla de cierre con checklist del Módulo 0 | “Tarea: deja Git instalado y configurado. En el próximo video hacemos nuestros primeros commits.” |

---

## Episodio 2 — Tus primeros commits: las 3 áreas de Git (14 min)

**Objetivo:** dominar `init`, `status`, `add`, `commit`, `log`, `diff` y `.gitignore`.

| ⏱ | 🖥 En pantalla | 🎙 Narración |
|---|----------------|--------------|
| 0:00 | Teaser: `git log --oneline` con un historial limpio | “Al final de este video vas a tener un historial así de tu propio proyecto.” |
| 0:30 | Diagrama animado de las 3 áreas (escritorio → caja → archivo histórico) | **Concepto clave del video.** Explicar con la analogía de enviar una encomienda: preparas la caja (`add`) y la sellas (`commit`). |
| 2:30 | IntelliJ: crear proyecto `biblioteca-poo`; abrir terminal integrada | “Creamos un proyecto Java normal. Ahora lo convertimos en repositorio.” |
| 3:15 | `git init` → `ls -a` mostrando `.git` | “Esta carpeta oculta es el cerebro. Nunca la borres.” |
| 3:45 | `git status` | “Este es el comando que más vas a usar. Léelo con calma: Git siempre te dice qué hacer.” |
| 4:30 | Crear `.gitignore`; `git status` antes y después (desaparece `out/`) | “Antes del primer commit, le decimos a Git qué NO guardar: los `.class` y la carpeta `out`.” |
| 6:00 | Crear `Libro.java` → `git add` → `git status` (verde) → `git commit -m` | Mostrar cada transición de color. “Rojo: Git lo ve pero no lo sigue. Verde: está en la caja.” |
| 8:00 | Modificar `Libro` (agregar `isbn`) → `git diff` → `git add` → `git diff --staged` | “`diff` te muestra lo que cambiaste; con `--staged`, lo que va a entrar en el commit.” |
| 10:00 | `git log`, `git log --oneline`, `git show <hash>` | “Cada commit tiene un identificador único, autor, fecha y mensaje.” |
| 11:30 | Pantalla dividida: mensajes malos vs. buenos | “‘cambios’ no le sirve a nadie. Usa verbos en imperativo: ‘Agrega clase Libro’.” |
| 13:00 | Resumen de comandos + link al Lab 1 | “Ahora te toca a ti: haz el Laboratorio 1.” |

---

## Episodio 3 — Ramas y conflictos sin miedo (15 min)

**Objetivo:** crear y fusionar ramas; provocar y resolver un conflicto.

| ⏱ | 🖥 En pantalla | 🎙 Narración |
|---|----------------|--------------|
| 0:00 | Grafo de ramas animado | “Las ramas son la superpotencia de Git: te permiten experimentar sin romper nada.” |
| 0:45 | Analogía: universos paralelos / líneas de tiempo | “Una rama es una línea de tiempo alternativa de tu proyecto.” |
| 1:45 | `git branch`, `git switch -c feature/material-abstracto` | Explicar convención de nombres `feature/`, `fix/`. |
| 3:00 | IntelliJ: crear clase abstracta `Material`; `Libro extends Material` → commits | Vincular con POO: “Justo lo que están viendo en herencia.” |
| 5:00 | `git switch main` → el archivo `Material.java` desaparece del árbol de IntelliJ | **Momento “wow”**: pausa. “No se borró: vive en la otra rama.” |
| 6:00 | `git merge feature/material-abstracto` → fast-forward; `git log --graph` | Explicar fast-forward con el diagrama. |
| 7:30 | Crear rama `fix/tostring-libro`; editar `toString()` distinto en ambas ramas | “Ahora vamos a provocar el famoso conflicto a propósito.” |
| 9:00 | `git merge` → mensaje `CONFLICT` en rojo | “Tranquilidad. Un conflicto no es un error: es Git preguntándote cuál versión quieres.” |
| 9:45 | Zoom a los marcadores `<<<<<<<`, `=======`, `>>>>>>>` | Explicar cada marcador. |
| 11:00 | Editar a mano, borrar marcadores, compilar, `git add`, `git commit` | “Cuatro pasos: decidir, borrar marcadores, probar, add + commit.” |
| 12:30 | `git log --oneline --graph --all` con el commit de merge | “Este commit tiene dos padres: une las dos historias.” |
| 13:15 | `git merge --abort` (demostración rápida) | “Y si te arrepientes en medio del conflicto, esto vuelve todo atrás.” |
| 14:00 | Tips para evitar conflictos + link al Lab 2 | |

---

## Episodio 4 — Sube tu proyecto a GitHub (12 min)

**Objetivo:** autenticarse, hacer `push`, `clone`, `pull` y entender el rechazo por *fetch first*.

| ⏱ | 🖥 En pantalla | 🎙 Narración |
|---|----------------|--------------|
| 0:00 | Diagrama local ↔ remoto ↔ compañero | “Hasta ahora todo vive en tu PC. Si se te cae el notebook al agua, pierdes todo. Vamos a la nube.” |
| 1:00 | Aviso: “GitHub ya no acepta tu contraseña en la terminal” | Mostrar las 3 opciones; demostrar **Git Credential Manager** (Windows) o `gh auth login`. |
| 3:00 | GitHub → New repository (sin README) | “Lo creamos vacío porque ya tenemos historial local.” |
| 4:00 | `git remote add origin`, `git remote -v`, `git push -u origin main` | “`origin` es solo un apodo para la URL.” |
| 5:00 | Recargar GitHub: archivos y commits | “Todo el historial está arriba, no solo los archivos.” |
| 5:45 | Editar README desde la web → `git fetch` → `git status` (behind) → `git pull` | Diferencia entre `fetch` y `pull`. |
| 7:30 | `git clone` en otra carpeta (“PC 2”) → commit → push | “Simulemos que trabajo desde el PC del laboratorio.” |
| 9:00 | En carpeta original: commit → `git push` → **rejected** | “Este es el error más común del semestre. Léelo: ‘fetch first’.” |
| 10:00 | `git pull` → `git push` ✅ | “Primero traes, después subes.” Advertencia sobre `--force`. |
| 11:00 | Insights → Network | Mostrar el grafo. Link al Lab 3. |

---

## Episodio 5 — Trabajo en equipo con Pull Requests (14 min)

**Objetivo:** aplicar GitHub Flow con colaboradores, issues, PR y code review.

> 🎭 Recomendación: graba con **dos cuentas de GitHub** (o con un ayudante) en dos navegadores para mostrar autor y revisor.

| ⏱ | 🖥 En pantalla | 🎙 Narración |
|---|----------------|--------------|
| 0:00 | Meme / escena: “¿quién me pasa el zip con lo último?” | “Basta de zips por WhatsApp. Así trabajan los equipos de verdad.” |
| 0:45 | Diagrama GitHub Flow | Explicar los 7 pasos. “Regla: nadie sube directo a `main`.” |
| 2:00 | Settings → Collaborators; Settings → Branches (protección de `main`) | “El líder del repo invita al equipo y protege `main`.” |
| 3:30 | Issues: crear 3 issues y asignarlos | “Repartimos el diagrama de clases en tareas.” |
| 4:30 | Cuenta “Integrante B”: clone, `switch -c feature/socio`, commits, push | |
| 6:00 | Botón “Compare & pull request”; escribir descripción con `Closes #2` | “Un buen PR explica qué, por qué y cómo probarlo.” |
| 7:30 | Cuenta “Revisor”: Files changed → comentar línea → Request changes | Mostrar checklist de POO: encapsulamiento, nombres, herencia. Tono respetuoso. |
| 9:30 | Autor corrige, push, PR se actualiza solo → Approve | “No se abre un PR nuevo: se sigue empujando a la misma rama.” |
| 10:45 | Merge (explicar *Squash and merge*) → Delete branch → issue cerrado automáticamente | |
| 12:00 | Terminal de los demás: `git switch main && git pull`; `git merge main` en su rama | “Después de cada merge, todos actualizan.” |
| 13:00 | Insights → Contributors | “Así ve el profe quién aportó qué.” Link al Lab 4 y rúbrica. |

---

## Episodio 6 — Git en IntelliJ + cómo deshacer errores (12 min)

**Objetivo:** usar Git desde IntelliJ y conocer las herramientas para deshacer.

| ⏱ | 🖥 En pantalla | 🎙 Narración |
|---|----------------|--------------|
| 0:00 | IntelliJ con archivos en colores | “Todo lo que hicimos en la terminal también se puede hacer acá, y algunas cosas incluso mejor.” |
| 0:30 | Settings → Version Control → GitHub → Log In | |
| 1:15 | Colores de archivos (rojo, verde, azul) | |
| 2:00 | `Ctrl+K`: ventana Commit, doble clic para diff, marcar archivos | “Las casillas son tu staging area.” |
| 3:30 | `Ctrl+Shift+K` push, `Ctrl+T` update project | |
| 4:15 | Widget de ramas: nueva rama, checkout, merge | |
| 5:15 | Provocar conflicto → herramienta de 3 paneles → Apply | **Destacar**: “Para conflictos, esto es mucho más cómodo que la terminal.” |
| 7:00 | `Alt+9` Log; Annotate with Git Blame | |
| 8:00 | Diagrama de decisión “¿qué quiero deshacer?” | Pasar por `restore`, `restore --staged`, `--amend`, `reset --soft`, `revert`. |
| 9:30 | Demo `git revert` sobre un commit publicado | “Lo publicado se revierte, no se borra.” |
| 10:15 | Demo `git stash` → cambiar de rama → `stash pop` | |
| 11:00 | Demo `reset --hard` → “pánico” → `git reflog` → recuperar | “Git casi nunca olvida.” |
| 11:40 | Los 10 mandamientos + despedida de la serie | “Ya tienes todo para trabajar como profesional. Nos vemos en GitHub.” |

---

## 📋 Metadatos para YouTube

### Lista de reproducción

- **Título:** Git y GitHub para programadores Java | DSY1102
- **Descripción:** Curso práctico de Git y GitHub para estudiantes de Programación Orientada a Objetos. Desde la instalación hasta el trabajo en equipo con Pull Requests, usando la terminal e IntelliJ IDEA. Material escrito y laboratorios: `https://github.com/donkiwicl/curso-git-github-dsy1102`

### Títulos sugeridos (≤ 60 caracteres)

1. `Git desde cero: qué es y cómo instalarlo | Ep. 1`
2. `Tus primeros commits en Git (las 3 áreas) | Ep. 2`
3. `Ramas y conflictos en Git sin miedo | Ep. 3`
4. `Sube tu proyecto Java a GitHub | Ep. 4`
5. `Pull Requests: trabajo en equipo en GitHub | Ep. 5`
6. `Git en IntelliJ y cómo deshacer errores | Ep. 6`

### Plantilla de descripción (ejemplo Ep. 3)

```text
Aprende a usar ramas en Git para desarrollar nuevas funcionalidades sin romper tu proyecto, y a resolver conflictos de merge paso a paso. Ejemplo práctico con herencia en Java (clase abstracta Material).

📚 Material escrito: https://github.com/donkiwicl/curso-git-github-dsy1102/blob/main/modulos/02-ramas-merge-conflictos.md
🧪 Laboratorio 2: https://github.com/donkiwicl/curso-git-github-dsy1102/blob/main/laboratorios/lab-02-ramas.md
📄 Cheatsheet: https://github.com/donkiwicl/curso-git-github-dsy1102/blob/main/recursos/cheatsheet.md

⏱ Capítulos
00:00 Qué son las ramas
01:45 Crear y cambiar de rama
03:00 Herencia en una rama aparte
05:00 ¿Dónde está mi archivo?
06:00 Merge fast-forward
07:30 Provocando un conflicto
09:45 Anatomía de un conflicto
11:00 Resolver el conflicto
12:30 El commit de merge
13:15 git merge --abort
14:00 Cómo evitar conflictos

▶️ Episodio anterior: <link Ep. 2>
▶️ Siguiente episodio: <link Ep. 4>

#git #github #java #programacion #intellij
```

> ⚠️ YouTube solo crea capítulos si el primero empieza en `00:00`, hay al menos 3 y cada uno dura ≥ 10 segundos. Ajusta los tiempos al video final editado.

### Tags

`git, github, git tutorial español, git desde cero, github para principiantes, java, intellij idea, control de versiones, pull request, merge conflict, ramas git, programación orientada a objetos, DSY1102`

### Miniaturas (texto corto, alto contraste)

| Ep. | Texto principal | Elemento visual |
|:---:|-----------------|-----------------|
| 1 | **¿QUÉ ES GIT?** | Logo Git + carpeta con zips tachados |
| 2 | **TU PRIMER COMMIT** | Diagrama 3 cajas |
| 3 | **CONFLICTOS 😱→😎** | Marcadores `<<<<<<<` en rojo |
| 4 | **A LA NUBE ☁️** | Flecha laptop → GitHub |
| 5 | **TRABAJO EN EQUIPO** | Botón verde “Merge pull request” |
| 6 | **CTRL+Z EN GIT** | Logo IntelliJ + flecha circular |

> Usa el logo oficial de Git según su [política de uso](https://git-scm.com/downloads/logos) y evita usar el logo de GitHub de forma que sugiera respaldo oficial.
