---
name: file
description: Leer archivos DOCX, XLSX, PDF usando file reader skills
argument-hint: "<filepath>"
---

📄 Extrae texto de `<filepath>` usando la skill universal con auto-detección.

**EJECUCIÓN:**
```bash
uv run .sia/skills/read_file.py '<filepath>'
```

Soporta: `.docx` `.xlsx` `.pdf` — PEP 723 (deps automáticas)

**OPCIONES:** `--format <ext>` forzar formato | `--list-formats` | `read_<ext>.py` reader específico

**GUARDIANES:** Δ(Input) ⇒ Δ(Output) | Exit: 0=ok 1=error 2=inesperado