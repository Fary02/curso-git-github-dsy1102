# Lab 3 — Publicar en GitHub y sincronizar

⏱️ 40 minutos · Módulo 3 · Individual · [Índice](../README.md)

## Contexto

Tu repositorio `biblioteca-poo` existe solo en tu computador. Lo publicarás en GitHub y simularás trabajar desde **dos computadores** (por ejemplo, el PC del laboratorio y tu notebook).

## Parte A — Publicar

1. Configura la autenticación (Credential Manager, `gh auth login` o SSH).
2. Crea en GitHub un repositorio **público** vacío llamado `biblioteca-poo` (sin README).
3. Conecta y sube:

   ```bash
   git remote add origin <url-de-tu-repo>
   git push -u origin main
   ```

4. Recarga la página en GitHub. Revisa la pestaña de commits: ¿está todo tu historial?

## Parte B — README

5. **Directamente en GitHub** (botón *Add a README*), crea un `README.md` con: nombre del proyecto, descripción, cómo ejecutarlo y tu nombre. Haz commit desde la web.
6. Ahora tu repositorio local está **desactualizado**. Compruébalo:

   ```bash
   git fetch
   git status        # "Your branch is behind 'origin/main' by 1 commit"
   git pull
   ```

## Parte C — Dos computadores

7. Simula el segundo computador clonando en **otra carpeta**:

   ```bash
   cd ..
   git clone <url-de-tu-repo> biblioteca-poo-pc2
   cd biblioteca-poo-pc2
   ```

8. En `biblioteca-poo-pc2`: agrega la clase `Socio` (rut, nombre, lista de préstamos) → commit → `git push`.
9. Vuelve a la carpeta original `biblioteca-poo` **sin hacer pull** y modifica `Main.java` → commit → `git push`.
   Deberías recibir el error **`rejected (fetch first)`**.
10. Resuélvelo:

    ```bash
    git pull
    git push
    ```

11. Revisa en GitHub → **Insights → Network** el grafo resultante.

## Entregable

- **Link** a tu repositorio público en GitHub (en AVA).
- En el repo, `informe-lab3.md` explicando con tus palabras por qué ocurrió el error del paso 9 y cómo se resolvió.

## Criterios de logro

| Criterio | ✔️ |
|----------|----|
| Repo público con historial completo de los labs 1 y 2 | |
| README con descripción, instrucciones e integrante | |
| Commit de `Socio` hecho desde el “segundo PC” | |
| Explicación correcta del rechazo y su solución | |
| Sin archivos compilados en el repositorio | |
