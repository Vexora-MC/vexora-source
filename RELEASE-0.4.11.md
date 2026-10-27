# Vexora 0.4.11 — Xbox fresh-install directory hotfix

The owner photographed a fresh Xbox Kodi21.2 failure in skin_staging: pathlib.mkdir attempted to create/check LocalState/addons,then traversed protected package parents and ended in WinError2/183/5. Managed skin/repository directories and private staging folders now use Kodi xbmcvfs.exists/mkdirs/mkdir. Each created directory must be verified;failed operations still fail installation. Cleanup is limited to the exact private staging directory created by this invocation. Existing security/path/hash checks,backups,native registration and update sources remain.

All current first-party versions align at0.4.11:Wizard,skin,repository,catalogue,bundled skin/repository and build filenames. The62publisher repository archives and74-record catalogue are byte-identical to0.4.10. Publisher IDs,versions,artwork and update URLs are unchanged. No navigation,artwork,Sports routes or playback behavior changed. Versioned0.4.10 packages remain unchanged.

## Validation

298 automated tests,2 privilege-dependent skips,0 failures;static skin validation passed. Regression staging succeeds with Python Path.mkdir and Python tempfile staging disabled while Kodi directory operations remain available. Tests also reject failed directory creation and unowned/colliding staging directories.

The final archive completed the actual Wizard flow in disposable Windows Kodi21.3 with the Vexora skin initially absent and provider dependencies preinstalled. One build confirmation,automatic activation,all seven selected providers ready,62external+1Kodi-managed+11exclusions. Normal restart retained all three0.4.11 components enabled and the active skin;Football still returned10game cards.

This is native Windows and simulated sandbox evidence,NOT physical Xbox verification. Fresh0.4.11 console installation requires owner retest. The photographed fresh0.4.10 failure supersedes earlier successful upgrade/playback acceptance.

## Update and retry the failed Xbox setup

1. Update Vexora Wizard to0.4.11 from Vexora Repository. If the catalogue has not refreshed,use Install from ZIP with zips/plugin.program.vexora/plugin.program.vexora-0.4.11.zip at https://vexora-mc.github.io/vexora-source/ .
2. Restart Kodi normally to load the new Wizard.
3. Open Vexora Wizard / Recovery backups,select the failed setup checkpoint and confirm Undo setup. This restores previous skin/enabled states and marks the interrupted transaction recovered;downloaded packages and backups remain. A newer own repository whose enabled state already matches is retained without downgrade. Other changed-version recovery guards remain.
4. Run the full build again and confirm once. Do not manually delete app data or backups. If recovery reports another error,retain the backup and report it before further changes.

Fresh installations:File Manager source https://vexora-mc.github.io/vexora-source/ ;install repository.vexora.zip FIRST,then Vexora Repository / Program add-ons / Vexora Wizard.

Full build:vexora-build-0.4.11.zip
SHA256:2b325867c4265f44354b65e3042555ba55a4c3ef2569611f031be97015ebd54c
