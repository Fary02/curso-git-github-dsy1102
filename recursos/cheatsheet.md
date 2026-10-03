# 📄 Cheatsheet de Git — DSY1102

[⬅️ Índice](../README.md)

## Configuración (una vez)

```bash
git config --global user.name "Nombre Apellido"
git config --global user.email "correo@ejemplo.com"
git config --global init.defaultBranch main
```

## Crear / obtener un repositorio

| Comando | Descripción |
|---------|-------------|
| `git init` | Crea un repositorio en la carpeta actual |
| `git clone <url>` | Copia un repositorio remoto |

## Día a día

| Comando | Descripción |
|---------|-------------|
| `git status` | Estado actual (úsalo siempre) |
| `git add <archivo>` / `git add .` | Pasar cambios al staging |
| `git commit -m "mensaje"` | Guardar una versión |
| `git commit -am "mensaje"` | `add` + `commit` de archivos **ya rastreados** |
| `git diff` | Cambios sin staging |
| `git diff --staged` | Cambios en staging |
| `git log --oneline --graph --all` | Historial con ramas |
| `git show <hash>` | Detalle de un commit |

## Ramas

| Comando | Descripción |
|---------|-------------|
| `git branch` | Listar ramas |
| `git switch -c <rama>` | Crear y cambiarse |
| `git switch <rama>` | Cambiarse |
| `git merge <rama>` | Traer `<rama>` a la actual |
| `git merge --abort` | Cancelar merge con conflictos |
| `git branch -d <rama>` | Borrar rama fusionada |

## Remotos (GitHub)

| Comando | Descripción |
|---------|-------------|
| `git remote add origin <url>` | Conectar con GitHub |
| `git push -u origin <rama>` | Primer push de una rama |
| `git push` | Subir commits |
| `git pull` | Traer y fusionar |
| `git fetch` | Traer sin fusionar |
| `git push origin --delete <rama>` | Borrar rama remota |

## Deshacer

| Situación | Comando |
|-----------|---------|
| Descartar cambios de un archivo | `git restore <archivo>` |
| Sacar del staging | `git restore --staged <archivo>` |
| Corregir último commit (sin push) | `git commit --amend` |
| Deshacer último commit, conservar cambios | `git reset --soft HEAD~1` |
| Deshacer commit publicado | `git revert <hash>` |
| Guardar trabajo a medias | `git stash` / `git stash pop` |
| Encontrar commits “perdidos” | `git reflog` |

## Etiquetas (versiones / entregas)

| Comando | Descripción |
|---------|-------------|
| `git tag -a v1.0 -m "Entrega 1"` | Crear etiqueta anotada |
| `git push origin v1.0` | Subir la etiqueta |
| `git tag` | Listar etiquetas |

## IntelliJ IDEA (Windows/Linux)

| Acción | Atajo |
|--------|-------|
| Commit | `Ctrl+K` |
| Commit and Push | `Ctrl+Alt+K` |
| Push | `Ctrl+Shift+K` |
| Update Project (pull) | `Ctrl+T` |
| Rollback | `Ctrl+Alt+Z` |
| Ventana Git (Log) | `Alt+9` |
| Terminal | `Alt+F12` |

## Flujo de trabajo en equipo (GitHub Flow)

```bash
git switch main && git pull
git switch -c feature/mi-tarea
# ...código... 
git add . && git commit -m "Agrega ..."
git push -u origin feature/mi-tarea
# → Abrir Pull Request en GitHub → Review → Merge
git switch main && git pull
git branch -d feature/mi-tarea
```
