# Therianthrope Advancement

A content module for the dnd5e system (system 6.0.x, Foundry 14+) providing the **Therianthrope Advancement Class**: a character afflicted by therianthropy gains Stages alongside their normal levels, unlocking transformations, gifts, and calling milestones. It ships the class, its seven paths, gifts, milestones, form actors, and a rules journal as compendium packs.

## Requirements

This module is content only. It requires:

- The **Advancement Classes** module, version 2.0.0 or later, which provides the framework.
- The dnd5e system.

## Installation

1. Install [Advancement Classes](https://github.com/WilliamCrewe/dnd5e-advancement-class) first.
2. Install this module via the manifest URL:

```
https://github.com/WilliamCrewe/dnd5e-therianthrope-advancement/releases/latest/download/module.json
```

3. Enable both modules in your world. The packs appear under the shared "Advancement Class" compendium folder; grant the Therianthrope class item to a character to begin progression.

## Contents

- **classes** pack: the Therianthrope class, seven paths, features, gifts, and milestones.
- **actors** pack: Animal and Hybrid form actors for each branch.
- **journals** pack: the full Therianthrope rules write-up.

## Regenerating the packs

The pack `_source` JSON is produced by `tools/generate.mjs`, which uses the content builder from the Advancement Classes repository. Either add that repo as a submodule at `vendor/advancement-classes`, or point at a local checkout:

```sh
ADVANCEMENT_CLASSES_ROOT=/path/to/advancementClass node tools/generate.mjs
```

This rewrites `packs/_source`. Pass `--pack` to also compile the packs, or use the Foundry CLI (`npx @foundryvtt/foundryvtt-cli package pack <name> --in packs/_source/<name> --out packs`).

## Release

Pushing a tag like `v1.0.0` runs the release workflow: it regenerates and compiles the packs, stamps the version and URLs into `module.json`, and publishes a GitHub release with `module.zip` and `module.json`.
