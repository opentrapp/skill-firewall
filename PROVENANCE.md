# Provenance

This repository is a generated, one-way projection of the Skill Firewall scanner
that lives in [albertdobmeyer/opentrapp](https://github.com/albertdobmeyer/opentrapp)
under `workloads/skills/` (the engine) and `actions/skill-scan/` (the action
metadata and README).

It exists only because a GitHub Marketplace listing requires a single action with
`action.yml` at the repository root, which the monorepo cannot provide. The monorepo
remains the source of truth.

## Regenerate

From a checkout of the source repo:

```bash
scripts/build-skill-firewall-projection.sh /tmp/skill-firewall-build
```

then sync `/tmp/skill-firewall-build` into this repository. In CI this is automated
on every `skill-scan-v*` tag (see `.github/workflows/sync-skill-firewall.yml` in the
source repo). Do not hand-edit files here; edit them in the source repo and let the
projection regenerate.

## What is and is not vendored

Only the offline Tier A engine is shipped: `scan` and `verify`. The model-backed
Content Disarm and Reconstruction (Tier B) is intentionally excluded so this
published action contains nothing that touches a network or a model.
