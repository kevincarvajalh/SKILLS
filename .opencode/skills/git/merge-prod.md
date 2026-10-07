# Skill: Merge a producción (main)

## Objetivo
Mergear `dev` a `main`, crear tag de versión y push a GitHub.

## Pasos

1. **Verificar que `dev` esté actualizado:** `git checkout dev && git pull origin dev`
2. **Cambiar a `main` y actualizar:** `git checkout main && git pull origin main`
3. **Merge de `dev` a `main`:**
   ```bash
   git merge --no-ff dev -m "release: vX.Y.Z"
   ```
4. **Crear tag de versión:**
   - Preguntar al usuario qué tipo de versión: `patch` (v1.0.1), `minor` (v1.1.0) o `major` (v2.0.0)
   - Por defecto incrementar `patch`
   - `git tag -a vX.Y.Z -m "release: vX.Y.Z"`
5. **Push a GitHub:** `git push origin main --tags`

## Reglas
- `main` y `dev` siempre se mantienen — nunca se borran
- El commit de merge usa `--no-ff` para conservar el historial
- El tag siempre es anotado (`-a`) con mensaje descriptivo
