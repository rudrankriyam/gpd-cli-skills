---
name: gpd-cli-usage
description: Guidance for using the Google Play Developer CLI (flags, output formats, auth, pagination). Use when asked to run or design gpd commands for Play Console workflows.
---

# GPD CLI usage

Use this skill when you need to run or design `gpd` commands for Google Play Developer Console.

## Command discovery
- Always use `--help` to confirm commands and flags.
  - `gpd --help`
  - `gpd publish --help`
  - `gpd monetization --help`

## Flag conventions
- Use explicit long flags (for example: `--package`, `--track`, `--status`).
- No interactive prompts; destructive operations require `--confirm`.
- Use `--all` when the user wants all pages.

## Output formats
- Default output is minified JSON.
- Use `--pretty` for readable JSON during debugging.

## Authentication and defaults
- Service account auth via `GPD_SERVICE_ACCOUNT_KEY` is required.
- Prefer a key **file** with `0600` permissions (`chmod 600 key.json`) or a
  secret manager over pasting raw JSON into the environment. Inline
  `export GPD_SERVICE_ACCOUNT_KEY='{...}'` leaks the key into shell history and
  the process environment (visible via `ps`, `/proc`, and child processes).
- Use a dedicated, least-privilege service account scoped only to the Play
  Console permissions the task needs; never commit keys to source control.
- Validate access for a package:
  - `gpd auth check --package com.example.app`

## Safety
- Use `--dry-run` when available before destructive operations.
- Prefer edit lifecycle (`gpd publish edit create`) for multi-step publishing.
