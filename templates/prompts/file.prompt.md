```prompt
---
name: file
description: Leer archivos DOCX, XLSX, PDF usando file reader skills
argument-hint: "<filepath>"
---

📄 **FILE READER PROTOCOL**

Extrae texto de documentos usando las skills de lectura de archivos del framework.

---

**PROTOCOLO:**

1. **Detecta formato** del `<filepath>` por extensión:
   - `.docx` → Microsoft Word
   - `.xlsx` → Microsoft Excel
   - `.pdf` → Portable Document Format

2. **Ejecuta skill adecuada:**
   ```bash
   uv run .sia/skills/read_file.py '<filepath>'
   ```
   - Auto-detección por extensión (reader universal)
   - PEP 723: dependencias se instalan automáticamente

3. **Presenta resultado:**
   - Si éxito → Muestra contenido extraído
   - Si error → Reporta diagnóstico (archivo no encontrado, corrupto, formato no soportado)

4. **Opciones avanzadas (si necesario):**
   - Forzar formato: `uv run .sia/skills/read_file.py --format pdf '<filepath>'`
   - Listar formatos: `uv run .sia/skills/read_file.py --list-formats`
   - Reader específico: `uv run .sia/skills/read_<ext>.py '<filepath>'`

---

**SKILLS DISPONIBLES:**

| Skill | Formato | Dependencia |
|---|---|---|
| `read_file.py` | Universal (auto-detect) | python-docx, openpyxl, PyMuPDF |
| `read_docx.py` | DOCX | python-docx |
| `read_xlsx.py` | XLSX | openpyxl |
| `read_pdf.py` | PDF | PyMuPDF |

**EXIT CODES:** 0 = éxito | 1 = error de archivo | 2 = error inesperado

---

**GUARDIANES:** DDD | SOLID | Δ(Input) ⇒ Δ(Output) | Domain Research First
```
