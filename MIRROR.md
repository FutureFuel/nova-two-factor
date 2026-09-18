# Why this repository exists

This is a mirror of the MIT-licensed package `visanduma/nova-two-factor`
version 3.0.1 (upstream reference `892e8786dd6d631c1245a35813eb302eeb5c2b0f`,
released 2025-01-28).

## Background

The upstream repository `https://github.com/Visanduma/nova-two-factor` was
taken down and returns HTTP 404 for the repository, its commits and its
zipballs. Packagist still lists the package, but every dist URL points at the
deleted repository, so `composer install` from a cold Composer cache fails.

The takedown followed the disclosure of the PolinRider supply-chain campaign,
which compromised the Visanduma GitHub organization from mid-June 2026 and
published malicious code to the package's unstable branch versions
(`dev-main`, `dev-nova4support`, `dev-using-inertia`, `dev-nova5`). No tagged
release was implicated.

## Provenance and verification

The contents here are the exact 3.0.1 files that were already installed in
`backend/vendor/visanduma/nova-two-factor/` in the `FutureFuel/ff` repository,
predating the intrusion window. No package code was modified; only this file
and a `LICENSE` file were added.

This tree was checked against the published PolinRider indicators and is clean:

- `tailwind.config.js` is 11 lines of Tailwind config
  (sha256 `7edcb28666a4624815607c3afeb8ea6edd49eff3481d9af23acfdd026c8a3fd8`),
  and does not match any of the five published payload hashes.
- No `.vscode/tasks.json`, no `.woff2` files, no `index.php`.
- No `shell_exec`, `proc_open`, `eval`, `child_process`, `base64_decode` or
  `atob` anywhere in the tree.
- None of the published command-and-control addresses or the dead-drop
  Ethereum address appear in the tree.

Because the `3.0.1` tag and the `main` branch here both point at this verified
tree, resolving any version from this mirror yields the clean 3.0.1 code.

## How it is consumed

`ff` consumes this mirror through a `vcs` repository entry in
`backend/composer.json`; the `require` constraint still names the original
package `visanduma/nova-two-factor`, so no application code changed.

The package provides two-factor authentication for the Nova admin panel.

Tracked in CD-28621.
