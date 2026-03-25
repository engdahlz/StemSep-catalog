# StemSep Catalog Repo

This directory is a checkout-ready scaffold for the dedicated remote catalog repository.

Expected published files:

- `catalog.runtime.remote.json`
- `catalog.runtime.remote.json.sig`
- `catalog.public.ed25519.txt`
- `catalog-fragments/`
- `reports/`

Recommended publication flow:

1. Verify source fragments.
2. Compile `catalog.runtime.json`.
3. Publish/sign into this repo root.
4. Commit and push this repo separately from the main StemSep app repo.

The app's remote-first catalog support is designed to read the signed runtime catalog from a dedicated GitHub Raw URL.
