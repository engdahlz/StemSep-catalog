# StemSep Catalog Repo

This directory is a checkout-ready scaffold for the dedicated remote catalog repository.

Expected published files:

- `catalog.runtime.remote.json`
- `catalog.runtime.remote.json.sig`
- `catalog.public.ed25519.txt`
- `catalog-fragments/`
- `reports/`

Recommended publication flow:

1. Ingest or update source/model fragments in the main `StemSep` repo.
2. Run the one-shot release entrypoint:
   `python scripts/registry/release_catalog.py --private-key <pem> --catalog-repo-root C:\Users\engdahlz\StemSep-catalog --run-acceptance`
3. Review `reports/report_catalog_v3_sources.json` and `reports/provider_acceptance.json`.
4. Commit and push this repo separately from the main StemSep app repo.

Acceptance policy:

- Hugging Face, GitHub Releases, GitHub Raw and deterministic Google Drive entries must install through the selection-first Rust control plane.
- Proton Drive entries remain `reference` or `manual` until a live deterministic `download_url` exists.

The app's remote-first catalog support is designed to read the signed runtime catalog from a dedicated GitHub Raw URL.
