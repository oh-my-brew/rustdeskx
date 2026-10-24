# Third-Party Notices

## RustDesk

RustDeskX redistributes a modified application bundle derived from the official RustDesk macOS arm64 release.

- Project: RustDesk
- Corresponding upstream source: https://github.com/rustdesk/rustdesk/tree/1.4.9
- Source archive: https://github.com/rustdesk/rustdesk/archive/refs/tags/1.4.9.tar.gz
- Pinned release: 1.4.9
- License: GNU Affero General Public License v3.0 (AGPL-3.0); see [LICENSE](LICENSE) and the [upstream license](https://github.com/rustdesk/rustdesk/blob/1.4.9/LICENCE)
- Upstream copyright notices remain in the application bundle.

The modifications performed by this repository are limited to application naming, bundle identifier, URL scheme, executable filename, code signing, notarization, and packaging. RustDeskX is not affiliated with or endorsed by the RustDesk project.


## Rebranding and redistribution sources

The RustDesk binary is taken from the official, SHA-256-pinned arm64 DMG described in
[Config/upstream.env](Config/upstream.env). It is not compiled by this wrapper repository.
The complete wrapper changes are maintained in [Scripts/](Scripts/), with packaging
instructions in [DISTRIBUTION.md](DISTRIBUTION.md). Retain upstream notices in the application.

Each distributed version must identify its exact upstream source version and the matching
RustDeskX wrapper revision, and provide source links alongside the binary download.
When changing the upstream version, update these references and verify source availability
before publication. These links describe the sources; they do not claim a local source build was verified.
