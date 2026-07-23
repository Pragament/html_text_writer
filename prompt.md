# Prompt: MS Word Clone for Class 3 Digital Literacy (Domain 1)

## Purpose

Build a **fully functional, browser-based clone of Microsoft Word 2021/365**, intended for **Class 3 students (age ~8)** who are following a printed textbook (Domain 1: Digital Literacy → Chapter 1: "Word Power Made Simple – Working with MS Word"). Students will follow textbook instructions **step-by-step, screenshot-by-screenshot**, so the UI must closely mirror real MS Word — same button names, same icons, same menu structure, same dialog boxes, same right-click behaviors.

**Every feature listed below must be 100% functional.** This is not a visual mockup — buttons, dropdowns, dialogs, and menus must actually perform their described action on real document content.

No teaching aids, tooltips, or hint overlays should be added — the textbook is the student's guide. The tool's job is only to work correctly and look like Word.

---

## Tech Stack

- Plain **HTML, CSS, JavaScript** (no frameworks, no build step, runs in any browser).
- No login, no backend server, no cloud storage.
- Files are saved and opened **locally on the user's device** (Blob + `<a download>` for saving, `<input type="file">` for opening).
- Code should be clean, modular, and well-commented — organized into clear HTML / CSS / JS sections.

---

## Overall Interface Structure

```
┌─────────────────────────────────────────────────────┐
│ TITLE BAR — shows document name                     │
├─────────────────────────────────────────────────────┤
│ RIBBON TABS: File | Home | Insert | Design | Layout  │
│  | References | Mailings | Review | View             │
├─────────────────────────────────────────────────────┤
│ RIBBON (Home tab active by default)                   │
│  ┌── Font Group ──────┐ ┌── Paragraph Group ────────┐ │
│  │ Font name dropdown │ │ Bullets | Numbering       │ │
│  │ Font size dropdown │ │ Align L | C | R | Justify │ │
│  │ B  I  U             │ │ Line & Paragraph Spacing  │ │
│  │ Font Color (A ▾)    │ └───────────────────────────┘ │
│  │ Highlight Color     │                               │
│  └─────────────────────┘                               │
├─────────────────────────────────────────────────────┤
│                                                       │
│              DOCUMENT AREA (white page,               │
│              contenteditable, spellcheck on)          │
│                                                       │
├─────────────────────────────────────────────────────┤
│ STATUS BAR — "Page 1 of 1" | Word Count               │
└─────────────────────────────────────────────────────┘
```

Only **File** and **Home** tabs need full functionality. Other tabs (Insert, Design, Layout, References, Mailings, View) should visually switch the ribbon strip but can be non-functional placeholders. **Review** tab needs the Thesaurus feature (see section 9).

---

## Feature Specifications

### 1. Creating a Document

Matches textbook steps: right-click empty space → New → Microsoft Word Document → name it → Enter.

- Provide a small simulated "desktop" area (or a "New Document" entry point) where:
  1. Right-clicking opens a context menu with a **"New"** option.
  2. Hovering/clicking "New" reveals **"Microsoft Word Document"** as a choice.
  3. Clicking it creates a new file icon/tile.
  4. The new file's name is **editable inline** — student types a name and presses **Enter**.
  5. Pressing Enter actually opens a blank document, and the typed name appears in the **Title Bar**.
- Also provide a straightforward **File → New** entry that does the same (opens a fresh blank document, prompts for a name).

### 2. Text Alignment

- Four buttons in the Paragraph group, in this exact order: **Align Text Left, Center, Align Text Right, Justify**.
- Selecting text (or placing the cursor in a paragraph) and clicking an alignment button must **immediately change** the real alignment of that text.
- **Undo (Ctrl+Z)** and **Redo (Ctrl+Y)** must work on both typing actions and formatting actions (not just visually — actual state must reverse/reapply).

### 3. Font (Text Shape)

- **Font Name dropdown** with a down-arrow, showing a scrollable list including at minimum:
  `Calibri, Arial, Arial Black, Arial Narrow, Times New Roman, Comic Sans, Georgia, Algerian, Agency FB`
- Selecting a font instantly applies it to selected text.
- **Right-clicking selected text** shows a floating mini-toolbar (matching Word's real behavior) with the same Font Name control, functioning identically to the ribbon version.

### 4. Text Size

- **Font Size dropdown** next to the font name box, listing standard sizes (8 through 72, in the usual Word increments).
- Selecting a size instantly resizes selected text.
- Also visible/functional in the right-click mini-toolbar.

### 5. Text Color

- **Font Color icon** ("A" with a colored bar underneath) with a small dropdown arrow beside it.
- Clicking the dropdown arrow opens a color palette: Theme Colors row, Standard Colors row (Red, Orange, Yellow, Green, Blue, Purple, etc.), "More Colors..." (a working color picker input), and optionally "Gradient."
- Selecting a color instantly applies it to selected text's font color.

### 6. Text Style

- **Bold (B)**, **Italic (I)**, **Underline (U)** buttons in the Font group.
- Clicking toggles the real style on selected text.
- Buttons should visually indicate active/pressed state when the cursor is inside styled text.

### 7. Spelling and Grammar Corrections

- Real spellcheck: use `contenteditable="true" spellcheck="true"` so the browser underlines misspelled words in **red wavy underline** automatically.
- **Right-clicking a red-underlined word** must show a real context menu with:
  - 1–3 suggested correct spellings (from the browser's native spellcheck suggestions where possible, or a small fallback dictionary).
  - An **"Ignore"** option.
  - Clicking a suggestion **replaces the word** in the document text.
  - Clicking "Ignore" **removes the underline** for that instance permanently.
- Simulate basic grammar-checking with a **blue wavy underline** for a small set of hardcoded common error patterns (e.g., repeated words like "the the", or a few sample phrases), with the same right-click → suggestion → fix / ignore behavior.

### 8. Paragraph and Line Spacing

- **Line and Paragraph Spacing** icon (with the up/down arrow icon) in the Paragraph group, with a dropdown listing: `1.0, 1.15, 1.5, 2.0, 2.5, 3.0`, plus **"Add Space Before Paragraph"** and **"Add Space After Paragraph"** toggle options.
- Selecting a spacing value instantly changes the line spacing of the selected paragraph(s).
- **Right-click → "Paragraph..."** must open a real dialog box:
  - Title: "Paragraph"
  - "Indents and Spacing" section with **Before** and **After** spacing number fields (in pt), each with working up/down increment arrows.
  - **OK** button that applies the entered spacing to the selected paragraph and closes the dialog.
  - **Cancel** button that closes without applying changes.

### 9. Thesaurus (Synonyms)

- Selecting a word and **right-clicking** shows a **"Synonyms"** entry in the context menu, which expands to show a short list of alternatives.
- Also accessible via a simplified **Review tab → Thesaurus** button, which opens a side panel showing synonyms for the selected word.
- Build a small built-in synonym dictionary covering at least 15–20 common words (e.g., remember → recall, retain, memorize, recollect, reminisce, evoke; happy → glad, joyful, cheerful; big → large, huge, giant; etc.).
- Clicking a synonym from the list **actually replaces** the selected word in the document.

### 10. Saving the Document

- **File menu** (styled like Word's dark File screen) with sidebar entries: `Info, New, Open, Save, Save As, Print, Share`.
- **Save As**:
  - Opens a dialog with an editable **File Name** field (pre-filled with current document name) and a **Save** button.
  - Clicking Save **downloads the actual document content** (with formatting preserved as HTML, or plain text if using .txt) to the user's local device via Blob + `<a download>`, using the entered file name.
- **Save** (after the first Save As):
  - Instantly re-downloads using the same file name, no dialog shown.
- **Open**:
  - Opens a native file picker (`<input type="file">`).
  - Selecting a previously saved file **actually loads its real content** back into the document area, preserving formatting where the file format allows (best with .html saves).

### 11. Printing the Document

- **File → Print**:
  - Shows a real **print preview** of the current document content on the right side of the screen (matching the textbook's layout), reflecting actual current formatting.
  - A **Print** button that triggers `window.print()`, printing the actual document content and formatting.

---

## Non-Negotiable Functional Checklist

- [ ] New Document creation (via right-click simulation AND File → New) works and names the doc.
- [ ] All 4 alignment buttons work on selected text.
- [ ] Undo / Redo work on real typing and formatting history.
- [ ] Font Name dropdown changes real font of selected text (9 fonts minimum).
- [ ] Right-click mini-toolbar mirrors font controls and works identically.
- [ ] Font Size dropdown changes real size of selected text.
- [ ] Font Color dropdown + palette changes real color of selected text.
- [ ] Bold / Italic / Underline toggle real styles with active-state indication.
- [ ] Native spellcheck underlines misspelled words in red; right-click → suggestions + Ignore work and actually edit the text.
- [ ] Simulated grammar check underlines sample errors in blue with working right-click fix/ignore.
- [ ] Line & Paragraph Spacing dropdown applies real spacing values.
- [ ] Right-click → Paragraph dialog opens, Before/After fields work, OK applies real spacing.
- [ ] Right-click → Synonyms and Review → Thesaurus both show real synonym lists and replace words on click.
- [ ] File menu (Info, New, Open, Save, Save As, Print, Share) is present; New, Open, Save, Save As, Print are fully functional.
- [ ] Save As dialog downloads a real file to local device with the entered name.
- [ ] Save re-downloads instantly with the same name.
- [ ] Open loads a real previously saved file back into the editor.
- [ ] Print → real preview + working `window.print()`.
- [ ] Status bar shows accurate live word count.
- [ ] No placeholder/dummy buttons — everything present must work.

---

## Notes on Fidelity vs. Simplicity

- Keep the ribbon color scheme, icon shapes, and menu structure close to real MS Word — students are visually matching the tool to textbook screenshots.
- Do **not** rename any control (e.g., don't rename "Justify" to "Even text" or similar) — use exact Word terminology throughout.
- Simplification is acceptable **only** in scope (e.g., other ribbon tabs can be inert, grammar-check can be a small simulated set instead of a full NLP engine) — never in the naming, layout, or working behavior of the features explicitly listed above.
