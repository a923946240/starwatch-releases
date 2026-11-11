# Starwatch releases

Prebuilt Linux packages and the install script for **Starwatch** (巡星), a self-hosted monitor for personal Linux servers. The source code is kept private and is not published here.

## Install or upgrade the Server

Open the release you want under [Releases](../../releases) and copy the full **Install Server** or **Upgrade Server** command from its notes. No GitHub login is needed.

Each command pins the release tag and the SHA256 of the install script. The script then pins both archive SHA256 values and the source commit, checks every file in the package, and only then runs the installer with root or sudo. There is no floating `latest` command.

Requirements: Linux amd64 or arm64, bash, curl, GNU coreutils/tar/gzip, root or sudo.

- First install listens on loopback only. To change that, append `--listen ADDRESS`; for remote access put an HTTPS reverse proxy in front and append `--external-url https://your-domain` (and `--trusted-proxy CIDR` if needed).
- Upgrade keeps the existing configuration, identity and data.
- Agents are installed from your own Server panel, not from this page.

## What is in a release

| Asset | Purpose |
|---|---|
| `starwatch-linux-amd64.tar.gz`, `starwatch-linux-arm64.tar.gz` | Server and Agent binaries, deploy scripts, operations docs, third-party licenses, `SHA256SUMS` |
| `*.sha256` | Checksums for manual review |
| `starwatch-install.sh` | Install script used by the copied command |
| `release-notes.md`, `release.json` | Commands, version, source commit and asset hashes |

The SHA256 values bind to these GitHub Release assets; they are not an independent signature.

## License

Copyright © the Starwatch author. All rights reserved. You may download and run these releases for your own use. Third-party components keep their own licenses, included under `licenses/` in each archive.
