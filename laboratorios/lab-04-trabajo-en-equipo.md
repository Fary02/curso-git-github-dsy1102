# Lab 4 — Trabajo en equipo con Pull Requests

⏱️ 90 minutos · Módulos 4 y 5 · **Grupos de 3** · [Índice](../README.md)

## Contexto

Su equipo desarrollará en conjunto un pequeño **Sistema de Préstamos** aplicando GitHub Flow. Cada integrante trabaja en su propia rama y **nadie hace push directo a `main`**. Se recomienda hacer este lab **desde IntelliJ** para practicar el Módulo 5.

## Roles

| Rol | Responsabilidad extra |
|-----|----------------------|
| **Integrante A — Líder de repo** | Crea el repositorio, invita colaboradores y configura la protección de `main` |
| **Integrante B** | Revisa los PR de A |
| **Integrante C** | Revisa los PR de B |
| (A revisa los PR de C) | |

## Parte A — Preparación (Integrante A)

1. Crea el repo `sistema-prestamos-<grupo>` con README y `.gitignore` de Java (plantilla *Java* de GitHub).
2. **Settings → Collaborators**: invita a B y C.
3. Protege `main` exigiendo PR con 1 aprobación ([Módulo 4, sección 6](../modulos/04-colaboracion-pull-requests.md#6-proteger-la-rama-main)).
4. Crea la estructura base: clase abstracta `Material` (titulo, anio, `getTipo()` abstracto) y `Main.java` vacío. Súbela vía PR (pide a B que la apruebe).
5. Crea estos **Issues** y asígnalos:

| Issue | Asignado |
|-------|----------|
| Crear `Libro` y `Revista` heredando de `Material` | A |
| Crear `Socio` con rut, nombre y lista de préstamos | B |
| Crear `Prestamo` (material, socio, fechaInicio, fechaDevolucion) con `estaAtrasado()` | C |
| Integrar todo en `Main` con datos de ejemplo | A (después de que todos fusionen) |

## Parte B — Desarrollo en paralelo (todos)

6. Cada integrante **clona** el repo (IntelliJ: *File → New → Project from Version Control*).
7. Crea su rama desde `main` actualizado: `feature/libro-revista`, `feature/socio`, `feature/prestamo`.
8. Implementa su issue con **al menos 3 commits**.
9. Push de la rama y abre un **PR** con:
   - Descripción de los cambios.
   - `Closes #<número-de-issue>`.
   - Reviewer asignado según la tabla de roles.

## Parte C — Code review

10. Cada reviewer deja **al menos 2 comentarios** en líneas específicas (usen el checklist de POO del Módulo 4).
11. Al menos un PR debe recibir **Request changes**; su autor corrige con nuevos commits en la misma rama.
12. Una vez aprobados, fusionen los PR **uno por uno**. Después de cada merge, los demás actualizan su rama:

    ```bash
    git switch main && git pull
    git switch feature/mi-rama
    git merge main            # resuelve conflictos si aparecen
    git push
    ```

## Parte D — Integración

13. El integrante A implementa el último issue (`Main` integrado) siguiendo el mismo flujo.
14. Verifiquen que el proyecto en `main` **compila y corre**.
15. Creen un **tag** de entrega:

    ```bash
    git switch main && git pull
    git tag -a v1.0 -m "Entrega Lab 4"
    git push origin v1.0
    ```

## Entregable (AVA)

- Link al repositorio (público o con el docente como colaborador).
- Todos los issues **cerrados** mediante PR.

## Criterios de logro

| Criterio | ✔️ |
|----------|----|
| `main` protegida; ningún commit directo (salvo el inicial) | |
| Cada integrante tiene ≥ 3 commits propios y ≥ 1 PR fusionado | |
| Cada PR tiene descripción, issue enlazado y revisión con comentarios | |
| Al menos un ciclo de *Request changes* → corrección → aprobación | |
| El proyecto en `main` compila y aplica herencia correctamente | |
| Tag `v1.0` publicado | |

> 💡 El docente revisará **Insights → Contributors** y el historial de PR para verificar la participación de cada integrante.
