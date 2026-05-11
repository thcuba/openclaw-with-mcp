# OpenClaw with MCP (Home Assistant Add-on)

Questo repository è una **fusion** (merge) pensata per avere in un unico progetto:

1. **OpenClaw Assistant – Home Assistant Add-on** (l’add-on che esegue OpenClaw dentro Home Assistant / HAOS)
2. **HA-MCP (Home Assistant MCP Server)** (il server MCP che espone strumenti per controllare Home Assistant tramite Model Context Protocol)

L’obiettivo è avere **OpenClaw + MCP “pronti” dentro HAOS**, con packaging, add-on, workflow e test in un unico repo.

---

## Cosa contiene

- **Home Assistant Add-on** per eseguire OpenClaw
- **MCP Server (ha-mcp)** per controllare Home Assistant via strumenti (tools)
- **Custom component** opzionale per abilitare alcuni tool “filesystem/YAML” quando richiesto
- **Test suite** (unit + e2e + addon + UAT stories) e workflow CI

---

## A cosa serve (in pratica)

Con questa combinazione puoi far lavorare un agente (OpenClaw) che, tramite MCP, è in grado di:

- cercare entità e leggere stati
- chiamare servizi
- creare/aggiornare automazioni, script, helper, dashboard Lovelace, ecc.
- fare diagnostica (logbook, history, traces…)

Tutto con un approccio “tool-first” (l’agente usa tool MCP) e con la parte add-on già integrata per HAOS.

---

## Struttura (alta livello)

- `src/` → codice del server MCP / librerie
- `homeassistant-addon/` (+ varianti dev/proxy) → add-on HA
- `custom_components/` → custom component (quando serve)
- `tests/` → test unit/e2e/UAT
- `.github/workflows/` → CI (incluso workflow E2E)

---

## Origini e crediti (repo originali)

Questo repo nasce dalla fusione di progetti esistenti. Qui sotto trovi i repo “sorgente” principali e i loro creatori.

### 1) OpenClaw Assistant – Home Assistant Add-on
- **Repo originale:** https://github.com/techartdev/OpenClawHomeAssistant
- **Creatore:** **techartdev** (GitHub: @techartdev)

### 2) Home Assistant MCP Server (ha-mcp)
- **Repo originale:** https://github.com/homeassistant-ai/ha-mcp
- **Creatore:** **Julien** (GitHub: @julienld)

Questa fusion (e le modifiche di integrazione) sono mantenute nel fork:
- https://github.com/thcuba/openclaw-with-mcp

---

## Licenza

Vedi `LICENSE`.

---

## Note

- Se stai cercando “come si usa” in produzione (HAOS / add-on), guarda anche `DOCS.md` e la cartella `docs/`.
- Se stai lavorando lato sviluppo/test, guarda `CONTRIBUTING.md` e `tests/README.md`.
