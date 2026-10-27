# Vexora 0.4.13 — automatic skin handoff correction

The owner reported Xbox setup remaining on Activating and verifying Vexora interface. After restarting, the installed skin worked when selected manually. This release waits until the native progress dialog is no longer visible before requesting a skin switch, rather than treating close() as an immediate GUI barrier. If it does not close within ten seconds, the switch is not dispatched. The exact consent-scoped skin confirmation observer starts before dispatch. Unrelated dialogs are never approved. Stage-only diagnostics identify handoff progress without personal URLs or credentials.

306 automated tests, two privilege-dependent skips, zero failures; static skin validator passed. Actual Windows Kodi21.3 final packaged Wizard installation with skin initially absent passed automatic activation and summary. Normal restart verification is documented separately. Provider dependencies were preinstalled: this is not a cold dependency-download test. Physical Xbox correction is not yet verified; owner retest is required before recommending it to family. This addresses observed timing risks; it cannot guarantee every device/network succeeds.

All first-party versions align0.4.13. All62 upstream repository ZIPs and the74-record catalogue are unchanged. All previous versioned ZIPs are preserved. Navigation, playback, artwork and dependency policies are unchanged.

Fresh installation: add https://vexora-mc.github.io/vexora-source/ in Kodi File Manager, install repository.vexora.zip, then Vexora Repository / Program add-ons / Vexora Wizard. Run the full build once. Undo is not a fresh-install prerequisite. Existing working0.4.12 installations do not need to reinstall the full build; allow the Wizard update. Keep recovery backups.

Full build: vexora-build-0.4.13.zip
SHA256: 6179398d0001a0b40459ffcab961876d474f60b06411b25ddc2639b63988191b
