# SonyLauncher

SonyLauncher is an independently developed Windows desktop launcher for Minecraft: Java Edition. It is built with Tauri, Rust, React and TypeScript.

**Development preview · Microsoft API approval pending.** This repository publishes application information for players and reviewers. Application source code, account data and credentials are not published here.

## What the launcher does

- Creates isolated game instances with their own worlds, configuration and mod files.
- Installs official Minecraft files and compatible Vanilla, Fabric, Quilt, Forge and NeoForge configurations.
- Selects compatible loader versions from the projects' official metadata.
- Obtains the appropriate official Mojang Java runtime when a compatible Java installation is unavailable.
- Manages compatible mods using Modrinth metadata and file hashes.
- Provides installation progress, cancellation, verification and recovery controls.

## Microsoft authentication and ownership

SonyLauncher requires a Microsoft account and verifies Minecraft Java Edition ownership before gameplay.

The flow is Microsoft authorization code with PKCE → Xbox Live → XSTS → Minecraft Services → Java entitlement and profile verification. Authentication and ownership checks run before every game launch. Worlds and profile records remain on the player's device.

Players enter passwords only on Microsoft's own pages in their system browser. SonyLauncher is a public/native OAuth client and embeds no client secret. Refresh tokens use Windows Credential Manager; access tokens remain in Rust memory and are not sent to the frontend.

Our own public Application (client) ID is `b5a5a933-20b8-43e1-8083-1d01c718323e`. Access to Minecraft Services is pending approval; successful licensed gameplay through this application has not yet been verified.

## Data and privacy

See [PRIVACY.md](PRIVACY.md). No analytics service or developer log-upload backend is implemented. Normal authentication, metadata and download requests go to their respective providers. Game data and launcher settings remain local.

## Availability and testing

This is a development preview. Installation and runtime components are tested separately from Microsoft Services access. Native checks verify that gameplay is denied when authentication is unavailable. No installer is distributed from this information repository.

## Contact

Project owner: [SonyDew](https://github.com/SonyDew). Questions can be raised through this repository's issues. The publisher's Microsoft review contact is supplied privately in the AppID review form.

## Rights and attribution

Copyright © 2026 SonyDew. All rights reserved. See [LICENSE](LICENSE). Application source code remains unpublished; downloading this repository's ZIP retrieves these public information materials only.

Third-party libraries retain their own licenses. SonyLauncher is not affiliated with or endorsed by Mojang, Microsoft, Sony, or their affiliates. Minecraft and Microsoft are their respective owners' marks.
