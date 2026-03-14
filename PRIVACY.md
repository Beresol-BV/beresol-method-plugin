# Privacy Policy

**Beresol Method Plugin**
Last updated: 14 March 2026

## Overview

The Beresol Method plugin is a Claude Code plugin that guides users through a structured project-building methodology. This policy explains how the plugin handles data.

## Data Collection

This plugin **does not collect, transmit, or store any personal data**. It has no server-side component, no analytics, no telemetry, and no network requests.

## Local Data

The plugin may create a single local file in your project directory (`.claude/beresol-method.local.md`) to track your progress through the 13-step methodology. This file:

- Is stored entirely on your local machine
- Is never transmitted anywhere
- Is excluded from git by default (via `.gitignore`)
- Can be deleted at any time without consequence

## File Access

The plugin's validation agent reads local project files (e.g. `package.json`, `robots.txt`, `README.md`) to check which methodology steps have been completed. It **never reads the contents of `.env` files** — it only checks for their existence.

No file contents are sent to any external service by the plugin itself. All processing occurs within your local Claude Code session.

## Third Parties

This plugin does not integrate with any third-party services, APIs, or analytics platforms.

## Contact

If you have questions about this privacy policy, contact:

- Email: hello@beresol.eu
- Website: https://beresol.eu

## Changes

Any changes to this policy will be reflected in this file and in the plugin's repository at https://github.com/Beresol-BV/beresol-method-plugin.
