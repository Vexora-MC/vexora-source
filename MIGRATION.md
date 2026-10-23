## Existing 0.4.7 users

A same-version package will not generate a newer-version notification. Existing service code continues checking its original source until the migrated Wizard is installed. Do not delete the Kodi profile, backups or provider data.

1. Back up Kodi settings using the existing recovery procedure. Add https://vexora-mc.github.io/vexora-source/ in Kodi File Manager under a distinct name such as Vexora-MC.
2. Use Add-ons / Install from zip file / Vexora-MC / repository.vexora.zip. Approve Kodi's normal prompts and wait for repository installation.
3. Explicitly reinstall the migrated Wizard through Install from zip file / Vexora-MC / zips / plugin.program.vexora / plugin.program.vexora-0.4.7.zip. Do not rely on Update or InstallAddon(existing ID) to replace equal-version bytes.
4. Restart Kodi normally. The existing skin is byte-identical and does not need reinstalling. Existing setup and personal settings remain. Do not rerun complete build setup merely to switch addresses.
5. Confirm repository.vexora/addon.xml points to vexora-mc.github.io and installed Wizard resources/lib/startup_tasks.py SOURCE uses that same host. Both still display 0.4.7, so version labels alone cannot identify migration. If ZIP reinstall fails, stop and retain the old working installation; do not delete data to force it.

Kodi Omega's native InstallFromZip reads the selected ZIP and calls DoInstall without a newer-version gate: https://github.com/xbmc/xbmc/blob/Omega/xbmc/addons/AddonInstaller.cpp . This is an explicit native reinstall, not an invented forced updater. Native desktop test passed in a disposable Windows Kodi 21 profile: repository ZIP reinstall succeeded, then the original 0.4.7 Wizard was replaced by the migrated 0.4.7 ZIP through this exact native Install from zip file flow. Every installed package file matched the selected ZIP; the addon_data preservation marker remained intact. The test exited normally. Packages were selected from a local copy; the matching hosted downloads were independently verified over HTTPS. Physical Xbox acceptance remains pending; this desktop test does not establish console runtime success.

