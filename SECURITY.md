# Publication and execution boundaries

No production data, real logs, API credentials, private addresses, GPU UUIDs, remote-access settings, or raw model responses belong in this repository. All test prompts are synthetic and public.

- Local configuration and results are ignored by Git. Ignore rules do not remove already tracked files.
- Only numeric loopback HTTP endpoints are accepted; proxy environment settings are bypassed and redirects refused. No network discovery or SSH automation is included.
- The harness sends inference requests and reads version/model metadata. It does not pull models, execute answers, expose ports, alter firewall rules, or modify services.
- Raw model responses remain only in memory for scoring. Reports retain allowlisted metrics, fixed case/profile names, model digest, sanitized version, and test settings. Endpoints and private model tags are omitted.
- HTTP errors are reported generically without response bodies. Local Ollama or other software can independently log requests; this harness does not control those logs.
- Reports are not anonymization guarantees. Model digests and software versions reveal metadata, so review reports before choosing to publish them.
- The included publication checker detects a few common patterns and local configuration presence. It does not replace manual review and a maintained full-history secret scanner.

No live server security audit occurred. A profile name is not an access boundary. Only trusted users should access the existing inference services and local host.
