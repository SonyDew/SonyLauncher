# Privacy policy



## Local storage

Launcher settings and profile metadata are stored locally using SQLite. Instance folders contain worlds, mods, configuration and game logs. Refresh tokens are stored using Windows Credential Manager. Access tokens remain in Rust process memory and are not exposed through the frontend IPC API. Passwords are entered only on Microsoft pages in the system browser.

The default game-data directory is `%APPDATA%\SonyLauncher\minecraft`. You can choose a different location in settings.

## Network requests

Microsoft, Xbox Live and Minecraft Services receive requests needed for sign-in, token exchange, entitlement and profile checks. Mojang's services provide official game metadata, files and Java runtimes. Fabric, Quilt, Forge, NeoForge and Modrinth endpoints are used when their corresponding content is requested. Those providers apply their own terms and privacy practices and may receive the user's IP address and ordinary request metadata.

SonyLauncher does not collect analytics, display advertising or automatically upload logs. Authentication tokens are not included in error messages.

## Removal and support

Signing out removes the corresponding launcher profile and its stored refresh token. Game worlds are separate from account records and are not deleted by signing out. Gameplay requires Microsoft authentication and Java entitlement verification.

For project questions, use this repository's issues. Do not post passwords, authentication codes, tokens, private game logs, or account identifiers in a public issue.
