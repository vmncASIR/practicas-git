# Limpieza de historial con git rebase -i

## ¿Qué es git rebase -i?

`git rebase -i` (rebase interactivo) permite reescribir el historial de commits antes de compartirlo. Es útil para limpiar mensajes confusos, fusionar commits pequeños y dejar un historial legible.

## Pasos realizados

### 1. Creación de commits con mensajes poco claros
Se crearon 4 commits con mensajes genéricos ("Arreglos", "Cambios", "Actualización de cosas", "cosas varias") que no describen qué cambio se hizo ni por qué.

### 2. Rebase interactivo
Se ejecutó `git rebase -i HEAD~4` para trabajar sobre los últimos 4 commits. En el editor se usaron dos acciones:
- **reword**: para cambiar el mensaje de un commit manteniendo sus cambios.
- **squash**: para fusionar un commit con el anterior, combinando sus cambios en uno solo.

### 3. Nuevos mensajes
Los 4 commits quedaron fusionados en 2 con mensajes descriptivos:
- `feat: añadir hobbies e idiomas al perfil`
- `feat: añadir disponibilidad y LinkedIn al perfil`

### 4. Push con --force
Al reescribir el historial local, el remoto ya no coincide. Se usa `git push --force` para sobreescribir el historial en GitHub con la versión limpia.

## ¿Por qué es importante?
Un historial limpio facilita el trabajo en equipo: cualquier persona puede entender qué se cambió y por qué sin tener que revisar el código línea por línea.
