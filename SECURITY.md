# Security

Do not report suspected vulnerabilities in public issues when disclosure would expose exploit details.
Use GitHub private vulnerability reporting if enabled, or contact the repository owner privately.

The supported execution contract is the reusable workflow pinned to a full commit SHA. Mutable branch or tag
references are not trusted execution identities. Artifact integrity is bound by `dist/SHA256SUMS`; evidence
bundles are independently verified before publication.
