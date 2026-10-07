# ORUS agent releases

This repository has the signed ORUS agent packages, published as GitHub Releases named `agent-v<version>`. It has no source code.

## Files in each release

| File | What it is |
|---|---|
| `orus-agent-<version>-<rid>.update.tar.gz` | The update payload. |
| `orus-agent-<version>-<rid>.tar.gz` / `.zip` | The first-install package. |
| `orus-agent-<version>-<rid>.manifest.json` | The manifest: SHA-256 and size of both files above. |
| `orus-agent-<version>-<rid>.manifest.sig` | The manifest's ECDSA P-256 signature, made with the offline ORUS release key. |
| `release-trust.json` | Release key rotation and revocation statements. |
| `SHA256SUMS` | Checksums of the files in the release. |

## How they are checked

ORUS installations download new versions from here. Nothing in this repository is trusted as such:

- **Before ORUS offers a version**, it checks every manifest against the release keys it trusts.
- **Before a host installs it**, the host checks the same signature again.

A file that does not match its signed manifest is refused.
