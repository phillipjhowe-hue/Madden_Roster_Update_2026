# How to Import the 2026 Roster into Madden NFL 2005

This guide covers the PCSX2 emulator (Windows, macOS, Linux) and a real PlayStation 2.

You need:
- **Madden NFL 2005 (USA)** for PS2, as a disc or an ISO — **Collector's Edition (`SLUS-21025`)**. Have the standard edition (`SLUS-21000`)? Use the file in [`standard-edition/`](standard-edition/) — see the note below.
- One of the roster files from this repo. Pick the one that matches how you play:

| File | Use it with | Guide |
|---|---|---|
| `BASLUS-21025D2026.psu` | **mymc / mymc+**, uLaunchELF on a real PS2, or any tool that imports `.psu` saves | [Part 2A](#part-2a-import-with-mymc-psu-file) |
| `Madden05-2026-Roster.zip` | **PCSX2 folder** memory cards (copy the folder in) | [Parts 1–2](#part-1-download-and-extract) |
| `Madden05-2026-Roster-Memcard.zip` | A complete **8 MB memory card** (`.ps2`) with the roster already on it. Use it as a PCSX2 card, or write it to a real card | [Part 2B](#part-2b-use-the-ready-made-memory-card) |

> **Which edition do I have?** Check your disc or ISO name, or look at an existing Madden save on your card in mymc. Collector's Edition saves start with `BASLUS-21025`, standard edition saves with `BASLUS-21000`. The game only lists saves with its **own** ID, so a save for the wrong edition won't show up in the Load menu. The roster data is identical in both versions.
>
> **Standard edition (`SLUS-21000`):** use [`standard-edition/BASLUS-21000D2026.psu`](standard-edition/BASLUS-21000D2026.psu) in Part 2A instead.

> **mymc can't import `Madden05-2026-Roster.zip`.** That zip holds a PCSX2 *folder* save, and mymc only imports `.psu`/`.max` files. Use **`BASLUS-21025D2026.psu`** with mymc.

---

## Part 2A: Import with mymc (`.psu` file)

1. Download **`BASLUS-21025D2026.psu`** from this repo (**Download raw file**).
2. Open **mymc** (or mymc+) and use **File → Open** to open your memory card image (`.ps2`). For PCSX2 this is usually `Documents\PCSX2\memcards\Mcd001.ps2`.
   - The card must be a **file** card (`.ps2` file), not a folder card. mymc can't open folder cards.
   - Close PCSX2 first, so the card isn't in use.
3. Click **Import** (or **File → Import**) and select **`BASLUS-21025D2026.psu`**.
4. The save appears in the list as **"Madden NFL 2005 Roster 2026"** (about 286 KB).
5. Close mymc, start PCSX2 with that card in **Slot 1**, and go to [Part 3](#part-3-load-the-roster-in-madden-2005).

Command-line mymc/mymc+ equivalent:

```
mymc Mcd001.ps2 import BASLUS-21025D2026.psu
mymc Mcd001.ps2 dir
```

## Part 2B: Use the ready-made memory card

1. Download and extract **`Madden05-2026-Roster-Memcard.zip`** to get `Madden05-2026-Roster-Memcard.ps2`, an 8 MB card containing only the 2026 roster.
2. Copy it into `Documents\PCSX2\memcards\`.
3. In PCSX2 **Settings → Memory Cards**, put **Madden05-2026-Roster-Memcard.ps2** in **Slot 1**. If you want to keep your own saves, put it in **Slot 2** instead and load the roster from Slot 2.
4. Go to [Part 3](#part-3-load-the-roster-in-madden-2005).

---

## Part 1: Download and extract

1. Open `Madden05-2026-Roster.zip` in this repo and click **Download raw file** (the download icon at the top right).
2. Right-click the downloaded zip and choose **Extract All…**.
3. You should now have a folder named **`BASLUS-21025D2026`** containing four files:

   ```
   BASLUS-21025D2026/
   ├── BASLUS-21025D2026   (the roster data)
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

Copy the whole **`BASLUS-21025D2026`** folder into the memory card folder, so the path looks like this:

```
Documents\PCSX2\memcards\Mcd001.ps2\BASLUS-21025D2026\BASLUS-21025D2026
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

1. Copy **`BASLUS-21025D2026.psu`** to a USB stick.
2. On a PS2 with **FreeMcBoot**, open **uLaunchELF**, browse to `mass:/`, select the `.psu`, press **R1 → psuPaste** to `mc0:/` (Slot 1).
3. Load it in-game as in **Part 3**.

If your setup writes whole memory card images (e.g. MemCard PRO, SD2PSX), use `Madden05-2026-Roster-Memcard.ps2` instead.

---

## Troubleshooting

| Problem | Fix |
|---|---|
| **mymc doesn't recognize the file** | You're importing the zip or the folder. mymc needs **`BASLUS-21025D2026.psu`**. Also make sure mymc opened a **file** card (`.ps2`), not a folder card. |
| The roster doesn't appear in the Load menu | Make sure the folder sits **directly** inside the card folder (`Mcd001.ps2\BASLUS-21025D2026\…`), not nested one level deeper (`…\BASLUS-21025D2026\BASLUS-21025D2026\BASLUS-21025D2026`). Make sure the card is a **Folder** card in **Slot 1**. |
| The save shows as corrupted | Re-download and re-extract the zip. Don't edit or rename any file inside the folder. |
| Teams are still the old 2004 rosters | You loaded the game without loading the roster. Do **Part 3**, and for Franchise start a **new** franchise afterwards. |
| PCSX2 doesn't show my copied save | Close PCSX2 completely, copy the folder, then reopen it. Folder cards are read when the game boots. |
| **The save is on the card but doesn't show in the game** | It's for the other edition of the game. Collector's Edition (`SLUS-21025`) needs `BASLUS-21025D2026`; standard edition (`SLUS-21000`) needs `standard-edition/BASLUS-21000D2026.psu`. |
| I also have other Madden saves | Rosters, profiles and settings can share one card. Just pick **Roster 2026** when loading. |

---

See [CHANGELOG.md](CHANGELOG.md) for everything in this roster.
