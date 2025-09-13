
# Column Mapper (Streamlit) — Profiles Edition

A lightweight Streamlit app to map columns from a **Source** CSV/XLSX to a **Target** schema, with auto-mapping, per-column transforms, batch processing, and **saved profiles** so you can reuse mappings without re-uploading the target.

## Features
- 🔁 **Auto-map** columns by name similarity
- 🎛️ Per-column modes: **source**, **constant**, **concat**
- 🧪 **Type enforcement**: text, integer, float, bool, date, datetime
- 📦 **Batch**: process multiple source files at once → ZIP with CSV + XLSX
- 💾 **Profiles**: save target schema + mapping spec to reuse later (no target upload)
- ⬇️ Export mapping spec CSV / profile JSON
- 🧰 Local-only mode example config (`.streamlit/config.toml`)

## Quickstart

```bash
# 1) Create venv (optional but recommended)
python -m venv .venv
# Windows
.venv\Scripts\activate
# macOS/Linux
source .venv/bin/activate

# 2) Install deps
pip install -r requirements.txt

# 3) Run (localhost only)
python -m streamlit run column_mapper_app_v3.py --server.address=127.0.0.1
```

Open http://localhost:8501 in your browser.

> To make localhost-only the default, see [`.streamlit/config.toml`](.streamlit/config.toml).

## Repo Structure
```
.
├── column_mapper_app.py          # Basic app (auto-map + manual mapping)
├── column_mapper_app_v2.py       # Pro edition (constants/concat/dtypes/batch)
├── column_mapper_app_v3.py       # Profiles edition (save & reuse target/mapping)
├── examples/
│   ├── source_customers.xlsx
│   ├── target_customers.xlsx
│   └── mapping_spec.csv
├── scripts/
│   ├── run_local.bat             # Windows one-click launcher (localhost only)
│   └── run_local.sh              # macOS/Linux launcher
├── .streamlit/
│   └── config.toml               # Streamlit config (localhost-only)
├── .gitignore
├── LICENSE
├── README.md
└── requirements.txt
```

## How to Use
1. **First time**
   - Upload Target (headers only OK) + Source
   - Click ✨ Auto-map or set mappings
   - Save Profile (e.g., `crm_import_v1`)
2. **Next time**
   - Upload Source(s) only
   - Load saved Profile → Preview → Download

## Demo (Screenshots)
Add screenshots in a `docs/` folder and reference them here.

## License
MIT — see [LICENSE](./LICENSE).
