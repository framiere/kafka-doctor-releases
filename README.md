# Kafka Doctor downloads

Official native collector downloads for macOS, Linux and Windows. The product source repository remains private; this repository contains release files and download instructions only.

**[Browse published releases](https://github.com/framiere/kafka-doctor-releases/releases)** · **[Latest stable release](https://github.com/framiere/kafka-doctor-releases/releases/latest)**

There are no binaries until the first release is published. Pre-releases appear in the full release list and do not replace the latest stable version.

| Computer | Release file |
| --- | --- |
| macOS, Apple silicon | `doctor-darwin-arm64` |
| macOS, Intel | `doctor-darwin-amd64` |
| Linux, x86-64 | `doctor-linux-amd64` |
| Linux, ARM64 | `doctor-linux-arm64` |
| Windows, x86-64 | `doctor-windows-amd64.exe` |
| Windows, ARM64 | `doctor-windows-arm64.exe` |

Choose the computer that can reach Kafka, which may differ from your browser. No JVM, Node installation or Docker runtime is required to run a native collector. A build for a platform does not by itself prove connected collection on that platform.

Each release includes six native files, six adjacent `.sha256` files, `SHA256SUMS` and `manifest.json`. The manifest records the source revision and artifact hashes. Verify the chosen file against its adjacent checksum:

```sh
# macOS
shasum -a 256 -c doctor-darwin-arm64.sha256
chmod u+x doctor-darwin-arm64
./doctor-darwin-arm64 version

# Linux
sha256sum -c doctor-linux-amd64.sha256
chmod u+x doctor-linux-amd64
./doctor-linux-amd64 version
```

On Windows PowerShell, compare `Get-FileHash .\doctor-windows-amd64.exe -Algorithm SHA256` with the adjacent checksum, then run `.\doctor-windows-amd64.exe version`.

Downloading or checking a version does not connect to Kafka. Only start a collector on a machine you intend to analyze from, following the instructions on your Kafka Doctor service.

SHA-256 checks detect changed bytes; they are not code signatures or notarization. The automatic “Source code” archives GitHub adds to a release contain only this distribution repository, not the private product source.
