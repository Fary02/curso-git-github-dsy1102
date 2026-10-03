# Lab 2 — Ramas y conflictos

⏱️ 45 minutos · Módulo 2 · Individual · [Índice](../README.md)

## Contexto

Seguimos con `biblioteca-poo`. Agregarás herencia (contenido de la unidad de POO) en una rama aparte y luego provocarás y resolverás un conflicto a propósito.

## Parte A — Funcionalidad en una rama

1. Desde `main`, crea la rama:

   ```bash
   git switch -c feature/material-abstracto
   ```

2. Crea una clase **abstracta** `Material` con `titulo`, `anio` y un método abstracto `String getTipo()`. → commit
3. Modifica `Libro` para que **herede** de `Material`. → commit
4. Crea `Revista extends Material` con atributo `numeroEdicion`. → commit
5. Observa el grafo:

   ```bash
   git log --oneline --graph --all
   ```

6. Vuelve a `main` y verifica que `Revista.java` **no existe** ahí. Regresa a la rama.
7. Fusiona en `main` y borra la rama:

   ```bash
   git switch main
   git merge feature/material-abstracto
   git branch -d feature/material-abstracto
   ```

   ¿Fue *fast-forward* o se creó un commit de merge? ¿Por qué?

## Parte B — Conflicto provocado

8. Crea la rama `fix/tostring-libro` **pero no te cambies aún**:

   ```bash
   git branch fix/tostring-libro
   ```

9. En `main`, cambia el `toString()` de `Libro` para que retorne:
   `"📕 " + getTitulo() + " - " + autor` → commit.
10. Cámbiate a `fix/tostring-libro` y cambia **el mismo método** para que retorne:
    `"Libro[titulo=" + getTitulo() + ", autor=" + autor + "]"` → commit.
11. Vuelve a `main` y fusiona:

    ```bash
    git switch main
    git merge fix/tostring-libro
    ```

12. Resuelve el conflicto **combinando** ambas ideas (por ejemplo `"📕 Libro[titulo=..., autor=...]"`), compila, ejecuta `Main` y cierra el merge:

    ```bash
    git add src/Libro.java
    git commit
    ```

13. Captura la salida de `git log --oneline --graph --all`.

## Parte C (opcional) — Repite el conflicto en IntelliJ

Repite los pasos 8–12 con otro método (por ejemplo `getTipo()`), pero resuelve usando la herramienta de 3 paneles de IntelliJ ([Módulo 5](../modulos/05-git-en-intellij.md#6-resolver-conflictos)).

## Entregable

Agrega a tu repositorio `informe-lab2.md` con:

- Respuesta a la pregunta del paso 7.
- Captura o texto del grafo del paso 13 (debe verse el commit de merge).
- Explicación en 3–5 líneas: ¿qué significaban `<<<<<<<`, `=======` y `>>>>>>>` en tu conflicto?

## Criterios de logro

| Criterio | ✔️ |
|----------|----|
| Herencia implementada correctamente en una rama propia | |
| Rama fusionada y eliminada | |
| Conflicto resuelto sin marcadores residuales y el proyecto compila | |
| Grafo muestra el commit de merge con dos padres | |
| Informe con respuestas correctas | |
