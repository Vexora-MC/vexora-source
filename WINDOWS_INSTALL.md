# Vexora Windows / Kodi 21 test build

Portable Windows installation testing passed for Vexora Wizard 0.2.9, skin 0.2.4 and Vexora Repository 0.2.1 on Kodi 21.3. This is a development test build, not a production release. See WINDOWS_TEST_RESULTS.md for evidence and limits.

## Install the complete build

1. Install and open Kodi 21 Omega on Windows.
2. Kodi Settings > File manager > Add source.
3. Enter https://djmlogistics.github.io/vexora-source/ and name it Vexora.
4. Add-ons > Install from ZIP > Vexora > repository.vexora.zip. If Kodi requires Unknown sources, review its warning and enable it yourself.
5. Install from repository > Vexora Repository > Program add-ons > Vexora Wizard > Install.
6. Open Vexora Wizard > Install Vexora build and accept the whole-build consent.
7. Complete Kodi's native installation prompts. The Wizard downloads the original skin and BOTH mandatory repositories from hosted HTTPS sources, validates them and verifies the installed files.
8. Keep the Vexora skin when Kodi asks. Success is reported only after activation is confirmed.
9. Movies and Sports display artwork tiles. An available tile requests native add-on installation; an installed tile launches only after enabled-state and transitive-dependency verification.

Only the initial Vexora Repository bootstrap uses Install from ZIP. No computer-local third-party ZIP selection is required. Neither mandatory repository has a separate decline path: canceling either cancels the build. The Wizard backs up affected folders, settings and a consistent add-on database before deployment.

Mandatory repositories are Angelitto 1.0.2 and Rising Tides 1.1. Video add-ons are optional: TMDB Movies 1.1.320 and Rising Tides 3.2.10.9 were installed and launched during testing. No third-party ZIPs are redistributed in Vexora.

## Existing Vexora preview skins

If an older manually installed Vexora skin is present, the Wizard opens Kodi's Vexora Repository skin listing before deployment. Select Vexora and use Install, Update or Versions as offered by Kodi to install the version requested by the Wizard. Accept Kodi's replacement confirmation, then reopen the Wizard > Install Vexora build. Update the Wizard first if its requested skin version is unavailable. This flow was tested from manual skin 0.1.0 to hosted skin 0.2.4.

The legacy skin replacement is a separate Kodi update before the new build transaction. Preserve any custom legacy skin edits before replacing it.

## Recovery

Backups are in special://profile/addon_data/plugin.program.vexora/backups/build-ID/transaction.json. Failed or interrupted deployment retains a recovery_required journal. Close Kodi before restoring.

Download vexora-recovery-tools.zip from the same public source, extract it, and use Python 3.11 or newer:

```powershell
python tools/restore_build.py "C:\path\to\backup\build-ID" --kodi-stopped --home "C:\path\to\KodiData" --userdata "C:\path\to\KodiData\userdata"
```

Use the exact Kodi data paths from the transaction journal; the home argument is the Kodi data directory containing addons, not the application executable directory. Recovery verifies hashes and target paths before restoring settings, affected folders and the add-on database. It removes build-created folders that were absent before installation. Libraries and unrelated files are preserved. Optional add-ons installed later remain separate Kodi-managed installations.

## Limits and package choice

Live TV requires your own configured PVR client and channel source. Installation, navigation and add-on root launches were tested; media playback, external accounts and PVR channel playback were not. Android, Fire TV and Xbox have not been validated.

For the downloadable Windows test bundle, use the GitHub Actions artifact named vexora-windows-kodi21-test-build. It contains this guide, test results, the repository bootstrap, original Wizard/skin packages, checksums and recovery tools. GitHub access to the private development repository is required; ordinary Kodi users can install using the public source URL.

The separate vexora-build-development.zip is a developer staging payload, not a Kodi ZIP installer; its install_ready=false marker remains intentional. Install the complete build through Vexora Wizard.

## App-container access-denied fix (Wizard 0.2.10)

Wizard 0.2.10 fixes parent-folder inspection failing with WinError 5 beneath a protected Kodi app-package directory. Actual target access failures still stop setup; links and Windows reparse points remain rejected. Update Wizard through Vexora Repository before retrying. Do not change package-folder permissions or run Kodi as administrator to work around this error. Regression tests simulate the restricted ancestor; Windows Store/Xbox runtime validation remains outstanding.

## Mouse pointer and playback controls (skin 0.2.6)

Update Vexora under Install from repository > Vexora Repository > Look and feel > Skin to 0.2.6; update Vexora Wizard to 0.2.12 as well to keep its bundled skin version aligned. Restart Kodi after the update. Reinstalling the full build is not required for these skin fixes.

During fullscreen playback, move the mouse or press M / OK to show the controls. Play/pause, Stop, Rewind, Forward, Volume -/+, Mute and a clickable seek timeline are available. Use arrows and OK with a keyboard or remote; Back closes the overlay. Seeking and pause availability follow the playing stream's capabilities. Audio passthrough may require volume adjustment on the receiver.
