# Why this repository exists

This is a mirror of the MIT-licensed package `visanduma/nova-two-factor`
version 3.0.1 (upstream reference `892e8786dd6d631c1245a35813eb302eeb5c2b0f`).

The upstream repository `https://github.com/Visanduma/nova-two-factor` was
deleted and returns HTTP 404 for the repository, its commits and its zipballs.
Packagist still lists the package, but every dist URL points at the deleted
repository, so `composer install` from a cold Composer cache fails.

The contents here are the exact 3.0.1 files that were already installed in
`backend/vendor/visanduma/nova-two-factor/` in the `FutureFuel/ff` repository,
republished unchanged so Composer has somewhere to fetch them from. No package
code was modified; only this file and a `LICENSE` file were added.

`ff` consumes this mirror through a `vcs` repository entry in
`backend/composer.json`; the `require` constraint still names the original
package `visanduma/nova-two-factor`, so no application code changed.

The package provides two-factor authentication for the Nova admin panel.

Tracked in CD-28621.
