<p align="center">
  <img src="docs/logo.svg" width="104" height="104" alt="Rastro logo: a shot tree, with the current shot in amber">
</p>

<h1 align="center">Rastro</h1>

<p align="center">
  <b>Every shot, version and to-do of a compositor, in one window.</b><br>
  A free Windows app for Nuke compositors. You do not need Nuke to run it.
</p>

<p align="center">
  <a href="https://github.com/neuralcheckpoint/rastro/releases"><img alt="Latest release" src="https://img.shields.io/github/v/release/neuralcheckpoint/rastro?include_prereleases&label=release&color=d6a64f"></a>
  <img alt="Windows 10 and 11, 64-bit" src="https://img.shields.io/badge/Windows-10%20%7C%2011%2C%2064--bit-3a3a3a">
  <img alt="Free for personal and commercial work" src="https://img.shields.io/badge/price-free%20forever-3a3a3a">
</p>

<p align="center">
  <a href="https://github.com/neuralcheckpoint/rastro/releases/download/v1.0.0-beta.3/rastro-1.0.0-beta.3-windows.zip"><b>Download Rastro 1.0.0-beta.3</b></a> (zip, about 14 MB)
  &nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="#install">Install</a>
  &nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="#first-run">First run</a>
</p>

![Contact sheet with production status on every shot and the selected version in the inspector](docs/contact-sheet.png)

Rastro keeps a compositor's shots in one window: every project, shot and version on disk, with
thumbnails, to-dos, production status, a production journal, side-by-side compare, review MP4s and
delivery checks. It is a standalone Windows app; you do not need Nuke to run it.

**Rastro is free, with every feature, for personal and commercial work.** No license, account or trial.

**[Download Rastro 1.0.0-beta.3](https://github.com/neuralcheckpoint/rastro/releases/download/v1.0.0-beta.3/rastro-1.0.0-beta.3-windows.zip)** (Windows 10/11, 64-bit, zip of about 14 MB).

**Install in 4 steps:**
1. Download the zip above.
2. Right-click it → **Extract All…** → choose a folder like `Documents\Rastro`.
3. Open the extracted folder and double-click `rastro.exe`.
4. If Windows says "Windows protected your PC", click **More info** → **Run anyway**.

No installer, no admin rights, no account. Details in [Install](#install) below.

## What it looks like

<table>
  <tr>
    <td width="50%" valign="top">
      <b>Every shot and version in one tree.</b> Rastro scans your project folders and lists shots,
      Nuke scripts and versions with production status, open to-dos and the last change.
      <br><br>
      <img src="docs/list-view.png" alt="List view: shots, scripts and versions with status and to-dos">
    </td>
    <td width="50%" valign="top">
      <b>Compare two versions.</b> Pick A and B in the Review tab and drag the wipe, or switch to
      flicker or blend. It plays the renders when there are any, the thumbnails when there are not.
      <br><br>
      <img src="docs/compare-wipe.gif" alt="Animation: dragging the wipe between v005 and v004 of a shot in the Review tab">
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <b>Every command in Ctrl+K.</b> Type a few letters and run it, with its shortcut beside it.
      <br><br>
      <img src="docs/command-palette.gif" alt="Animation: typing contact in the command palette and opening the Contact sheet">
    </td>
    <td width="50%" valign="top">
      <b>Delivery check before you send.</b> Open to-dos, review status, the final Write, frame
      range and render jobs in one list, with the action that fixes each one beside it.
      <br><br>
      <img src="docs/delivery-check.png" alt="Delivery check listing the issues that block delivery of a version">
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <b>To-dos per shot or per version.</b> Add notes from a client call to the shot, mark them
      done, in progress or blocked, and filter the whole project in the To-do Center.
      <br><br>
      <img src="docs/todo-center.png" alt="To-do Center with done, in progress and blocked to-dos">
    </td>
    <td width="50%" valign="top">
      <b>A production journal.</b> Write what changed today, paste frames, tag entries
      (<code>#review</code>, <code>#seq=040</code>) and link shots. It stays on your machine.
      <br><br>
      <img src="docs/production-journal.png" alt="Production Journal with dated entries, tags and pasted frames">
    </td>
  </tr>
</table>

### Examples

- **Morning check:** open the **Contact sheet**, filter by **Open To-dos**, and see which shots wait
  on you and which are waiting on review.
- **After a client note:** select the shot, type the note in **Add a to-do**, set the production
  status to **In progress**, and log it in the **Production Journal** with a frame pasted in.
- **Before sending a version:** select two versions (Ctrl+click) and press **C** to compare them,
  make a **Review MP4** (M), then run the **Delivery check**.
- **No Nuke at all:** add a folder of renders as a **Renders only** project and use Rastro to
  browse, compare and track your movies and image sequences.

## Requirements

- Windows 10 or 11, 64-bit.
- A GPU with DirectX 12 or Vulkan (any card from the last ~8 years, including integrated graphics).
- Optional: FFmpeg for review MP4s, contact sheets and movie thumbnails. If it isn't on your `PATH`,
  use **Profile · Download ffmpeg** (command palette): Rastro asks first, then downloads and checks it.
  Without it those commands say FFmpeg is missing; everything else works.
- Color: Compare previews and review MP4s follow the script's color management (OCIO/ACES included)
  without Nuke. A missing config can be fetched with **Profile · Download OCIO config**.
- Optional: Nuke, only to open scripts and for the tools that run it (render queue, render quality
  check, review renders). Point Rastro to it in **Profile · Nuke executable** (command palette,
  Ctrl+K): **Detect** finds installs in `C:\Program Files\Nuke*`, or type the path to
  `Nuke<version>.exe`, then pick your edition (Nuke, NukeX, Studio, Indie or Non-commercial).
  Without it, those commands tell you where to set it; everything else works.
- Nuke Indie is supported: scripts open with `--indie` (`.nkind` scripts always do). Background
  renders and render checks may not work in Nuke Indie; Rastro warns and runs them anyway.
- Optional: [mpv](https://mpv.io/installation/) on your `PATH`, only for **Play selected versions
  in mpv** (side by side, split or difference). Without it that command says mpv was not found;
  everything else works.

## Install

Rastro is a single folder with `rastro.exe`. There is no installer and it does not need
administrator rights.

1. **Download.** Open the [release page](https://github.com/neuralcheckpoint/rastro/releases/tag/v1.0.0-beta.3), scroll to **Assets** and click
   `rastro-1.0.0-beta.3-windows.zip`. Do not use the "Source code" links: they are not the app.
2. **Extract.** In your Downloads folder, right-click the zip → **Extract All…**, pick a folder you
   can write to (for example `C:\Users\<you>\Documents\Rastro`) and click **Extract**.
   Do not run Rastro from inside the zip, and avoid `C:\Program Files` (it is read-only).
3. **Open.** In the extracted `rastro-1.0.0-beta.3` folder, double-click `rastro.exe`.
4. **SmartScreen.** The exe is not signed yet, so the first time Windows may show
   "Windows protected your PC". Click **More info** → **Run anyway**. It is asked only once.
5. **Shortcut (optional).** Right-click `rastro.exe` → **Show more options** → **Send to** →
   **Desktop (create shortcut)**, or pin it to Start or the taskbar.
6. **FFmpeg (optional, recommended).** Press **Ctrl+K**, type `ffmpeg` and run
   **Profile · Download ffmpeg**. Rastro shows the source and size, asks for your OK, then downloads
   and checks it. Skip this if FFmpeg is already on your `PATH`.

**Check the download (optional).** In PowerShell, in the Downloads folder:

```powershell
Get-FileHash rastro-1.0.0-beta.3-windows.zip -Algorithm SHA256
```

The hash must match the one in `rastro-1.0.0-beta.3-windows.zip.sha256` on the release page.

## First run

1. Rastro opens with no projects. Click **Add project** (also the **+** button in the header).
2. Pick the project's root folder, give it a name, choose its type and tick the subfolders that hold
   shots (for example `shots`, `comp`, `renders`). **Renders only** projects need no Nuke: Rastro lists
   your movies (.mov, .mp4, .mxf) and image sequences (.exr, .dpx, .tif, .png, .jpg) as versions.
3. Rastro scans the folders and lists every shot and version it finds. Use **Scan folders** after
   adding new shots on disk; it also refreshes by itself while the app is open.

Press **Ctrl+K** for the command palette: every command is there with its shortcut.
**Ctrl+click** a second version in the tree to select two, for **Compare selected versions** and
**Play selected versions in mpv**.
**Help · Reduce motion** also stops the Board preview that follows the mouse over a video or sequence.
Press **C** in the tree's List view to compare the selected versions. In **Delivery check**, actions
that open another tool (Review, Dependencies, Enqueue render…) bring the check back when that tool
closes, and Enqueue render selects the version first.

## Where your data lives

| What | Where |
|---|---|
| Projects, to-dos, status, journal, reviews | `%LOCALAPPDATA%\RafaTools\NukeProjectManager\` |
| Window and view preferences | `%APPDATA%\rastro-rs\` |

Your shot folders are only read. Rastro writes to them only when you ask it to (Duplicate as next
version, Collect, Publish, review MP4s). **Profile · Back up** (in the command palette) saves your Rastro data to a single zip.

## Update

Close Rastro, unzip the new version over the old folder (or to a new folder) and open it. Your
data stays where it is, so nothing has to be moved.

## Uninstall

Delete the Rastro folder. To also remove your Rastro data, delete the two folders in
*Where your data lives*.

## Troubleshooting

- **The window does not open, or it opens black.** Update your graphics driver. On a remote desktop
  or a VM without GPU acceleration Rastro may not start.
- **A project shows no shots.** Open **Scan folders** and check that the subfolders with shots are
  ticked.
- **Review MP4 or thumbnails fail.** Run **Profile · Download ffmpeg**, or install FFmpeg and make
  sure `ffmpeg -version` works in a new terminal.

## Files in this folder

- `rastro.exe`: the app (one file, no installer).
- `EULA.md`: the license agreement for Rastro.
- `python/`: two small helper scripts Rastro runs inside Nuke (thumbnails and script limits).
- `LICENSES/`: licenses of the third-party software inside `rastro.exe` (also under
  **About Rastro**).
- `SHA256SUMS.txt`: the SHA-256 of every file in this folder.

## Credits

Screenshots and animations use frames from *Tears of Steel*, © Blender Foundation | mango.blender.org, licensed
[CC BY 3.0](https://creativecommons.org/licenses/by/3.0/).
