# Lab 1 — Tu primer repositorio: `biblioteca-poo`

⏱️ 40 minutos · Módulos 0 y 1 · Individual · [Índice](../README.md)

## Contexto

Construirás el inicio de un sistema de biblioteca en Java y registrarás cada paso con Git. Usarás **la terminal** (Git Bash en Windows) para los comandos y **IntelliJ** para escribir el código.

## Instrucciones

### Parte A — Preparación

1. Verifica tu configuración:

   ```bash
   git config user.name
   git config user.email
   ```

2. En IntelliJ crea un proyecto Java llamado `biblioteca-poo` (sin Maven/Gradle, con `Main.java` de ejemplo).
3. Abre una terminal en la carpeta del proyecto (en IntelliJ: pestaña **Terminal**, `Alt+F12`) y crea el repositorio:

   ```bash
   git init
   git status
   ```

### Parte B — `.gitignore` primero

4. Crea `.gitignore` copiando el contenido de [`recursos/gitignore-java.txt`](../recursos/gitignore-java.txt).
5. Ejecuta `git status`. ¿Aparece la carpeta `out/`? (No debería.)
6. Commit:

   ```bash
   git add .gitignore
   git commit -m "Agrega .gitignore para proyecto Java"
   ```

### Parte C — Commits incrementales

Haz **un commit por cada paso**, con un mensaje descriptivo en imperativo.

7. Crea la clase `Libro` con atributos privados `titulo`, `autor` e `isbn`, constructor y getters. → commit
8. Agrega a `Libro` un atributo `boolean disponible` (inicia en `true`) y los métodos `prestar()` y `devolver()`. → commit
9. Sobrescribe `toString()` en `Libro`. → commit
10. En `Main.java`, crea 3 libros, presta uno e imprime todos. → commit

Antes de cada `git commit`, ejecuta `git diff` y luego `git diff --staged` para ver qué estás guardando.

### Parte D — Explorar el historial

11. Ejecuta y copia la salida en tu informe:

    ```bash
    git log --oneline
    ```

12. Usa `git show <hash>` sobre el commit del paso 8. ¿Qué líneas se agregaron?

## Entregable

Un archivo `informe-lab1.md` en la raíz del repo con:

- La salida de `git log --oneline` (mínimo **5 commits**).
- Respuesta: ¿qué diferencia observaste entre `git diff` y `git diff --staged`?
- Haz commit del informe también.

Comprime la carpeta **incluyendo la carpeta oculta `.git`** y súbela a AVA (en el Lab 3 la publicarás en GitHub).

## Criterios de logro

| Criterio | ✔️ |
|----------|----|
| Repositorio inicializado con `.gitignore` como primer commit | |
| Al menos 5 commits, cada uno con un solo propósito | |
| Mensajes en imperativo y descriptivos | |
| No hay archivos `.class` ni carpeta `out/` en el repositorio | |
| Informe con respuestas correctas | |
