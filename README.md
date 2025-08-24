# Design System Texts - Workflow

Este repositorio centraliza los textos de un Design System y mantiene un **flujo controlado de versión** desde Google Sheets, GitHub, Local y ZeroHeight.

---

## 1. Flujo general



markdown
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
  