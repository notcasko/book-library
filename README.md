# 📚 Local Archive & Book Review Dashboard

A beautiful, lightweight, self-contained **offline-first library application** designed to manage book series, read full-text volumes, and track chapter notes directly in your browser.

By utilizing modern browser APIs, this project eliminates the need for complex databases, servers, or command-line installations. Drop the single `index.html` file into your reading folder, and you instantly have a fully searchable, visually stunning digital library.

---

## ✨ What It Accomplishes

* 🌐 **100% Local Privacy:** No accounts, no data logging, and no servers. All processes run entirely inside your browser using raw native disk handles via the File System Access API.
* 📦 **Automated EPUB Separation Engine:** Dynamically unpacks and converts uncompressed `.epub` and `.txt` files into an organized structure.
* 🖼️ **On-Demand Memory Performance:** Decouples images from text! Instead of converting files to heavy embedded Base64 strings, it automatically writes images to isolated external directories (`[series]/images/`), loading them on-demand **only** when active to ensure near-zero UI latency.
* ✏️ **Integrated Markdown Sidecar Notes:** Create, edit, and modify structured notes or summaries (`notes.md`) alongside your full text volumes with a seamless in-dashboard Markdown editor.
* 🔍 **Deep Global & Local Search Engine:** Search across your *entire* personal archive instantly or filter deep inside a single specific volume. Matches instantly highlight and auto-scroll directly to the exact relevant line.
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

1. **Save the Code:** Save the `index.html` file to your computer.
2. **Launch:** Double-click `index.html` to open it natively in any modern browser (Chrome, Edge, Opera, or Brave recommended for API storage hooks).
3. **Connect Your Archive:** Click **📁 Connect Project Folder** in the top control bar and choose an empty directory (or your pre-existing workspace folder).
4. **Import & Read:** Hit **✚ Add Series**, drop your digital files in, name the title, and let the background compiler process your collection.
