# Vexora 0.4.3 - installation and recovery

This distribution contains one complete Vexora build: Wizard 0.4.3, skin 0.4.3 and repository 0.4.3. The identical Wizard ZIP is used for Windows PC and UWP/Xbox Kodi 21. There is one source and update channel: https://djmlogistics.github.io/vexora-source/ . Physical Xbox One/Series S/Series X validation is pending; treat the prepared distribution as a release candidate until those checks pass.

## Install after coordinated publication is approved

1. Keep the currently working Vexora installation and export important personal settings. Do not uninstall Kodi or delete its profile.
2. Open Kodi 21. Add the source URL above in File manager. Install `repository.vexora.zip` from that source, reviewing Kodi's security prompts yourself.
3. Install or update Vexora Wizard from Vexora Repository > Program add-ons, and the matching Vexora skin from Look and feel > Skin. Both must be 0.4.3. The Wizard opens Kodi's native version-selection UI if an older skin needs updating; complete that update, then reopen the Wizard.
4. Restart Kodi after updating the Wizard and skin to ensure new widget code is loaded. Open Wizard > Install Vexora build. Read the full-build consent.
5. The same installer validates publisher archives, probes only Kodi's translated add-on/profile directories, backs up affected files and the add-on database, installs and verifies all six repositories through Kodi, verifies skin files and requests skin activation. Confirm keeping the skin if Kodi asks. Cancel stops the operation; failures retain the recovery checkpoint.
6. Choose optional video add-ons during first-run setup or later from their artwork tiles. A tile has one Vexora OK/Cancel install confirmation. Kodi may require its own origin/security/dependency prompts. Kodi resolves required dependencies; ready state is verified before launching.

Mandatory sources are Angelitto and Rising Tides; the build also installs JewRepo, The Crew, Bugatsinho and The Loop repository sources. Optional providers remain in their existing sections. Kids uses TMDB Movies Animation genre16 and Family genre10751, with no third TV row. Genres are not age ratings; this is not a parental-control or child-safe guarantee. Third-party ZIPs are never redistributed in this package.

## Controls

Mouse/keyboard and native remote/controller focus are supported by the same skin. Left/Right selects a main tab, Down enters its controls/poster rows, Up returns to navigation, Select opens the focused entry, and Back/Escape returns or cancels. Press Up from a main tab to reach the neon power symbol. Close Kodi uses native Quit. Force close is desktop Windows only, excluded on UWP/Xbox before importing desktop APIs, and requires confirmation; unsaved state can be lost. Use the console dashboard to terminate an unresponsive Xbox application.

## Recovery on either platform

Wizard > Recovery backups offers native **Undo setup** for newly created backups. It restores the previous skin selection and the original enabled/disabled states of managed skin/repositories through Kodi APIs. Newly downloaded packages are retained but disabled. It checks the profile, managed ID allowlist and original versions before changes; version differences require Kodi's own Versions workflow. Confirm the previous skin if asked. This operation does not downgrade files, restore a live database or remove unrelated add-ons.

Existing pre-0.4.3 backups do not contain enabled-state snapshots and require full offline recovery. A partially completed native undo retains its journal and can be retried. If the previous skin has been removed/disabled, restore/enable it in Kodi first. If setup cannot open, switch to Kodi's bundled skin through Interface settings and reopen the Wizard.

## Full stopped-Kodi restore

For byte-for-byte file/database recovery on Windows, close Kodi completely and run the bundled `tools/restore_build.py` using Python3.11+, supplying the exact backup path and recorded home/profile paths with `--kodi-stopped --home ... --userdata ...`. The tool validates scope, paths and every backup hash before changes. Never run it against a live Kodi database. The package contains this offline utility for exported console backups too, but running desktop Python is not an on-console operation. Native Undo setup is the supported in-Kodi state recovery; full console database restoration remains an owner-assisted recovery task and must be tested separately.

## Previous working release

Skin0.3.6 and Wizard0.3.7 are retained unchanged as the owner-confirmed Windows fallback. Original versioned archives stay at `zips/skin.vexora/skin.vexora-0.3.6.zip` and `zips/plugin.program.vexora/plugin.program.vexora-0.3.7.zip` beneath the same public source. Preserve the current backup and select/install original packages through Kodi's supported native add-on workflow; do not overwrite existing files manually or reuse published version numbers. The initial skin version update precedes the build transaction, so native Undo setup restores selection/state rather than downgrading that update.

## Xbox acceptance required

Before declaring console support, the owner must verify the exact console/Kodi version, source access, sandbox path write/rename/backup behaviour, native installs and dependencies, every main tab, TMDB Kids posters, controller focus/Back/Select, playback controls, cancellation and recovery. Windows tests and simulated UWP flags are not physical-console evidence.


### InputStream Adaptive on Xbox

The publisher documents that InputStream Adaptive is embedded in Kodi on UWP/Xbox and is updated with Kodi itself: https://github.com/xbmc/inputstream.adaptive/wiki/How-to-install-and-get-updates . Use the console's bundled version; do not install a desktop Windows binary ZIP. The dependency audit's windows-x86_64 marker describes the Windows fixture, not a package to ship to Xbox. Native Kodi must confirm the actual console version meets each provider's requirement. DRM and individual media-service compatibility remain provider/platform specific.
