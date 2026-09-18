# SQL Cost Gate

Minimal public distribution of the reusable SQL cost gate.

This repository is intentionally **not** a mirror of the private
`db-cost-attribution` project. It contains only:

- one base64-armored Python zipapp implementing the SQL scanner and evidence verifier;
- the zipapp's SHA-256 manifest;
- the exact runtime dependency pin;
- the reusable GitHub Actions workflow.

No attribution engine, collectors, lake code, research modules, tests, or private project
documentation are published here.

## Distribution provenance

The current zipapp was assembled from the runtime import closure of
`cost_attribution.sql_analysis` at private source commit
`9c071c4f372935a9984f6d48f01e705d1e366e38`. The artifact embeds the same
provenance record.

The artifact is base64-armored only because GitHub's narrow publication interface is
textual. The workflow decodes it, verifies `dist/SHA256SUMS`, and executes the decoded
zipapp. The base64 encoding is not a confidentiality mechanism.

Consumers must call the reusable workflow at a full immutable commit SHA. Tags are for
discovery only.

## Local verification

```bash
base64 --decode dist/sql-cost-gate.pyz.b64 > sql-cost-gate.pyz
(cd dist && sha256sum --check SHA256SUMS)
python sql-cost-gate.pyz scan --help
python sql-cost-gate.pyz verify --help
```

Licensed under Apache-2.0.
