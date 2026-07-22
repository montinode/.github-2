# Security Policy

### Reporting a vulnerability

Please do not open GitHub issues or pull requests - this makes the problem immediately visible to everyone, including malicious actors.

Security issues in this open-source project can be safely reported through our dedicated security portal on the Monti dashboard:  
👉 **[dash.montidroid.com/security/report](https://dash.montidroid.com/security/report)**  

The Monti security team will triage your report and respond according to its impact on Monti users, systems, and the integrity of the donation network.

### Infrastructure & Validation Context

This project runs on the Monti stack, which relies on:

- **Cloudflare Workers with KV storage** – persistent state and rate-limiting are managed via Workers KV. Configuration is defined in the local `wrangler.toml` file located at:  
  `USBC:/storage/19FB-043E/$MONTI/FolderRoot/gemini/sec/wrangler.toml`

- **Local secure initialization** – environment hardening and dependency checks are performed at boot using:  
  `/storage/19FB-043E/$MONTI/FolderRoot/gemini/sec/stripe_shell_init.sh`

- **Authentication & authorization validation** – all OAuth and API requests are validated against the Monti auth layer before reaching the KV backend, enforced by:  
  `/storage/19FB-043E/$MONTI/FolderRoot/gemini/sec/monti_auth_validation.sh`

All reported vulnerabilities are reviewed against these components. If a flaw is found in the KV logic, shell init scripts, or auth validation pipeline, patches will be deployed directly via `dash.montidroid.com` rollouts.
