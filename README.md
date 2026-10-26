# SonyLauncher

SonyLauncher is an independently developed Windows desktop launcher for Minecraft: Java Edition. It is built with Tauri, Rust, React and TypeScript.

**Development preview · Microsoft API approval pending.** This repository publishes application information for players and reviewers. It does not contain the launcher's source code, account data, credentials, or downloadable historical builds.

## What the launcher does

- Creates isolated game instances with their own worlds, configuration and mod files.
- Installs official Minecraft files and compatible Vanilla, Fabric, Quilt, Forge and NeoForge configurations.
- Selects compatible loader versions from the projects' official metadata.
- Obtains the appropriate official Mojang Java runtime when a compatible Java installation is unavailable.
- Manages compatible mods using Modrinth metadata and file hashes.
- Provides installation progress, cancellation, verification and recovery controls.

Modpack browsing/import is under development and is not advertised here as a released feature. The launcher does not offer server hosting, a store, or developer-managed game accounts.

## Microsoft authentication and ownership

The current review-targeted implementation requires a Microsoft account and verifies Minecraft Java Edition ownership before gameplay. The former nickname-only login path has been removed from the UI and IPC, and legacy local nickname profiles cannot launch games. This is an application-wide restriction, not a reviewer-specific switch.

The flow is Microsoft authorization code with PKCE → Xbox Live → XSTS → Minecraft Services → Java entitlement and profile verification. The same checks run before each launch by refreshing the Microsoft session. There is no local nickname, demo-account, environment-variable or network-error fallback for gameplay. Old worlds and profile records remain on the player's device.

Players enter passwords only on Microsoft's own pages in their system browser. SonyLauncher is a public/native OAuth client and embeds no client secret. Refresh tokens use Windows Credential Manager; access tokens remain in Rust memory and are not sent to the frontend.

Our own public Application (client) ID is `b5a5a933-20b8-43e1-8083-1d01c718323e`. Microsoft/Xbox/XSTS authentication has completed in a user test, but Minecraft Services currently returns HTTP 403; final Microsoft-enabled gameplay has not been verified and approval is not claimed.

## Data and privacy

See [PRIVACY.md](PRIVACY.md). No analytics service or developer log-upload backend is implemented. Normal authentication, metadata and download requests go to their respective providers. Game data and launcher settings remain local.

## Availability and testing

This is a development preview. Earlier local installation/runtime tests are not evidence of a successful Microsoft licensed login. The Microsoft-only launch restriction is being validated separately. No installer or older nickname-enabled version is distributed from this information repository.

## Contact

Project owner: [SonyDew](https://github.com/SonyDew). Questions can be raised through this repository's issues. The publisher's Microsoft review contact is supplied privately in the AppID review form.

## Rights and attribution

Copyright © 2026 SonyDew. All rights reserved. See [LICENSE](LICENSE). Application source code remains unpublished; downloading this repository's ZIP retrieves these public information materials only.

Third-party libraries retain their own licenses. SonyLauncher is not affiliated with or endorsed by Mojang, Microsoft, Sony, or their affiliates. Minecraft and Microsoft are their respective owners' marks.
