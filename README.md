# HTML Text Writer 📝

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg?style=for-the-badge)](LICENSE)

A powerful, lightweight, zero-dependency browser-based HTML text editor modeled after the classic Microsoft Word interface. Built with vanilla HTML5, CSS3, and JavaScript, **HTML Text Writer** delivers a full-featured word processing experience directly inside any web browser without needing server dependencies or installations.

---

## ✨ Features

### 🎨 Office Ribbon Interface
- **Multi-Tab Navigation:** Includes Home, File, Review, Insert, Design, Layout, References, Mailings, and View tabs.
- **Font Controls:** Dynamic font family selection (*Calibri, Arial, Georgia, Times New Roman, Comic Sans, Algerian, etc.*) and font sizing (8pt to 72pt).
- **Text Styling:** Toggle Bold, Italic, and Underline formatting instantly.
- **Color Pickers:** Full theme color palettes for Font Color and Text Highlight Color with custom color support.
- **Paragraph Formatting:** Unordered/Ordered lists, Text Alignments (Left, Center, Right, Justify), and custom Line & Paragraph spacing.

### 📁 Backstage File Menu
- **Info:** View document metadata and word count.
- **New & Open:** Create new blank documents or upload existing HTML/TXT files.
- **Save & Save As:** Download document files locally directly from your browser.
- **Print Preview:** Built-in live document print preview and direct browser printing capabilities.

### 📖 Proofing & Thesaurus
- **Built-in Thesaurus:** Select any word in the document to lookup synonyms via the Review tab or context menu.
- **Simulated Grammar & Spell Check:** Visual indicators for proofing and document scanning.

### ⚡ Context Controls & Micro-Interactions
- **Context Menu:** Right-click anywhere in the editor page for quick editing actions.
- **Mini Toolbar:** Floating formatting toolbar triggered on text selection for quick styling without moving to the top ribbon.
- **Live Status Bar:** Real-time metrics tracking total word count, character count, and page details.

---

## 🎹 Keyboard Shortcuts

| Shortcut | Action |
| :--- | :--- |
| `Ctrl + B` | Toggle Bold |
| `Ctrl + I` | Toggle Italic |
| `Ctrl + U` | Toggle Underline |
| `Ctrl + Z` | Undo |
| `Ctrl + Y` | Redo |
| `Ctrl + S` | Quick Save Document |
| `Ctrl + Shift + S` | Save As Dialog |
| `Ctrl + N` | New Blank Document |
| `Ctrl + O` | Open Local Document |
| `Ctrl + P` | Open Print Dialog |

---

## 🚀 Getting Started

Since **HTML Text Writer** is built entirely with native web technologies, no build process or package installation (`npm` / `yarn`) is required.

### Quick Start
1. Clone the repository:
   ```bash
   git clone https://github.com/gagan2105/html_text_writer.git
   ```
2. Open `index.html` in any web browser:
   - Double-click `index.html`, or
   - Serve using any static HTTP server (e.g., VS Code Live Server, `npx serve`, or `python -m http.server`).

---

## 📁 Repository Structure

```
html_text_writer/
├── index.html        # Main web application entry point & embedded styles/scripts
├── README.md         # Documentation
└── LICENSE           # GNU General Public License v3.0
```

---

## 🌐 Browser Compatibility

Tested and compatible with all modern browsers:
- Google Chrome / Chromium 90+
- Mozilla Firefox 88+
- Microsoft Edge 90+
- Apple Safari 14+

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check out the [Issues page](https://github.com/Pragament/html_text_writer/issues).

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git checkout -b feature/AmazingFeature` & `git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📜 License

Distributed under the GNU General Public License v3.0. See `LICENSE` for more information.