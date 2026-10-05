# Changelog — CORSair

---

## v3.0.0

### Added
- **Telegram Integration** (dedicated tab) — Send findings directly to Telegram via Bot API:
  - Step-by-step bot setup guide built into the UI
  - Test Connection button — verifies token + chat ID before sending
  - Send All: text summary with severity, target, CORS headers, and verdict; HTML PoC, Exfil PoC, HTML Report, and Bug Report all sent as Telegram document attachments in one click
  - Telegram-safe MarkdownV2 escaping (`escTG()`) — special characters properly escaped so messages never fail to send
  - Telegram send log — timestamped per-file status in the UI
- **Smart PoC Naming** — All generated files named after the target domain:
  - `api-company-com_cors_poc.html`
  - `api-company-com_cors_exfil_poc.html`
  - `api-company-com_cors_iframe_poc.html`
  - `api-company-com_cors_report.html`
  - `api-company-com_cors_report.md`
  - Filename displayed as a badge above the PoC Gen sub-tabs
- **HTML Security Report** (new PoC Gen sub-tab) — Professional, submit-ready styled HTML report:
  - Cover page with severity badge, target metadata grid
  - CORS verdict section with color-coded verdict box
  - CVSS v3.1 score display
  - Full CORS headers table
  - Findings cards with technical detail
  - Steps to Reproduce
  - Remediation checklist
  - References
  - Print-to-PDF ready (CSS print media query included)
  - Named after target domain

### Changed
- Version: v2.0.0 → v3.0.0
- Tab layout: 6 tabs → 7 tabs (added dedicated Telegram tab)
- PoC Gen sub-tabs: 6 → 6 (HTML PoC, Exfil PoC, iframe null, **HTML Report** replaces a gap, cURL, Bug Report)
- Download buttons now use smart target-domain filenames everywhere
- All `dlFile()` calls now resolved at genPoC() time — filename is always consistent with target

### Preserved from v2.0.0
All v2 features unchanged:
- Auth Presets (JWT, API Key, Basic Auth, Cookie)
- Preflight AUTO-probe (OPTIONS)
- WAF/CDN Detection (8 signatures)
- Security Headers Inspector
- CORS Bypass Matrix (10 origin variants)
- Batch URL Scanner (50 endpoints)
- Response Diff Analyzer
- Exfiltration PoC (triple-fallback: fetch → beacon → img)
- iframe Sandbox PoC (null origin)
- JSON Export (batch + session history)

---

## v2.0.0

### Added
10 new features over v1: Auth Presets, Preflight AUTO-probe, WAF/CDN Detection, Security Headers Inspector, CORS Bypass Matrix, Batch URL Scanner, Response Diff Analyzer, Exfiltration PoC, iframe Sandbox PoC, JSON Export.

---

## v1.0.0

Initial release. Single-target CORS probe, 5-tab UI (Probe/Response/Analysis/PoC Gen/History), CORS analysis engine, standard HTML PoC, cURL generator, bug report template, session history.

---

## v0.1.0 — CorsPoC.html (Legacy)

Original single-file CORS PoC tool. GET-only XHR with withCredentials, Raw/JSON output toggle.
