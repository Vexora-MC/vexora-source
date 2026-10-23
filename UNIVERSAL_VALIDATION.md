# Vexora 0.4.0 validation record

Status: coordinated universal release candidate, not yet published. The same Wizard and skin bytes target desktop Windows and UWP/Xbox; no per-platform packages, release branches, indexes or channels are created. Physical Xbox testing is pending.

## Baseline

Primary known-good source: `fix/kids-tmdb-release-037`, commit c8a0854ec15ea6dbc1215b236d627ba988d86030. Full-build Actions run39863806880 completed successfully. The owner confirmed the published skin0.3.6/Wizard0.3.7 works on Windows. That source was merged with preserved local work. Public Wizard/skin archive identity, integrity, nested manifest and hosted/bundled equality were also verified during handover reconciliation. Existing Windows functionality/design and TMDB Kids genre routes are preserved.

## Compatibility changes

- Automatic platform capability detection, Kodi special-path resolution and write/rename/read/cleanup probes inside managed data roots after installation consent.
- Desktop Force close excludes UWP before importing ctypes; native Close is retained. Controller focus audit corrected dangling targets in FileBrowser/PVR screens.
- New backup journals record original managed-addon states. Native Undo setup restores skin selection/enabled states through Kodi, without rewriting a live database; old full backups and desktop offline restore remain available.
- Successful Movie/TV/Kids directories use Kodi caching; failures and install fallbacks remain uncached. Installed-state tiles remain fresh. No measured performance gain is claimed until native revisit/refresh measurements complete.
- Kids empty-provider action now points to the actual TMDB Kids tile key.

## Test evidence

Local Windows Python/XML/security/recovery/packaging suites are the primary validation. Detailed final counts and archive hashes are recorded in `release-manifest.json`/`SHA256SUMS.txt` in the prepared output and the development checkpoint. Tests cover protected sandbox ancestors, path traversal/reparse rejection, archive identities/hashes, Windows/UWP capability matrix, native undo scope/version/failure checks, cache behaviour, controller focus and package consistency.

No physical Xbox One, Series S or Series X was available. All console filesystem/controller/playback/native-dependency outcomes remain unverified. Third-party publishers control dependency availability and media services; no third-party redistribution permission is inferred. Animation/Family genres are not age ratings.

## Actions budget

No new Actions run was triggered during recovery or local compatibility work. The connected GitHub tool cannot access account billing/remaining Actions allowance; this is unavailable, not zero. Prepare one manual final validation run after local checks and publication approval. Avoid push/PR-triggered matrix runs by using a single coordinated commit with CI skipped for the push, then one explicit manual staging workflow. Do not disable failure notifications.

## Release approval

Prior explicit no-push/no-publish requirement remains observed while this candidate is prepared locally. Publication must be coordinated: all new Wizard/skin/bootstrap ZIPs, index, MD5 and SHA256 metadata and guides together. Physical-console acceptance or a clearly approved release-candidate publication is required before describing Xbox support as validated.


### InputStream Adaptive on Xbox

The publisher documents that InputStream Adaptive is embedded in Kodi on UWP/Xbox and is updated with Kodi itself: https://github.com/xbmc/inputstream.adaptive/wiki/How-to-install-and-get-updates . Use the console's bundled version; do not install a desktop Windows binary ZIP. The dependency audit's windows-x86_64 marker describes the Windows fixture, not a package to ship to Xbox. Native Kodi must confirm the actual console version meets each provider's requirement. DRM and individual media-service compatibility remain provider/platform specific.


## Local native Windows evidence for universal candidate

The disposable Kodi 21.3 profile was backed up before staging original Vexora candidate code. Native Files.GetDirectory returned21 movie entries,21 TV entries and21 TMDB Kids Animation entries. Two movie directory queries measured2.859s then0.969s; TV0.797s then0.828s. These are single local observations with existing Kodi/provider caches, not a general performance benchmark or causal proof. Provider entries retain their original URLs/art.

Exercised the new native-undo engine against actual Kodi JSON-RPC: captured a disabled Angelitto repository state, enabled it to simulate setup, restored its recorded disabled state via Addons.SetAddonEnabled and confirmed the previous skin setting via Settings.SetSettingValue. Then restored the disposable profile's original repository enabled state. No live database/file restore was attempted and no personal profile was modified. Full first-run/physical Xbox recovery acceptance remains pending.

## Final local candidate checks

2026-10-23: root suite 115 tests (113 passed, 2 skipped), Kodi adapter 35 passed, skin/controller/theme 20 passed, packaging tools 1 passed: 169 passed, 2 skipped. The final skin run includes UWP power-menu focus and missing native settings templates. An initial rerun used an inaccessible sandbox TEMP; rerunning with workspace TEMP passed. Runtime compilation and diff whitespace checks passed. These are local checks, not a new CI result.

Candidate output: dist/universal-release-0.4.0/vexora-universal-0.4.0.zip, with per-package and outer SHA256 metadata. The installable Wizard ZIP is inside source/zips/plugin.program.vexora; the outer archive is the complete coordinated repository delivery, not itself a Kodi add-on ZIP. No third-party ZIPs are included. Fresh full 0.4.0 installation and physical Xbox acceptance remain pending. No push or Actions was triggered.

## Coordinated 0.4.2 Xbox fix

Wizard, skin, repository and bundled skin manifest all declare0.4.2. This supersedes the briefly published Wizard-only0.4.1 without overwriting it. Fixes the observed Xbox missing-os.fsync traceback in probes and journal writes. Optional sync preserves desktop behaviour, while Xbox retains flush/close/atomic rename/readback without a physical disk-sync guarantee. Strict version alignment, package SHA256, hosted/bundled skin equality and absent-fsync regressions are checked locally. Physical Xbox retry pending; no new CI run claimed.

## 0.4.3 Xbox diagnostics

Aligned Wizard/skin/repository0.4.3 retains missing-fsync fix. A caught setup failure now writes a full traceback to Kodi LOGERROR and displays details automatically, including errors importing build_manager. This repairs the missing error-reporting path; it does not claim the remaining Xbox LocalState failure has been resolved. No physical Xbox success claimed. No extra Actions validation run.

## 0.4.4 confirmed Xbox backup path fix

Native Xbox traceback identifies WinError5 specifically in pathlib.resolve/_getfinalpathname while recording backup root, after the write probe. Checked profile identity now uses lexical absolute normalization only when resolve raises WinError5; detected links/reparse points and actual I/O errors remain failures. Native recovery uses the same identity rule. Regression runs backup/journal/recovery with resolve denied and rejects wrong profiles/other errors. This is a targeted sandbox compatibility fix; complete physical installation still awaits owner retry. All components and skin manifest0.4.4.

## 0.4.5 controller navigation

Fixes group-list numeric navigation being replaced by Kodi: Movies/TV/Kids rows now use explicit SetFocus actions and section group exits. Skin21 tests pass. Source evidence https://github.com/xbmc/xbmc/blob/Omega/xbmc/guilib/GUIControlGroupList.cpp AddControl. Xbox physical retry pending. Components aligned0.4.5; missing-fsync and final-path backup fixes retained.
