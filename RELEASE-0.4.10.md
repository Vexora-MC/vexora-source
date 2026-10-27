# Vexora 0.4.10 production release

Promoted from the owner-accepted0.4.10~test4 build. The owner explicitly reported all Xbox and PC testing OK and authorised production publication and removal of test sources. Agent verification uses disposable Windows Kodi21.3; the agent did not physically operate an Xbox.

All current first-party components use0.4.10: repository.vexora,plugin.program.vexora,skin.vexora,the full-build filename,hosted catalogue,release manifest and bundled skin/repository manifests. All update channels point to https://vexora-mc.github.io/vexora-source/ . Third-party publishers retain their original IDs,versions and update sources.

## Included changes

One complete-build consent covers the original seven repositories and the expanded deduplicated ecosystem:62 verified external repository archives+1Kodi-managed repository+11 explicit exclusions account for74 records. No desktop runtime binaries are bundled. Kodi resolves native dependencies. Safe backups,cancellation,retries,recovery and delayed startup update checks remain. No silent whole-build replacement.

Automatic skin activation and restart persistence. Authoritative installed/disabled/missing add-on tile states,including RisingTides. Kids Animation/Family preserved. LiveTV navigation removed;noMusic section. Sports Boxing row dynamically uses MadTitan LiveSports/Boxing;Football row enters BOTH RisingTides PL ALL GAMES CLICK HERE SERVER1/SERVER2 folders and displays their games directly,not menu links. Provider art/playback URLs retained;no fixed event URLs.

## Validation

291 automated tests,2 privilege-dependent skips,0failures. Actual stable0.4.8->0.4.10 native Wizard upgrade:one selection dialog,ONE full-build confirmation,summary visible,all seven providers installed/dependencies ready,repository report registered,skin.vexora activated. After clean normal shutdown/restart,repository/Wizard/skin0.4.10 all enabled and active skin persisted. Stable Football directory returns10 game cards. Native source/checksum/version/channel validation passed. Xbox/PC physical acceptance is owner-reported for the tested baseline;stable-ID packaging/upgrade is agent-verified on Windows.

## Install or update

Kodi FileManager/Addsource: https://vexora-mc.github.io/vexora-source/

Install repository.vexora.zip FIRST. Then Installfromrepository/VexoraRepository/Programaddons/VexoraWizard. Existing production users can check repository updates and update to0.4.10. Open Wizard and choose the full build to apply coordinated configuration/skin upgrades;confirm once.

Existing TEST users: test identities are separate and do not turn into production through updates. Install the production repository and production Wizard above,run the complete build,then remove the old TEST repository/Wizard/skin through Kodi after production is active. Remote test sources are being retired after live production verification. A fresh isolated install remains the cleanest migration path;avoid manually deleting active skin files or databases.

Wizard: zips/plugin.program.vexora/plugin.program.vexora-0.4.10.zip
Repository: zips/repository.vexora/repository.vexora-0.4.10.zip (root alias repository.vexora.zip)
Skin: zips/skin.vexora/skin.vexora-0.4.10.zip
Full build: vexora-build-0.4.10.zip
Full-build SHA256: 9b7cfbf205e9017220bc1408a9f04fe0941f58aa9c037cfd07509625fbe489d9

Previous stable versioned packages are retained unchanged for recovery. Do not install old versions over newer working packages.

## Repository exclusions

- repository.Fido: No verified compatible publisher package found
- repository.Palantir: No verified compatible publisher package found
- repository.a4kstreaming: No verified compatible publisher package found
- repository.djaythemes: No verified compatible publisher package found
- repository.funstersplace: No verified compatible publisher package found
- repository.gearheads2: No verified compatible publisher package found
- repository.grindhousekodi: No verified compatible publisher package found
- repository.stremioforkodi: No verified compatible publisher package found
- repository.twistednutz: No verified compatible publisher package found
- repository.wod: No verified compatible publisher package found
- repository.zeus768: No verified compatible publisher package found

Repository preservation audit: [REPOSITORY-PRESERVATION-0.4.10.json](REPOSITORY-PRESERVATION-0.4.10.json). All62repositoryZIPs and the74-record catalogue are byte-identical to the owner-tested build. Original publisher IDs,versions,artwork and update directory metadata are preserved.
