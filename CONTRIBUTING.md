# Contributing to CORSair

Thank you for your interest in contributing to **CORSair**! Contributions from security researchers, bug hunters, and developers are welcome.

---

## Code of Conduct

Please follow the [Code of Conduct](CODE_OF_CONDUCT.md) in all community interactions.

## Architectural Principles

1. **Zero External Runtime Dependencies**: CORSair is intentionally designed as a standalone, browser-run application that requires no `npm`, no backend server, and no build pipeline. Any new UI or analysis feature should use vanilla HTML5, CSS3, and modern JavaScript (`fetch`, `AbortController`, `Blob`, etc.).
2. **Safe & Authorized Testing Only**: Features that attempt unauthorized mass exploitation, denial-of-service, or weaponized payload spreading will not be accepted.
3. **Cross-Browser Reliability**: Ensure any new features work reliably across modern Chrome/Chromium, Firefox, and Safari.

---

## How to Contribute

1. **Fork the Repository**:
   ```bash
   git clone https://github.com/pratik-khairnar-sec/CORSair.git
   cd CORSair
   ```
2. **Local Testing**:
   Serve the application locally to test Origin handling:
   ```bash
   python3 -m http.server 8080
   # Open http://localhost:8080/CORSair.html
   ```
3. **Sync Changes**:
   If modifying `CORSair.html`, make sure to sync changes to `index.html` (or copy `CORSair.html` to `index.html`) so GitHub Pages stays up to date:
   ```bash
   cp CORSair.html index.html
   ```
4. **Submit a Pull Request**:
   Describe what changed, attach screenshots of the UI, and verify across browsers.
