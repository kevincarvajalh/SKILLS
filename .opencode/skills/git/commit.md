# Skill: Commits

## Objetivo
Crear commits con formato consistente en español.

## Formato del mensaje

```
tipo: descripción en español
```

- **tipo:** mismo tipo que la rama (`feat`, `fix`, `docs`, `refactor`, `chore`, `test`)
- **descripción:** breve, en imperativo, en minúsculas, sin punto final, sin redundancia

## Ejemplos

- `feat: agregar formulario de registro`
- `fix: corregir validación del login`
- `docs: actualizar guía de instalación`
- `refactor: simplificar función de cálculo`

## Verificación de autoría

Antes de hacer commit, verificar que el autor esté configurado:
```bash
git config user.name
```
Si no está configurado o es incorrecto, configurarlo:
```bash
git config user.name "Kevin Carvajal"
```

## Reglas
- Un commit por cambio lógico (no mezclar cambios no relacionados)
- No hacer commit de archivos temporales, build artifacts o secrets
