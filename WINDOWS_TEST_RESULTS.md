# Windows Kodi 21 test results

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
