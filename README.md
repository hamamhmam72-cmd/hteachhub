# RealHQ Studio — H-teach hub (backend, Phases 1–2)

```bash
pip install reportlab arabic-reshaper python-bidi      # PDF export only; everything else is stdlib
python -m server.server                                  # first run prints a ONE-TIME password for user "hammam"
python -m tests.test_smoke                               # 88 end-to-end checks (boots its own server + temp data dir)
python -m server.admin reset-password hammam             # offline recovery
python -m server.restore data/backups/<file>.db           # verify a snapshot (add --apply to restore)
```
Key env vars: `REALHQ_DATA_DIR`, `REALHQ_PORT`, `REALHQ_ENV=development` (allows non-HTTPS cookies on localhost),
`REALHQ_BOOTSTRAP_PASSWORD`, `REALHQ_SEED_DEMO=0`, `REALHQ_PDF_FONT`, `REALHQ_TRUST_PROXY=1` (behind a reverse proxy). See `server/config.py`.

Run behind a TLS reverse proxy in production. Full design, RBAC matrix and API contract: `docs/PHASE1_ARCHITECTURE.md`.
