---
title: Afterglow Browser Harness — Privacy Policy
---

# Afterglow Browser Harness — Privacy Policy

_Last updated: 2026-07-04_

Afterglow Browser Harness ("the extension") is a local, developer-facing bridge
that lets an AI assistant you run yourself observe and act on browser pages you
approve. This policy describes what the extension does and does not do with
your data. It is written to be truthful about a tool whose entire design point
is that **your data stays on your own machine**.

## Single purpose

The extension exists to connect the current browser tab to a **local** Afterglow
native host (a program running on the same computer, reachable only over
loopback `127.0.0.1`) so that a coding assistant you operate can read the page
and perform actions you have authorized. It is not an analytics, advertising,
tracking, or content-injection product.

## What data the extension handles

When you authorize a tab, the extension may read, on that tab only:

- page structure and visible text (DOM snapshot, accessibility tree),
- screenshots of the tab,
- console logs and network request metadata (URLs, methods, status — not bodies),
- cookies and storage **for the authorized origin**, when a tool that needs them
  is invoked and the owner has enabled that capability.

This data is passed to the local native host over loopback. The extension
performs the actions you request (click, type, navigate, etc.) on the authorized
tab.

## What the extension does NOT do

- **No remote servers.** The extension talks only to the local native host on
  `127.0.0.1`. It does not send your browsing data to Afterglow, to the author,
  or to any third-party server. There is no telemetry, no analytics, and no
  "phone home."
- **No background collection.** The extension reads a tab only after you click
  its icon (or press the authorize shortcut) on that tab. It does not silently
  watch tabs you have not authorized.
- **No sale or sharing of data.** Because no data leaves your machine through the
  extension, there is nothing to sell or share. We do not sell or transfer user
  data to third parties.
- **No use for advertising or credit purposes**, and no use unrelated to the
  single purpose above.

## Secret handling

Password fields, one-time-codes, and similarly sensitive inputs are redacted by
default before any snapshot or log leaves the page context. Captured URLs and
logs have credentials and sensitive query parameters scrubbed. See
[../SECURITY.md](../SECURITY.md) for the exact redaction rules.

## Local data and your control

All data the harness retains (audit log, replay summaries, optional screenshots,
download metadata, the local access token) is stored **on your computer** and is
listed, with locations and retention, in
[../PUBLIC_ALPHA_TRUST_PACKET.md](../PUBLIC_ALPHA_TRUST_PACKET.md). You can export
or remove it at any time (stop, pause, forget-site, clear-audit, remove-local-data).

## Optional outbound features (off by default)

Fetching "web context" for a public URL can use a **local** self-hosted sidecar
(no external egress). A hosted provider (e.g. Firecrawl) is used **only** if you
explicitly configure its endpoint and key. Nothing outbound is enabled by
default.

## Changes

Material changes to this policy will be reflected in this file with an updated
date, published in the extension's public repository.

## Contact

Afterglow Browser Harness is an open-source project. Questions and reports:
open an issue at the project repository, or contact the maintainer at the email
listed on the repository.
