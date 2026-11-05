# Public signing keys

These keys are public. Their private halves exist only as GitHub Actions secrets of the (private) source repository and in the maintainer's offline backup.

| File | Use | Algorithm | Fingerprint / check |
|---|---|---|---|
| `html-slides-archive-keyring.pgp` | signs the apt repository (`InRelease`, `Release.gpg`); install it as `/usr/share/keyrings/html-slides-archive-keyring.pgp` | OpenPGP Ed25519, created 2026-11-05, expires 2029-11-04 | `3706 8170 C47C ADB1 35FE EDBF C0CC 3DC3 8853 6F1D` |
| `update-signing-public.pem` | verifies the signature on each Release's `SHA256SUMS` before the Update button installs anything | Ed25519 (SPKI PEM) | SHA-256 of the file: `b6a6982c86d27aff159b3ee9b7808f2b1063f59d82def776991db631a138742e` |

Check the apt key before trusting it:

```bash
gpg --show-keys --with-fingerprint html-slides-archive-keyring.pgp
```

The fingerprint printed must equal the one above.