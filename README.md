[README(1).md](https://github.com/user-attachments/files/35001418/README.1.md)
<p align="center">
  <img src="assets/minto-cover.png" alt="Minto — Big ideas. Small daily wins. A mint-and-charcoal illustration of flashcards and connected ideas." width="100%">
</p>

<div align="center">

# A little more curious.

**A calm, local-first alternative to subscription-heavy study apps.**  
Flashcards, custom concept maps, and a little room to focus.  
No account. No paywall. No cloud required.

<kbd>LOCAL-FIRST</kbd> &nbsp; <kbd>OFFLINE-READY</kbd> &nbsp; <kbd>DARK + LIGHT</kbd> &nbsp; <kbd>NO RUNTIME DEPENDENCIES</kbd>

[Get started](#get-started) &nbsp; · &nbsp; [Explore the features](#made-for-your-kind-of-learning) &nbsp; · &nbsp; [Build a concept map](#give-the-whole-unit-a-home) &nbsp; · &nbsp; [User guide](docs/USER_GUIDE.md)

</div>

---

## Your study space. Actually yours.

Minto keeps the useful parts of a study app and leaves out the pressure. Breeze through a deck, work on the cards that need another look, or connect an entire unit in your own words.

Your library lives in your browser. The app makes no external requests, needs no login, and works from a single downloaded HTML file.

> **Built around learning. Not limits.**  
> Start with one card. Make one connection. Come back at your own pace.

## Made for your kind of learning

| When you want to… | Minto has you covered |
| :--- | :--- |
| **Just flip through** | **Browse** — move with **← / →**, flip with **Space**, shuffle, or replay. No ratings. No changes to your review schedule. |
| **Make it stick** | **Memorize** — reveal, then rate **1 Again**, **2 A little**, **3 Pretty well**, or **4 Easily**. Ratings save immediately; Again brings the card back. |
| **Check what you know** | **Practice quizzes** — up to **10 questions**, with up to **4 answer options** each. Requires **2 distinct prompt/answer pairs**. |
| **Find the connection** | **Match Pairs** — rounds of up to **6 pairs**. Requires **2 distinct prompt/answer pairs**. |
| **See the big picture** | **Custom concept units** — create up to **50 units**, each with up to **20 independent charts**. Build the nodes and connections yourself. |
| **Settle into a session** | **Focus room** — **5, 15, 25, 45, or 60 minutes**, with optional locally generated brown noise or rain-like noise and volume control. |
| **Keep your space organized** | **Collections** — create up to **100 collections**. Rename them, choose their sets, and organize without an extra dropdown in the set editor. |
| **Notice the little wins** | **Local progress** — **7-day activity**, quiz accuracy, and a gentle daily goal of **5–200 cards**. |
| **Take your work with you** | **Import / export** — JSON backups, CSV/TSV files, and pasted two-column cards. File imports support up to **5 MB**. |

**A few thoughtful details:** minty dark and light themes, keyboard-friendly controls, reduced-motion handling, and responsive layouts. Every set-based study mode returns you to the set you started from — including its completion screen.

The library starts with **3 editable sample sets and 34 cards**. Custom concept units start empty: no charts are generated from your flashcards.

## Get started

### The easy way

1. Download this repository using **Code → Download ZIP** and extract it.
2. Open [`Minto.html`](Minto.html) in a current desktop browser.
3. Pick a sample set, or create your own.

**No install. No build step. No internet connection needed after downloading.**

### The steady-address way

For a consistent browser storage location, use the included local launcher. It requires **Python 3**, with no additional packages.

```bash
python start.py
```

On macOS or Linux, use `python3 start.py` if needed.

The launcher opens **http://127.0.0.1:8765/Minto.html**. Keep its terminal open while using the local server; press **Ctrl+C** to stop it.

<details>
<summary><strong>Port already in use?</strong></summary>

```bash
python start.py --port 8766
```

You can also pass `--no-browser` to start without opening a browser window.

A different port is a different browser storage location. **Export a backup before switching addresses.**

</details>

## Give the whole unit a home

Concept maps are their own thing — not an automatic diagram of a flashcard set.

```text
Cell Structure                         concept unit
├── Animal Cells                       your first chart
│   ├── Nodes with your own notes
│   └── Connections you name
└── Plant Cells                        another independent chart
    ├── Its own layout and ideas
    └── Its own relationships
```

1. Open **Concept maps → Create a concept unit**.
2. Add a chart such as **Animal Cells**. It starts with one editable title node.
3. Add your own nodes and notes. Use **Connect nodes** to choose both ends and optionally label the relationship.
4. Add **Plant Cells** as a separate chart, then switch between them using the chart tabs.

Drag nodes into place, select one to read its notes, or edit a connection from the inspector. Everything stays separate from your flashcards and is included in your library backup.

<details>
<summary><strong>Canvas controls and chart limits</strong></summary>

- **Move a focused node:** arrow keys move **10 pixels**; **Shift + arrow keys** move **40 pixels**. On-screen movement buttons are available too.
- **Zoom:** **40%–140%** in **10-percentage-point** steps; reset returns to **100%**.
- **Canvas:** **2400 × 1600 pixels**, with contained scrolling.
- **Arrange:** a confirmed grid rearrangement that keeps every node and connection.
- **Each chart:** up to **100 nodes** and **200 connections**.
- **Entire library:** up to **5,000 concept nodes** and **10,000 connections**.
- **Text:** unit/chart names **100 characters**; descriptions **300**; node titles **80**; node notes **4,000**; connection labels **80**.

Deleting a node removes its attached connections. Deleting a chart leaves its sibling charts intact. Deleting a unit never deletes flashcard sets.

Connections are authored by you — they are not inferred by an AI service.

</details>

## Keep the flow

| Shortcut | Action |
| :--- | :--- |
| **← / →** | Previous / next card in Browse |
| **Space** | Flip the active flashcard |
| **1–4** | Rate a revealed card in Memorize, or select a quiz answer |
| **/** or **Ctrl / ⌘ + K** | Search the library |
| **Tab / Shift + Tab** | Move between controls |
| **Esc** | Close a dialog; unsaved edits ask for confirmation |
| **Arrow keys** on a chart node | Move **10 pixels** |
| **Shift + arrow keys** on a chart node | Move **40 pixels** |

Switching from Memorize to Browse and back keeps your place in the current memorization session. Browsing never changes your ratings. In-progress sessions do not survive a page reload.

<details>
<summary><strong>How the review schedule works</strong></summary>

Minto uses a transparent local heuristic — not FSRS, and not a claim of optimal learning intervals.

| Recall rating | Next interval |
| :--- | :--- |
| **1 · Again** | **1 minute**; also requeued in the current session. Successful-recall count resets. |
| **2 · A little** | At least **6 hours**, or the previous interval × **1.2**. |
| **3 · Pretty well** | At least **1 day**, or the previous interval × **2.5**. |
| **4 · Easily** | At least **3 days**, or the previous interval × **3.5**. |

Intervals are capped at **365 days**. The dashboard review button selects currently due cards. Memorize can practice an entire set and update its schedule; Browse cannot. Editing an existing card preserves its schedule, and quizzes do not silently change it.

Flashcard ratings count immediately. Quiz and matching results count when the round is finished.

</details>

## Your data stays with you

> [!IMPORTANT]
> **Local does not mean automatically backed up.** Your library is stored in this browser using `localStorage` — not written into the downloaded HTML file. Use **Export your library** regularly.

- No account, analytics, cloud sync, remote fonts, CDN, or AI service.
- Browser data clearing, private browsing, switching browsers, or moving/renaming the file can affect access to saved data.
- The local launcher provides a stable address; keep **one active Minto tab per storage location** to avoid competing edits.
- A JSON backup includes cards, collections, concept units, charts, schedules, preferences, and history.
- Import can add independent copies or explicitly replace the whole library. Both **version 1 and version 2** backups are accepted; exports use **version 2**.
- Real saving failures show a warning. Dismissing the warning does **not** mean unsaved work is safe.

**Updating Minto?** Export first, close the old tab, and replace the app. Existing version-1 libraries migrate automatically. Do not reopen an older app against an upgraded library. If a new file location appears empty, import your backup rather than clearing browser data.

<details>
<summary><strong>Import format and storage limits</strong></summary>

Use **two non-empty columns**: prompt and answer. A header is optional. Choose **Tab**, **Comma**, or **Semicolon**; quoted fields and multiline answers are supported.

```csv
Term,Definition
Hola,Hello
Gracias,Thank you
```

| Item | Limit |
| :--- | :--- |
| Flashcard sets | **200** per library |
| Cards | **5,000** per set; **10,000** per library |
| Collections | **100** |
| Import file | **5 MB** |
| Set title / description | **100 / 300 characters** |
| Collection name | **40 characters** |
| Card prompt / answer | **2,000 / 4,000 characters** |

Browser storage quotas may be reached before these application limits. Export remains available when a local save fails.

A single-set export excludes unrelated concept units. A concept-unit export contains that unit and its charts, not your flashcard library.

</details>

## Small codebase. Room to make it yours.

Plain HTML, CSS, and JavaScript. Browser-local storage. Web Audio for ambient sound. Python is optional and only used for the local launcher and rebuilding the single-file app.

```text
.
├── README.md
├── Minto.html                 # Complete, self-contained website
├── start.py                   # Optional local launcher
├── assets/
│   └── minto-cover.png        # Original README cover illustration
├── docs/
│   ├── USER_GUIDE.md          # Detailed behavior, limits, and update notes
│   └── PUBLISHING.md          # Repository setup checklist
└── source/
    ├── index.html
    ├── styles.css
    ├── app.js
    └── build.py               # Regenerates Minto.html
```

Edit the files in `source/`, then rebuild:

```bash
python source/build.py
```

This regenerates `Minto.html`; no package install is required. You can also serve `source/index.html` directly with a local HTTP server.

## Project notes

**Desktop-first, with responsive layouts.** Mobile styling is included as a baseline. Minto is offline-capable as a downloaded file, but is not a service-worker-installed PWA.

**170 automated checks passed during development:** **88 core regressions**, **56 concept-map/collection checks**, and **26 study-navigation checks**. These covered local data handling and interactions using a mocked browser environment; they are not a browser-compatibility certification or a live CI badge.

A full visual-browser, assistive-technology, and audible-playback pass was not available in the development environment. The optional local server could not be HTTP-smoke-tested there because listening ports were restricted. Its source and rebuild command were validated.

Focus audio is generated locally, not streamed. The timer and sound can continue after closing the focus dialog; reopen the headphones button to stop them. Keep the tab open. Completed focus sessions are recorded, but active timer state is not restored after reload.

**Ideas or bugs?** Open an issue with what happened, what you expected, and the steps to reproduce it. Include your browser and operating system, and use a small example set rather than a private library backup.

**Licensing:** this repository bundle does not include a license file yet. The repository owner should choose and add one before publishing reuse or contribution terms. See the [publishing checklist](docs/PUBLISHING.md).

---

<div align="center">

**A little less cramming. A little more connecting.**

<sub>Minto · Built around learning. Not limits.</sub>

</div>
