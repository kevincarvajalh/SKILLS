# Skill: Crear rama de trabajo

## Objetivo
Antes de modificar cualquier archivo, crear una rama de trabajo desde `dev`. Nunca trabajar directamente en `main`.

## Pasos

1. **Preguntar al usuario:** "¿Quieres que cree una rama para este cambio?"
2. **Clasificar el tipo de cambio** según la naturaleza de la tarea:
   - `feat/` → nueva funcionalidad
   - `fix/` → corrección de bug
   - `docs/` → solo documentación
   - `refactor/` → restructuración sin cambio de comportamiento
   - `chore/` → mantenimiento (deps, configs, etc.)
   - `test/` → añadir o corregir tests
3. **Proponer un nombre de rama** con estas reglas:
   - En español
   - Preciso y sin redundancia: no repetir el tipo ya indicado en el prefijo
     - ❌ `fix/arreglar-bug-login` → ✅ `fix/validar-login`
   - Máximo 2-4 palabras, solo las esenciales
   - Sin artículos, sin genéricos ("cambio", "actualizacion"), sin fechas ni números de issue (salvo que el usuario los pida)
4. **Verificar que `dev` exista y esté actualizada:**
   - Si no existe `dev`, preguntar al usuario antes de crearla
   - Hacer `git pull origin dev` para tener la última versión
5. **Crear la rama:** `git checkout -b <tipo>/<nombre> dev`

## Reglas
- Ramificar SIEMPRE desde `dev`, nunca desde `main`
- Si el usuario dice que no necesita rama, continuar en la rama actual
