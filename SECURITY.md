# Security and public repository scope

This package contains newly written documentation, synthetic benchmark tooling, and configuration templates. It contains no copied server environment files, private addresses, operational endpoints, credentials, customer data, chat exports, or model weights. Security depends on deployment and cannot be guaranteed by documentation or a pattern scan.

## Reference deployment boundaries

- Only the UI is published, bound to IPv4 loopback. Ollama has no published host port.
- Authentication stays enabled. Registration defaults off. First-admin bootstrap is a local, temporary step described in deployment notes.
- No privileged mode, host network, Docker socket, host filesystem mounts, terminal tools or public tunnel is included.
- GPU selection and image digests are required local values; the template does not silently choose all GPUs or floating image tags.
- Docker service DNS names in the example are generic; they are not live hostnames.
- The Ollama API inside the container network is not an authenticated trust boundary. Only trusted services belong on that network. Local users and Docker administrators remain trusted.
- Loopback binding does not replace application authentication, host patching or verification of Docker port behavior. Use a maintained Docker release and validate reachability locally.

## Before making a repository public

Run `python scripts/publication_check.py`, inspect `git diff --cached`, and use an established secret scanner on the full history. The included checker is a limited heuristic, not a secret detector guarantee. Review screenshots, archives, model manifests, logs and generated output manually. Ignore rules do not protect files already tracked by Git.

Keep `.env`, GPU identifiers, hostnames, private addresses, tokens, browser sessions, authentication databases, raw logs, actual network diagrams, and backups private. Do not add live compose exports. Public examples use loopback and generic service names only.

If a credential is committed, revoke or rotate it immediately. Removing the current file does not remove the credential from history or copies. Avoid placing vulnerability details or credentials in public issues.
