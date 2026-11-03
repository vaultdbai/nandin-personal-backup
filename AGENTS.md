# AI Agent Instructions

## Overview

Nandi Personal Backup (MIT): Backup Keeper and the "Set up S3 backup" workflow, which back up your folders to your own S3 bucket. See [README.md](README.md) for what each agent does.

Inside the Nandi workspace, the workspace `AGENTS.md` adds the general standards. This file is the stand-alone minimum for contributors.

## Core Rules (CRITICAL)

- An agent's `skill.md` body stays at **900 words or fewer**.
- Its `capabilities` must match the registry entry in `nandi-registry` **exactly**: `tools` = `allowed-tools`, `network` = the `network.allow` hosts, `requires_approval` = `requires_approval`.
- Every tool that writes files or runs commands **requires approval**.
- **No `model:`** in a pack. Pack agents use the user's default model.
- Users change an agent's rules in its **Settings › Your rules**, which survive updates. Don't put user-specific rules in `skill.md`.
- **Releases:** bump `version` in `.nandi/manifest.yaml`, tag `v<version>`, then update and sign the entries in `nandi-registry`.
- No unsolicited commits, and never force-push. Use Conventional Commits.

## Licence

MIT (see `LICENSE`).
