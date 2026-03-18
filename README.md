# overstory-cli

Nix packaging for `@os-eco/overstory-cli` using Bun and `bun2nix`.

## Package

- Upstream package: `@os-eco/overstory-cli`
- Pinned version: `0.9.1`
- Installed binary: `overstory`
- Upstream executable invoked by Bun: `overstory`

## What this repo does

- Uses `bun.lock` and generated `bun.nix` as the dependency lock surface for Nix
- Builds an internal Bun application package with `bun2nix`
- Exposes only the canonical binary name `overstory`
- Provides a GitHub Actions workflow that can sync the pinned npm version

## Files

- `flake.nix`: flake entrypoint
- `nix/package.nix`: Nix derivation
- `nix/package-manifest.json`: pinned package metadata and exposed binary name
- `scripts/sync-from-npm.ts`: updates pinned npm metadata without changing the canonical output binary

## Usage

```bash
nix build
./result/bin/overstory --help
```

## Notes

- The packaged output removes the bundled Pi guard extension files and the `pi.ts` integration that writes them.
- Pi guard handling is intended to live in `RogerNavelsaker/os-eco-pi-extension`, not in this package.
