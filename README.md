# Docs Base Devenv

Reusable documentation environment for polyrepo setups using `devenv` v2.

## Includes

- Treefmt: enabled with `mdformat`
- Git hooks: pre-commit `treefmt` and `typos` hooks enabled
- Scripts: `fmt`, `fmt-check`, `spellcheck`, `spellcheck-fix`, `ci`
- Generates `devenv.local.yaml` (via `dvnv-local-inputs`)

## Use

```yaml
inputs:
  dvnv-docs-env:
    url: github:Alb-O/dvnv-docs-env
    flake: false
imports:
  - dvnv-docs-env
```

## Consumer treefmt overrides

Consumers can extend the shared docs formatting by adding extra programs under `treefmt.config`.
This composes with `dvnv-docs-env` defaults (for example, `mdformat` stays enabled):

```nix
{
  treefmt.config.programs.taplo.enable = true;
}
```
