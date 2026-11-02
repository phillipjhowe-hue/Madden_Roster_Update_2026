# How to Import the 2026 Roster into Madden NFL 2005

This guide covers the PCSX2 emulator (Windows, macOS, Linux) and a real PlayStation 2.

You need:
- **Madden NFL 2005 (USA)** for PS2, as a disc or an ISO (game ID `SLUS-21000`, the Collector's Edition works too)
- **`Madden05-2026-Roster.zip`** from this repo

---

## Part 1: Download and extract

1. Open `Madden05-2026-Roster.zip` in this repo and click **Download raw file** (the download icon at the top right).
2. Right-click the downloaded zip and choose **Extract All…**.
3. You should now have a folder named **`BASLUS-21000D2026`** containing four files:

   ```
   BASLUS-21000D2026/
   ├── BASLUS-21000D2026   (the roster data)
   ├── icon.sys
   ├── view.ico
   └── _pcsx2_index
   ```

   Don't rename the folder or the files inside it. The game finds the save by its name.

---

## Part 2: Copy the save into PCSX2

The roster is a memory card save in PCSX2's **Folder** memory card format. Which steps you follow depends on whether your memory card is already a folder card.

### Step 1: Check your memory card type

1. Open PCSX2 and go to **Settings → Memory Cards**.
2. Look at **Slot 1**:
   - If the card shows as a **Folder** card, skip to [Step 3](#step-3-open-the-memory-card-folder).
   - If it's a **File** card (a single `.ps2` file, e.g. `Mcd001.ps2`), do Step 2 first.

### Step 2: Convert or create a folder card

You only need **one** of these options.

**Option A: Convert your existing card (keeps your other saves)**
1. In **Settings → Memory Cards**, right-click your Slot 1 card and choose **Convert**.
2. Pick **Folder** as the type and give it a name (e.g. `Mcd001_folder`).
3. Put the new folder card in **Slot 1**.

**Option B: Create a new, empty folder card**
1. In **Settings → Memory Cards**, click **Create**.
2. Choose **Folder** as the type, name it (e.g. `Madden2026`), and click **Create**.
3. Put it in **Slot 1**.

> Menu names vary slightly between PCSX2 versions. In older 1.6.x builds this is under **Config → Memorycards**, and you need to tick **Enable folder memory cards**.

### Step 3: Open the memory card folder

1. In **Settings → Memory Cards**, click **Open Memory Card Directory** (in some versions it's **Browse**, or right-click the card → **Open in File Explorer**).
2. Windows usually opens: `Documents\PCSX2\memcards\`
3. Open your folder card. It's a **folder** whose name ends in `.ps2`, e.g. `Mcd001.ps2` or `Madden2026.ps2`.

### Step 4: Copy the roster in

Copy the whole **`BASLUS-21000D2026`** folder into the memory card folder, so the path looks like this:

```
Documents\PCSX2\memcards\Mcd001.ps2\BASLUS-21000D2026\BASLUS-21000D2026
```

PCSX2 must be closed, or the game must not be running, when you copy files in.

---

## Part 3: Load the roster in Madden 2005

1. Start PCSX2 and boot **Madden NFL 2005**.
2. Let the game finish loading your profile and settings from the memory card.
3. From the main menu, go to **My Madden → Load/Save → Load** (the menu may be named **Load Roster** or **Load File** depending on your version).
4. Select **Slot 1**, then pick **Roster 2026** (the save is shown as *Madden NFL 2005 Roster 2026*).
5. Confirm. You'll see current teams in **Play Now**, **Roster Management** and the depth charts.

### Using it in Franchise mode

Franchise mode copies the roster in memory when you **start** a franchise:

1. Load **Roster 2026** first (Part 3 above).
2. Then go to **Game Modes → Franchise → New Franchise**.

An existing franchise won't pick up the new roster. You have to start a new one after loading it.

### Optional: make it load automatically

If your Madden settings have **Auto Save** / **Auto Load** turned on, save the roster once over your default roster file (**My Madden → Load/Save → Save**) so it loads every time you boot the game.

---

## Part 4: Real PlayStation 2 (optional)

To use the roster on real hardware, you need to get the save onto a physical memory card. The easiest way is to go through PCSX2 first:

1. Follow **Parts 1–2** above to put the save on a PCSX2 **folder** card.
2. In PCSX2 **Settings → Memory Cards**, **Convert** that folder card to a **File** card (`.ps2`, 8 MB).
3. Open the `.ps2` file in a memory card manager such as **mymc** / **mymc+** and **export** the `BASLUS-21000D2026` save as a **`.psu`** file.
4. Copy the `.psu` to a USB stick, and on a PS2 with **FreeMcBoot** use **uLaunchELF** (`mc0:` / `mc1:`) to copy or import it onto your memory card.
5. Load it in-game as in **Part 3**.

---

## Troubleshooting

| Problem | Fix |
|---|---|
| The roster doesn't appear in the Load menu | Make sure the folder sits **directly** inside the card folder (`Mcd001.ps2\BASLUS-21000D2026\…`), not nested one level deeper (`…\BASLUS-21000D2026\BASLUS-21000D2026\BASLUS-21000D2026`). Make sure the card is a **Folder** card in **Slot 1**. |
| The save shows as corrupted | Re-download and re-extract the zip. Don't edit or rename any file inside the folder. |
| Teams are still the old 2004 rosters | You loaded the game without loading the roster. Do **Part 3**, and for Franchise start a **new** franchise afterwards. |
| PCSX2 doesn't show my copied save | Close PCSX2 completely, copy the folder, then reopen it. Folder cards are read when the game boots. |
| I also have the 2024 roster | Both can live on the same card: `BASLUS-21000D2024` and `BASLUS-21000D2026` are separate saves. Just pick **Roster 2026** when loading. |

---

See [CHANGELOG.md](CHANGELOG.md) for everything in this roster.
