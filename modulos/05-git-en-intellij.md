# Módulo 5 — Git en IntelliJ IDEA

⏱️ 45 minutos · [⬅️ Anterior](04-colaboracion-pull-requests.md) · [Índice](../README.md) · [Siguiente ➡️](06-deshacer-y-buenas-practicas.md)

## Objetivos

- Hacer desde IntelliJ todo lo que aprendiste por terminal.
- Usar la herramienta visual para resolver conflictos.
- Saber cuándo conviene el IDE y cuándo la terminal.

> ℹ️ Las rutas de menú corresponden a la **nueva interfaz** de IntelliJ IDEA (2023.x en adelante). En la interfaz clásica el menú se llama **VCS** en lugar de **Git**. Los atajos son de Windows/Linux; en macOS cambia `Ctrl` por `⌘`.

---

## 1. Conectar tu cuenta de GitHub

**File → Settings → Version Control → GitHub → `+` → Log In via GitHub…** Se abre el navegador, autorizas y listo.

Verifica también que IntelliJ encuentre Git: **Settings → Version Control → Git → Path to Git executable → Test**.

## 2. Crear o abrir un repositorio

| Quiero… | En IntelliJ |
|---------|-------------|
| Convertir mi proyecto en repo (`git init`) | **VCS → Create Git Repository…** (o en el widget superior *Version control → Create Git Repository*) |
| Publicar mi proyecto en GitHub (crea repo + push) | **Git → GitHub → Share Project on GitHub** |
| Clonar un repo (`git clone`) | **File → New → Project from Version Control…** → pega la URL |

## 3. La ventana Commit (`Ctrl+K`)

Equivale a `git status` + `git add` + `git commit`:

- Los archivos modificados aparecen en **Changes**; los nuevos en **Unversioned Files**.
- Marca con ✔️ los archivos que quieres incluir (eso es el *staging*).
- Escribe el mensaje y presiona **Commit**, o **Commit and Push…** (`Ctrl+Alt+K`).

Colores de los nombres de archivo en el árbol del proyecto:

| Color | Significado |
|-------|-------------|
| ⚪ Blanco/negro | Sin cambios |
| 🔵 Azul | Modificado |
| 🟢 Verde | Nuevo, agregado a Git |
| 🔴 Rojo | Nuevo, **no** agregado a Git (untracked) |
| 🟤 Gris/oliva | Ignorado por `.gitignore` |

> 💡 Haz doble clic sobre un archivo en la ventana Commit para ver el **diff** lado a lado antes de confirmar.

## 4. Push, pull y fetch

| Terminal | IntelliJ | Atajo |
|----------|----------|-------|
| `git push` | **Git → Push…** | `Ctrl+Shift+K` |
| `git pull` | **Git → Update Project…** (elige *Merge*) | `Ctrl+T` |
| `git fetch` | **Git → Fetch** | — |

## 5. Ramas

El **widget de ramas** está arriba a la izquierda, junto al nombre del proyecto (muestra `main`). Al hacer clic:

- **New Branch…** → equivale a `git switch -c`.
- Clic sobre una rama → **Checkout** (cambiarse), **Merge into Current**, **Delete**, **Push…**

## 6. Resolver conflictos

Cuando un merge o pull produce conflictos, IntelliJ abre **Conflicts**:

1. Selecciona el archivo → **Merge…**
2. Verás **tres paneles**:
   - **Izquierda**: tu versión (*Yours*, rama actual).
   - **Derecha**: la versión entrante (*Theirs*).
   - **Centro**: el resultado final.
3. Usa las flechas `>>` / `<<` para aceptar cada bloque, o edita el centro a mano.
4. **Apply**. IntelliJ hace el `git add` por ti; luego haz commit.

> 💡 El botón con la varita mágica (**Apply all non-conflicting changes**) resuelve automáticamente las partes sin conflicto.

## 7. Historial y anotaciones

- **Ventana Git** (`Alt+9`) → pestaña **Log**: el equivalente gráfico de `git log --graph --all`. Puedes filtrar por rama, autor o fecha.
- **Clic derecho en el número de línea → Annotate with Git Blame**: muestra quién y en qué commit modificó cada línea.
- **Clic derecho en un archivo → Git → Show History**: historial de ese archivo.

## 8. Deshacer desde el IDE

| Terminal | IntelliJ |
|----------|----------|
| `git restore <archivo>` | En la ventana Commit, clic derecho → **Rollback** (`Ctrl+Alt+Z`) |
| `git revert <hash>` | En Log, clic derecho sobre el commit → **Revert Commit** |
| `git commit --amend` | Casilla **Amend** en la ventana Commit |
| `git stash` | **Git → Uncommitted Changes → Stash Changes…** |

> 💡 IntelliJ además tiene **Local History** (clic derecho → *Local History → Show History*), una red de seguridad independiente de Git que guarda cambios aunque no hayas hecho commit.

## 9. Pull Requests sin salir del IDE

Con la cuenta de GitHub conectada, **Git → GitHub → Create Pull Request** abre el PR, y la herramienta **Pull Requests** permite revisarlos y comentarlos. Es opcional: hacerlo en la web también está perfecto.

## ¿Terminal o IDE?

| Usa IntelliJ para… | Usa la terminal para… |
|---------------------|----------------------|
| Commits diarios y ver diffs | Entender qué está pasando realmente |
| Resolver conflictos (visual) | Operaciones menos comunes (`reset`, `reflog`) |
| Ver historial y blame | Servidores sin interfaz gráfica |
| | Cuando el IDE muestra un error confuso |

**Recomendación:** aprende con la terminal, trabaja con lo que te resulte más productivo. Y si el IDE hace algo raro, `git status` en la terminal te dirá la verdad.

## ✅ Checkpoint

- [ ] Hiciste un commit con `Ctrl+K` revisando el diff antes.
- [ ] Creaste una rama desde el widget de ramas y la subiste con `Ctrl+Shift+K`.
- [ ] Resolviste un conflicto con la herramienta de 3 paneles.
