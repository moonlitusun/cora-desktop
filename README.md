# Cora Desktop

Release artifacts for the Cora desktop app. Development happens elsewhere; this
repository builds and hosts the published installers. The build workflow checks
out the private source with a read-only deploy key and runs here, where Actions
is not billed against the private repository's budget.

## Download

Grab the newest installer from the [latest release](https://github.com/moonlitusun/cora-desktop/releases/latest):

| Platform | File |
| --- | --- |
| macOS (Apple Silicon) | `Cora_<version>_aarch64.dmg` |
| Windows (x64) | `Cora_<version>_x64-setup.exe` |

Neither installer is OS code-signed yet, so macOS Gatekeeper and Windows
SmartScreen warn on first launch.

## Updates

On startup the app reads `latest.json` from the latest release here and offers
to install any newer version. Update packages carry a minisign signature that
is verified before anything is installed.
