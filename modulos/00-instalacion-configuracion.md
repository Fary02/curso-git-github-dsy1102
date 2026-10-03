# Módulo 0 — Instalación y configuración

⏱️ 20 minutos · [⬅️ Índice](../README.md) · [Siguiente ➡️](01-fundamentos.md)

## Objetivos

- Instalar Git en tu sistema operativo.
- Configurar tu identidad (nombre y correo).
- Crear tu cuenta en GitHub.

---

## 1. ¿Git o GitHub? No son lo mismo

| Git | GitHub |
|-----|--------|
| Programa que se instala en **tu computador** | Sitio web / servicio en **la nube** |
| Guarda el historial de versiones de tu proyecto | Aloja repositorios Git para compartirlos |
| Funciona sin internet | Necesita internet |
| Creado por Linus Torvalds (2005) | Empresa (hoy parte de Microsoft) |

> 💡 Analogía: **Git** es como la cámara que saca fotos de tu proyecto; **GitHub** es el álbum en la nube donde las compartes con tu equipo.

## 2. Instalar Git

### Windows

1. Descarga el instalador desde <https://git-scm.com/download/win>.
2. Durante la instalación, deja las opciones por defecto, salvo:
   - **Default editor**: elige *Visual Studio Code* o *Notepad* si no te manejas con Vim.
   - **Initial branch name**: elige *Override… → `main`*.
3. Esto instala también **Git Bash** (una terminal tipo Linux) y **Git Credential Manager** (para iniciar sesión en GitHub).

### macOS

```bash
xcode-select --install     # instala Git junto a las herramientas de desarrollo
# o, si usas Homebrew:
brew install git
```

### Linux (Ubuntu/Debian)

```bash
sudo apt update && sudo apt install git
```

### Verifica

```bash
git --version
# git version 2.4x.x
```

## 3. Configurar tu identidad

Cada commit lleva tu nombre y correo. **Usa el mismo correo que en GitHub** para que tus commits aparezcan en tu perfil.

```bash
git config --global user.name "Nombre Apellido"
git config --global user.email "tu-correo@ejemplo.com"
git config --global init.defaultBranch main
```

Opcional, pero recomendado:

```bash
git config --global core.autocrlf true     # solo en Windows: evita líos de fin de línea
git config --global core.autocrlf input    # en macOS/Linux
git config --global pull.rebase false      # pull hace merge (comportamiento más predecible al aprender)
```

Revisa tu configuración:

```bash
git config --list --global
```

## 4. Crear tu cuenta de GitHub

1. Entra a <https://github.com/signup>.
2. Usa un **nombre de usuario profesional** (ej. `jperez-dev`, no `xXjuanitoGamerXx`). Este perfil lo verán futuros empleadores.
3. Activa la **autenticación de dos factores (2FA)**: GitHub la exige para cuentas que contribuyen código.
4. 💡 Si eres estudiante, solicita el **GitHub Student Developer Pack** en <https://education.github.com/pack> (beneficios gratuitos, incluido GitHub Copilot y licencias de IDE).

## Errores frecuentes

| Síntoma | Causa | Solución |
|---------|-------|----------|
| `git: command not found` / `'git' no se reconoce…` | Git no está en el PATH | Reinicia la terminal o reinstala marcando “Git from the command line” |
| Commits aparecen sin tu foto en GitHub | El `user.email` no coincide con tu cuenta | Agrega ese correo en *GitHub → Settings → Emails* o cambia `user.email` |
| Se abre Vim y no sabes salir | Editor por defecto | Escribe `:q!` y Enter. Luego `git config --global core.editor "code --wait"` |

## ✅ Checkpoint

- [ ] `git --version` muestra una versión.
- [ ] `git config user.name` y `git config user.email` devuelven tus datos.
- [ ] Tienes cuenta en GitHub con 2FA activado.
