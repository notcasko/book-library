# 📚 Local Archive & Book Review Dashboard

A beautiful, lightweight, self-contained **offline-first library application** designed to manage book series, read full-text volumes, and track chapter notes directly in your browser.

By utilizing modern browser APIs, this project eliminates the need for complex databases, servers, or command-line installations. Drop the single `index.html` file into your reading folder, and you instantly have a fully searchable, visually stunning digital library.

---

## ✨ What It Accomplishes

* **Bypasses Server Overhead:** Brings the power of a full desktop reading application to a single static HTML file that runs completely locally.
* **Dynamic Local File Syncing:** Automatically counts files, detects covers, and reads full text on-the-fly. If you add, remove, or rename a volume in your folder, clicking "Rescan" updates the UI instantly without reloading the page.
* **Per-Volume Smart Document Splitting:** Lets you write all your reviews, character arcs, and key chapter actions for an *entire series* inside a single `notes.md` file. The app uses a custom parsing engine to extract and display only the notes relevant to the specific volume you are reading.
* **Intelligent Cross-Series Search Engine:** Digs through every line of every text volume and markdown file simultaneously. Clicking a global search result auto-switches the viewport tab (Notes vs. Full Text), highlights your search query, and smoothly scrolls directly to the target line.
* **Persistent One-Click Reconnect:** Navigates browser security restrictions seamlessly. It remembers your folder structure using securely isolated IndexedDB tokens so you only have to pick your directory once. When you return, a single click anywhere on the page unlocks your entire archive.

---

## 📂 Directory Architecture

For the dynamic scanning system to work perfectly, keep your files organized in your project folder using this clean structure:

```text
📂 Your-Book-Archive/
│── 📄 index.html             <- The dashboard file
│── 📄 db.json                <- Optional: Clean display titles configuration
└── 📂 books/
    ├── 📂 Book Series 1/
    │   ├── 🖼️ cover.jpg       <- Can be .jpg, .png, or .webp
    │   ├── 📄 notes.md        <- The master Markdown notes for this series
    │   ├── 📄 Volume 01.txt   <- Full-text files (sorted alphabetically)
    │   └── 📄 Volume 02.txt   
    └── 📂 Book Series 2/
        ├── 🖼️ cover.png
        ├── 📄 notes.md
        ├── 📄 01 - Initiation.txt
        └── 📄 02 - Grid Crash.txt

```

### ⚙️ Setting Up `db.json` (Optional)

If your physical folders have short or messy names, you can map them to beautifully formatted titles on your screen by placing a `db.json` file in the root folder:

```json
{
  "seriesSettings": {
    "The Orion Chronicles": "The Orion Chronicles (Sci-Fi Epic)",
    "Neon Overdrive": "Neon Overdrive (Cyberpunk Saga)"
  }
}

```

---

## 🛠️ Feature Walkthrough

### 1. The 4-Wide Gallery Grid

The top of the screen displays an elegant responsive grid featuring the primary cover of each series alongside a live volume counter. Clicking a series card focuses the lower workspace on that narrative arc.

### 2. The Multi-Tier Viewport Window

Toggle effortlessly between two reading experiences:

* **📖 Notes & Reviews:** Shows your beautifully rendered Markdown documentation (bulleted key actions, character outlines, or thoughts).
* **📄 Read Full Text:** Loads the complete, raw text of the `.txt` volume in a clean, high-readability monospace typesetting environment.

### 3. Dual-Scope Search System

* **Global Search Bar (Top Right):** Searches everything everywhere. It shows live text snippets in a dropdown overlay so you can preview context before hopping to a book.
* **Local Search Bar (Sidebar):** Constrained to the series you are currently looking at. It instantly filters your volume list and highlights matching lines in real-time as you type.

---

## 🚀 Getting Started

1. Save the dashboard code as `index.html` inside your main folder.
2. Open `index.html` in any modern web browser (Chrome, Edge, Opera, or Brave).
3. Click the **📁 Connect Project Folder** button at the top left.
4. Select your main directory and grant the browser permission to read the files.
5. Bookmark the page. The next time you open it, just click anywhere on the screen to instantly resume reading.
