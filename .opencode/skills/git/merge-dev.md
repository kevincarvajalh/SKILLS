# Skill: Merge a dev

## Objetivo
Mergear la rama de trabajo actual a `dev` y push a GitHub.

## Pasos

1. **Verificar working tree limpio:** `git status` — no debe haber cambios pendientes
2. **Cambiar a `dev` y actualizar:** `git checkout dev && git pull origin dev`
3. **Merge de la rama de trabajo a `dev`:**
   ```bash
   git merge --no-ff <rama-de-trabajo> -m "merge: <rama-de-trabajo> a dev"
   ```
4. **Push de `dev` a GitHub:** `git push origin dev`
5. **Borrar la rama de trabajo** (local y remota si existe):
   ```bash
   git branch -d <rama-de-trabajo>
   git push origin --delete <rama-de-trabajo>  # si existe en remoto
   ```

## Reglas
- `main` y `dev` siempre se mantienen — nunca se borran
- Si el merge genera conflictos, resolverlos antes de continuar
- El commit de merge usa `--no-ff` para conservar el historial de la rama
