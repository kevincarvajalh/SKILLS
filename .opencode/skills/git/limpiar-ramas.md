# Skill: Limpieza de ramas

## Objetivo
Limpiar ramas abandonadas que ya fueron mergeadas en `dev`, dejando el repositorio solo con `main`, `dev` y las ramas de trabajo activas.

## Pasos

1. **Actualizar referencias remotas:** `git fetch --prune`
2. **Diagnosticar ramas mergeadas en `dev`:** `git branch --merged dev`
3. **Protección absoluta:** nunca borrar `main` ni `dev`
4. **Preguntar al usuario:**
   - "Encontré estas ramas ya mergeadas en dev: [lista]. ¿Las borro todas?"
   - "¿Borro también las ramas remotas en GitHub o solo las locales?"
5. **Borrar ramas mergeadas (con confirmación):**
   - Locales: `git branch -d <rama>`
   - Remotas (si el usuario confirma): `git push origin --delete <rama>`
6. **Informar ramas no mergeadas:** "Estas ramas no están mergeadas en dev, no las toco: [lista]"
7. **Verificación final:** `git branch -a` — mostrar el estado limpio del repositorio

## Reglas
- Solo se borran ramas mergeadas en `dev` — las no mergeadas nunca se tocan
- `main` y `dev` son permanentes — nunca se borran
- Siempre preguntar antes de borrar remotas en GitHub
