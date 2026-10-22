# Windows Kodi 21 test results

## 0.3.0 repository test update

Available test versions: Wizard 0.3.0, skin 0.3.0 and Vexora Repository 0.2.2. This is a user-testable development update, not a claim that new runtime acceptance is complete. Previous skin 0.2.6 and Wizard 0.2.13 archives remain available as fallback (avoid Wizard 0.2.12).

Existing installation: open Kodi Add-on browser > Check for updates. Update Vexora Repository to 0.2.2 first, then Vexora Wizard and Vexora skin to 0.3.0 through Vexora Repository (Program add-ons / Look and feel > Skin), or Available updates. If a version is not shown, refresh repository updates and reopen its listing. Reopen Wizard > Install Vexora build to back up affected files and install/verify all six publisher repositories; updating the skin alone does not run build setup.

New UI includes KIDS after TV SHOWS, TMDB poster rows, separate Sports tiles, four additional native repository sources, and direct single-add-on OK/Cancel installation. Kodi security/origin/dependency confirmations remain Kodi-owned. Optional video add-ons stay optional; Crew is shared by Movies, Sports and Kids. Third-party packages are downloaded from publishers and never bundled.

Automated suites: 147 passed, two Windows symlink skips before version bump. Current native evidence: eight tabs render, Movies artwork/metadata loads and missing-Crew Kids fallback works. Populated Kids artwork/ratings/selection, all additional native installs and full upgrade acceptance still need testing. Kids hides unrated or disallowed certification metadata; it is not certified child-safe. Xbox is queued after Windows acceptance and is not supported by this test claim.

The results below describe earlier versions and must not be read as acceptance of every 0.3.0 feature.

Validated on 21 October 2026 using Windows Kodi 21.3 and disposable portable profiles. Personal Kodi data was not modified.

Packages: Vexora Repository 0.2.1; Vexora Wizard 0.2.9; Vexora skin 0.2.4.

| Acceptance check | Result |
| --- | --- |
| Add source > ZIP bootstrap > repository > Program add-ons > Wizard | Passed in Kodi |
| Full-build consent, preflight, backup and installed-file verification | Passed |
| Native hosted Angelitto 1.0.2 and Rising Tides 1.1 installs | Passed; enabled versions and exact installed contents verified |
| Keep-skin confirmation and persistent Vexora activation | Passed |
| Seven Home sections, artwork and keyboard/mouse navigation | Passed available navigation checks |
| Movies/Sports available and installed artwork states | Passed |
| TMDB Movies 1.1.320 native dependencies and root launch | Passed |
| Rising Tides 3.2.10.9 native dependencies and root launch | Passed |
| On-screen keyboard, remote key selection, Backspace, physical input and cancel | Passed |
| Manual preview skin 0.1.0 > native hosted skin 0.2.4 > complete build | Passed |
| Offline rollback, exact restored hashes, removed build-created folders, SQLite integrity and restart | Passed |
| Automated root suite | 76 run: 74 passed, 2 Windows symlink skips |
| Kodi adapter suite | 35 passed |
| Skin suite | 7 passed |
| Packaging suite | 1 passed |

Total automated result: 117 passed, 2 skipped, 0 failed. GitHub Actions also runs the staging suites on Windows and Linux.

The runtime checks verify installation and launch readiness. They do not establish availability or operation of any third-party media service. Media playback and account authentication were not tested. Live TV correctly displays Kodi's PVR setup prompt without a configured backend; channel playback remains untested. Other target platforms remain untested. This is a Windows development test build, not a production release.

Use WINDOWS_INSTALL.md for installation, legacy updates and rollback. Third-party packages are downloaded by Kodi from their publishers and are not included in the Vexora distribution.

## Pointer and playback overlay correction (skin 0.2.6)

The earlier acceptance did not exercise actual media playback controls. User reports exposed a missing cursor implementation, absent VideoOSD/MusicOSD and empty seek/volume placeholders. Skin 0.2.6 includes cursor states, audio/video playback controls, seek timeline and compact status overlays; Wizard 0.2.12 bundles the same skin version.

Windows Kodi 21.3 disposable-profile checks used original generated local MJPEG AVI and PCM WAV fixtures. Confirmed visible cursor; video play/pause speeds 1/0; Forward 2; Rewind -2; mouse Stop leaves no active players; timeline click seeks exactly 50% / 01:30 of 03:00; Volume - changes 100 to 99 and Volume + restores 100; Mute changes native mute state. M opens video/audio OSD; keyboard Right then Enter stops audio after verified Stop focus. Fullscreen audio shows its title/control hint. Seek slider orientation/proportions corrected after runtime inspection. Original test skin preserved separately; no personal profile changed.

These checks cover local media and native player actions. They do not establish third-party stream reliability, live-stream seek support, external-player controls or passthrough volume behavior. Seeking/pause controls respect Kodi capability flags.
