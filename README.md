# gpd cli skills

A collection of Agent Skills for shipping with the [gpd cli](https://github.com/rudrankriyam/Google-Play-Developer-CLI) (`gpd`). These skills are designed for zero-friction automation around Android releases, Play Store metadata, testing tracks, pricing, and Play Console operations.

This is a community-maintained, unofficial skill pack and is not affiliated with Google.

Skills follow the Agent Skills format.

## Available Skills

### gpd-cli

Google Play umbrella skill for publishing, reviews, vitals, monetization, purchases, permissions, analytics, and migration workflows.

**Use when:**
- You need broad Google Play or Android publishing help
- You want the agent to route into the right `gpd-*` skill automatically

### gpd-cli-usage

Guidance for running `gpd` commands, including auth, flags, output formats, and command discovery.

**Use when:**
- You need the correct `gpd` command or flag combination
- You want JSON-first output and auth guidance for automation

### gpd-release-flow

End-to-end release workflows for Google Play tracks, staged rollouts, promotions, and edit lifecycle.

**Use when:**
- You want to upload an Android build and release it to Play
- You need staged rollout or track promotion steps

### gpd-submission-health

Preflight checks and release-readiness validation for Google Play submissions.

**Use when:**
- You want to catch submission issues before release
- You need listing, asset, or edit validation guidance

### gpd-metadata-sync

Sync Play Store listings, assets, and Fastlane-style Android metadata with `gpd`.

**Use when:**
- You are updating store listings, screenshots, or localized metadata
- You are migrating Android metadata from Fastlane

### gpd-build-lifecycle

Track processing status, release state, and internal sharing for Android builds.

**Use when:**
- You are waiting on uploaded builds to process
- You need release status or cleanup guidance

### gpd-betagroups

Manage internal and beta testing groups, testers, and track promotion flows.

**Use when:**
- You need to distribute builds to testers
- You manage multiple testing tracks or groups

### gpd-id-resolver

Resolve package, track, product, and subscription identifiers for Play workflows.

**Use when:**
- A `gpd` command requires an exact ID
- You want deterministic inputs for automation

### gpd-ppp-pricing

Territory-specific pricing workflows for Play products and subscriptions.

**Use when:**
- You are adjusting regional prices
- You need PPP or localized pricing strategies

## Installation

Install this skill pack:

```bash
npx skills add rudrankriyam/gpd-cli-skills
```

## Usage

Skills are automatically available once installed. The agent will use them when relevant tasks are detected.

**Examples:**

```
Upload my Android AAB and release it to the internal track on Google Play
```

```
Validate my Play Store metadata in ./fastlane/metadata/android and sync it with gpd
```

```
Set up a staged rollout to production for package com.example.app
```

```
Adjust Google Play subscription pricing by region using PPP
```

## Skill Structure

Each skill contains:
- `SKILL.md` - Instructions for the agent
- `scripts/` - Helper scripts for automation (optional)
- `references/` - Supporting documentation (optional)

## License

MIT
