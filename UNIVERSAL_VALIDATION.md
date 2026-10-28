# Vexora 0.4.15 - native skin update dependency

The owner reports that Xbox updates Vexora Wizard and the repository but leaves the Vexora skin behind. A previously staged skin can have an empty repository origin, so Kodi does not list a private-repository update for it even though the Wizard detects a newer release on the website.

Wizard0.4.15 now requires skin.vexora minimum0.4.15. During the working native Wizard update, Kodi resolves the matching skin dependency, installs it from the repository and records its origin itself. Future releases must keep that dependency aligned; both packaging and source validation reject a missing, stale, optional or duplicate skin requirement. No product code writes Kodi's database, changes update policy or replaces the full build silently. The existing repository requirement remains and there is no circular dependency.

## Validation

314 automated tests:253main,35legacy installer,25skin,1tools;two privilege-dependent skips,zero failures. Static skin validation passed.

Actual Windows Kodi21.3 automatic upgrade test with the final packages: Wizard14 had a working repository origin and skin14 deliberately retained an empty origin. Kodi automatically fetched Wizard15 and skin15, enabled both, and assigned repository.vexora as the skin origin. Only the Wizard origin was prepared offline in the disposable fixture to reproduce the owner's reported starting state; neither test nor product wrote the skin origin. A loopback-only feed served the exact unchanged candidate archives; shipped URLs remain production HTTPS.

A separate first-install native check with both Wizard and skin absent installed both15 through Kodi's dependency resolver and assigned both origins. The installed skin matched the final archive exactly. Actual full-build setup subsequently preserved the native skin origin and activated Vexora. Normal shutdown/restart checks retain the skin, all3aligned components, their repository origins and all62 enabled third-party repositories. Other provider runtime dependencies were preinstalled; this is not a cold full-ecosystem download or physical Xbox test.

The62 reviewed publisher repository ZIPs and74-record catalogue are byte-identical to0.4.14. Skin interface, artwork and resources are unchanged except its version manifest. Football Live competition rows and Mad Titan Boxing are retained. All previous versioned ZIPs are immutable.

## Existing installation

Keep the existing Xbox installation. Restart Kodi normally and allow its repository/Wizard update to complete according to Kodi's configured policy. Wizard0.4.15 now requires skin0.4.15; Kodi should download the skin automatically as that dependency. Restart Kodi after updating, then check Settings / Interface / Skin / Vexora information for0.4.15. No fresh install, full-build reinstall or Undo is required for this repair. If the Wizard itself cannot update, install the versioned Wizard ZIP from the main source once and report the result; the owner's reported Wizard update path already works.

Physical Xbox automatic updating remains pending owner confirmation. Native Windows success must not be presented as physical console verification.

## Fresh installation

Add https://vexora-mc.github.io/vexora-source/ in Kodi File Manager. Install repository.vexora.zip first, then Vexora Repository / Program add-ons / Vexora Wizard. Kodi installs the matching skin as a dependency; open Wizard / Full build for the coordinated setup and automatic activation. Keep Kodi's own required security prompts. Undo is not a fresh-install prerequisite.

Full build: vexora-build-0.4.15.zip
SHA256: 1d5f95c628727833ea7a56f3fd01679e169b4dbb922b5137e51966b94bcb41ae
