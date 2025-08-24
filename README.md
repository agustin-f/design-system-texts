# Design System Texts - Workflow

Este repositorio centraliza los textos de un Design System y mantiene un **flujo controlado de versión** desde Google Sheets, GitHub, Local y ZeroHeight.

---

## 1. Flujo general

+-------------------+ push JSON/MD +------------------+
| |-------------------------------->| |
| Google Sheets | | GitHub |
| (Fuente de verdad)|<--------------------------------| (Repositorio) |
| | pull/update | |
+-------------------+ +------------------+
| |
| Apps Script exporta JSON & MD |
v v
+-------------------+ +------------------+
| |<------------------------------->| |
| Local | pull / push commits | ZeroHeight |
| (Clonación, Edits)| | (Embed MD) |
| | | |
+-------------------+ +------------------+

markdown
Copiar
Editar

### 🔹 Cómo leer el diagrama

1. **Google Sheets → GitHub**  
   - Apps Script exporta `fundamentos.json` y `fundamentos.md`.  
   - Cada ejecución crea un commit en la rama `main`.

2. **Local ↔ GitHub**  
   - Cloná el repo y editá localmente.  
   - Ejecutá `git pull` para traer cambios de Sheets.  
   - Ejecutá `git push` para subir tus cambios al repositorio.

3. **GitHub → ZeroHeight**  
   - Usar el archivo Markdown generado (`fundamentos.md`) como embed:  
     ```
     https://raw.githubusercontent.com/agustin-f/design-system-texts/main/fundamentos.md
     ```
   - Cada actualización en GitHub se refleja automáticamente en ZeroHeight al refrescar la página.

---

## 2. Buenas prácticas

- **Commits claros**: mensajes descriptivos para cada cambio.  
- **Sincronización**: hacer `git pull` antes de editar localmente.  
- **Ramas opcionales**: crear ramas para probar cambios sin afectar `main`:
  ```bash
  git checkout -b nombre-de-rama
  git push origin nombre-de-rama
Luego abrir un Pull Request para revisar antes de mergear.

JSON vs Markdown:

.json → integración con sistemas y otras herramientas.

.md → ZeroHeight y documentación legible para equipos no técnicos.

3. Estructura de archivos
fundamentos.json → datos exportados desde Google Sheets.

fundamentos.md → Markdown generado automáticamente para ZeroHeight.

Otros .json pueden agregarse siguiendo el mismo patrón por sección o componente.

4. Actualización desde Google Sheets
Abrir el Google Sheet vinculado.

Editar los textos.

Ejecutar el Apps Script updateFundamentos.

Se generan y suben automáticamente fundamentos.json y fundamentos.md a GitHub.

5. Actualización manual local
Clonar o actualizar el repositorio:

bash
Copiar
Editar
git pull origin main
Editar los archivos JSON localmente.

Commit y push:

bash
Copiar
Editar
git add fundamentos.json
git commit -m "Actualización local de textos"
git push origin main
6. Visualización en ZeroHeight
Insertar como Embed → Markdown:

perl
Copiar
Editar
https://raw.githubusercontent.com/agustin-f/design-system-texts/main/fundamentos.md
Cada actualización en GitHub se reflejará automáticamente al refrescar la página.

Notas
Google Sheets es la fuente de verdad, pero los cambios locales también se pueden versionar y fusionar vía GitHub.

Mantener un control de versiones ayuda a revertir cambios y revisar historial de actualizaciones de textos.