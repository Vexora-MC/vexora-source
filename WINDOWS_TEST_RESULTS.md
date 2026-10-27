# Vexora 0.4.12 — repository staging correction

The Xbox 0.4.11 setup report showed 30 failed repositories, 32 verified and one Kodi-managed repository retained. Failures shared the Wizard error "Managed directory creation was not exclusive". This came from treating a false directory-creation return as a collision before checking the resulting folder.

0.4.12 verifies actual directory existence after creation, uses single-child creation inside an owned staging parent, and reserves staging names with exclusive claim files. Only an invocation with its intact ownership claim may remove its staging folder. Existing folders, files and collisions are retained. Names use the full UUID, monotonic time and a per-interpreter counter rather than a truncated UUID prefix; repeated zero UUID prefixes were visible in the Xbox report. Genuine creation/verification failures still stop setup.

All Vexora first-party packages, nested manifests, repository catalogue and full-build filename align at 0.4.12. The 62 reviewed publisher repository archives and 74-record catalogue are byte-identical to 0.4.11. Original IDs, artwork, versions and upstream update sources remain. The 11 documented exclusions remain. Existing versioned packages are unchanged. Navigation, Sports provider routes, playback and binary dependency policy are unchanged.

## Validation

302 automated tests: 2 privilege-dependent skips and 0 failures. Static skin validation passed. Regressions reproduce false/None SDK creation returns and repeated zero UUIDs with a fixed clock. Tests verify collision handling, preserved foreign files, ownership changes, and successful repository/skin staging without Python directory creation.

Actual disposable Windows Kodi21.3 test: ALL62 repository folders and the Vexora skin were absent before the real Wizard ran. All62 were freshly created, registered and enabled, with no failures or leftover private staging/claim files. One build consent, automatic skin activation and all seven selected providers ready. Normal shutdown/restart retained all three0.4.12 components and all62 enabled repositories. Provider runtime dependencies were preinstalled; this was not a cold dependency-download or physical Xbox test.

Fresh Xbox installation remains UNVERIFIED until the owner retests. Windows-native and simulated backend tests must not be reported as physical console acceptance. The earlier crypto-unavailable report preceded successful selected-add-on setup; this hotfix does not force incompatible dependencies or bundle desktop binaries.

## Update and retry on Xbox

1. Update Vexora Wizard to0.4.12 from the main repository. If the catalogue is stale, use Install from ZIP with zips/plugin.program.vexora/plugin.program.vexora-0.4.12.zip from https://vexora-mc.github.io/vexora-source/ .
2. Restart Kodi normally.
3. Open Wizard / Recovery backups, select the failed setup checkpoint and confirm Undo setup. Backups and downloaded components remain; no version downgrade is performed.
4. Run the full build again. Successfully installed compatible repositories are reused. If recovery or setup reports another failure, retain its report and backups rather than resetting Kodi app data.

Fresh users: add https://vexora-mc.github.io/vexora-source/ in File Manager and install repository.vexora.zip first, then Vexora Repository / Program add-ons / Vexora Wizard.

Full build: vexora-build-0.4.12.zip
SHA256: 742f1436dd4e5fadcc6bfb2de76a547d66b42d0bde23b8d593d24f1946392059
