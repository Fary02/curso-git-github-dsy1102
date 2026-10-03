# Curso de Git y GitHub — DSY1102 Programación Orientada a Objetos

> Aprende a versionar tus proyectos Java, trabajar en equipo y entregar tus evaluaciones como lo hace un equipo de desarrollo profesional.

![Nivel](https://img.shields.io/badge/nivel-básico--intermedio-blue)
![Duración](https://img.shields.io/badge/duración-3%20sesiones-green)
![Herramientas](https://img.shields.io/badge/herramientas-Git%20CLI%20%7C%20IntelliJ%20IDEA-orange)

## ¿Por qué Git en un curso de POO?

En DSY1102 vas a construir proyectos Java con varias clases, paquetes y, en algunos casos, en equipo. Git te permite:

- **No perder trabajo nunca más**: cada versión de tu proyecto queda guardada.
- **Experimentar sin miedo**: prueba una nueva clase o refactoriza en una rama; si sale mal, vuelves atrás.
- **Trabajar en equipo** sin pasarse archivos `.zip` por WhatsApp.
- **Construir tu portafolio**: tu perfil de GitHub es tu carta de presentación como desarrollador.

## Contenido

| # | Módulo | Qué aprendes | Sesión |
|---|--------|--------------|:------:|
| 0 | [Instalación y configuración](modulos/00-instalacion-configuracion.md) | Instalar Git, configurar identidad, crear cuenta GitHub | 1 |
| 1 | [Fundamentos de Git](modulos/01-fundamentos.md) | Las 3 áreas, `init`, `add`, `commit`, `log`, `diff`, `.gitignore` | 1 |
| 2 | [Ramas, merge y conflictos](modulos/02-ramas-merge-conflictos.md) | `branch`, `switch`, `merge`, resolver conflictos | 2 |
| 3 | [GitHub y repositorios remotos](modulos/03-github-remotos.md) | `remote`, `push`, `pull`, `clone`, autenticación | 2 |
| 4 | [Colaboración con Pull Requests](modulos/04-colaboracion-pull-requests.md) | GitHub Flow, PR, code review, issues | 3 |
| 5 | [Git en IntelliJ IDEA](modulos/05-git-en-intellij.md) | Todo lo anterior desde el IDE | 3 |
| 6 | [Deshacer cambios y buenas prácticas](modulos/06-deshacer-y-buenas-practicas.md) | `restore`, `revert`, `reset`, `stash`, mensajes de commit | 3 |

### Laboratorios prácticos

| Lab | Descripción | Módulos |
|-----|-------------|---------|
| [Lab 1](laboratorios/lab-01-primer-repositorio.md) | Tu primer repositorio: proyecto `biblioteca-poo` | 0, 1 |
| [Lab 2](laboratorios/lab-02-ramas.md) | Nueva funcionalidad en una rama + conflicto provocado | 2 |
| [Lab 3](laboratorios/lab-03-github.md) | Publicar en GitHub y sincronizar desde dos lugares | 3 |
| [Lab 4](laboratorios/lab-04-trabajo-en-equipo.md) | Trabajo en equipo con Pull Requests | 4, 5 |

### Recursos

- 📄 [Hoja de referencia rápida (cheatsheet)](recursos/cheatsheet.md)
- 🧾 [Rúbrica de evaluación](recursos/rubrica.md)
- ☕ [`.gitignore` recomendado para proyectos Java](recursos/gitignore-java.txt)
- 🎥 [Serie de videos para YouTube (guion)](video/guion-serie-youtube.md)

## Requisitos previos

- Un computador con Windows, macOS o Linux.
- JDK instalado (17 o superior) y **IntelliJ IDEA** (Community o Ultimate).
- Conocimientos básicos de Java (clases, objetos, `main`).
- Ganas de romper cosas y arreglarlas 🙂

## Cómo usar este curso

1. Lee cada módulo **en orden**. Cada uno termina con un ✅ *Checkpoint* para autoevaluarte.
2. Escribe los comandos **a mano** en la terminal; no copies y pegues todo. La memoria muscular importa.
3. Haz los laboratorios. Son la parte que realmente se evalúa.
4. Si te atascas, revisa la [cheatsheet](recursos/cheatsheet.md) o la sección *Errores frecuentes* de cada módulo.

## Convenciones

- Los comandos de terminal aparecen así:

  ```bash
  git status
  ```

- Lo que **tú debes reemplazar** va entre `<ángulos>`, por ejemplo `git clone <url-del-repo>`.
- 💡 = consejo · ⚠️ = cuidado · ✅ = checkpoint

## Licencia

Material docente de libre uso con fines educativos ([CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.es)).
