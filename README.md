# Chief Command Center releases

Signed releases of [Chief Command Center](https://github.com/TheWikiWatch/chief-command-center), a Windows app that
gives you a chief of staff (no source here; the code is in that repository). Windows 10 (version 2004 or later) or
Windows 11, 64-bit.

## Install

1. Open the [latest release](https://github.com/TheWikiWatch/chief-command-center-releases/releases/latest) and
   download **`Chief-Command-Center-setup-<version>.zip`** (the `.msix` next to it is what the app's updater uses).
   Unzip it; don't run it from inside the zip.
2. Double-click **`Install Chief.cmd`**. It checks the package's signature, then asks for the first 8 characters of
   the publisher certificate's fingerprint. Compare with the fingerprint you were sent, or with this one:

   `AE12F08579ADD8AFB6C8593B7C97A76EA5A2070C`

   If they don't match, stop: the folder isn't the published one.
3. If the PC has more than one drive with room, it asks which drive to install on (only the program goes there,
   about 3 GB; your chats, notes and settings stay in your user folder). Updates stay on that drive.
4. Windows asks for administrator permission once, to trust that certificate for app packages (the builds are
   signed with the project's own certificate, not yet a publicly trusted one). If SmartScreen says it protected
   your PC, click **More info**, then **Run anyway**.
5. Chief opens and walks you through connecting an AI model and your notes folder.

## Updates

The app checks this repository at launch and once a day, with no key needed, and shows an "Update available" card;
nothing installs until you click it. Each release carries `release.json`, signed with the project's release key
(`release.json.sig`), which names the package's SHA-256: the app verifies both before installing, so a file swapped
on this page can't be installed as an update. `*.cdx.json` is the release's bill of materials.
