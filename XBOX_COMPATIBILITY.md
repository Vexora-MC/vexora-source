# Vexora universal compatibility - release candidate 0.4.0

One Wizard ZIP, matching skin and repository index are used for Windows PC and UWP/Xbox. There is no separate console build/channel. Known-good source is fix/kids-tmdb-release-037 at c8a0854ec15ea6dbc1215b236d627ba988d86030 (owner-confirmed Windows skin0.3.6/Wizard0.3.7). Current candidate preserves TMDB Movies Kids Animation16/Family10751 and the rest of the existing catalogue/design.

## Implemented compatibility work

- Kodi special-path resolution and managed-directory write/rename/read probes after consent; protected ancestor access-denied handling and link/reparse rejection remain.
- Desktop Force close explicitly excludes UWP before importing ctypes. Native Close remains; on console use the dashboard for forced termination. A regression makes ctypes unavailable and verifies the UWP path still returns safely.
- Native setup-state undo for new backups: profile-bound allowlisted journal, preflight version checks, previous skin selection and original enabled states through Kodi APIs, observed completion, retained retry journal. It never overwrites Kodi's live database or downgrades files. Existing stopped-Kodi full restore remains separate.
- Explicit directional navigation audited across skin XML; invalid file/PVR focus references corrected. Physical controller ergonomics are not inferred from XML checks.
- Native Windows candidate checks returned21 entries in Movies/TV/Kids Animation. Actual Kodi API undo restored a simulated pre-setup disabled repository state and the fixture's original enabled state was restored afterward. No personal profile modified.
- Successful catalogue directories can be reused through native caching. First-load/network and physical-console performance are not guaranteed.

## Dependency audit

UNIVERSAL_DEPENDENCY_AUDIT.json follows57 declared provider/repository/runtime dependency IDs using reviewed archives, installed Windows fixture metadata, publisher index snapshots and reference manifests. No declared ID lacked a metadata record in those sources. Provenance is explicit; snapshots are not console runtime proof and null binary-file observation means files were not inspected for that record.

InputStream Adaptive is a native component; the Windows fixture's windows-x86_64 platform is not redistributable to Xbox. The upstream project states UWP/Xbox receives InputStream Adaptive embedded with Kodi and updates with Kodi itself: https://github.com/xbmc/inputstream.adaptive/wiki/How-to-install-and-get-updates . The installer continues using native Kodi dependency resolution and actual installed manifests, never copying a Windows binary into the console package. Provider/DRM support must be verified on the target device.

## Remaining physical acceptance and limits

No Xbox device is connected. Verify Kodi version/source reachability, UWP sandbox probes/backup, native six-repository/provider/dependency installation, controller Select/Back/rows/settings/numeric dialogs, playback and recovery on Xbox One/Series S/Series X before claiming validated support. Native Undo setup restores selection/enabled states, not complete previous binary/file versions. Full byte-for-byte console database recovery requires Kodi stopped and exported backup handling; no in-process live-database restore is attempted.

The prepared package is a coordinated release candidate. Do not describe physical Xbox installation/controller/playback as passed. Publication and the single final Actions run remain subject to the owner's no-push/no-publication approval gate.
