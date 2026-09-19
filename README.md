# Lichess Markdown Studio

A visual editor and converter for [Lichess](https://lichess.org) team biographies. Write your bio like in any text editor, insert emojis with your keyboard, and on export they are automatically converted to the HTML entities that Lichess understands (`&#128512;`).

🌐 **Live demo:** https://meowdev1011.github.io/Lichess-Marckdown-Studio-/
---

## ✨ Features

- **Visual editor** with bold, italic, H2–H6 headings, lists, and quotes.
- **Automatic emoji conversion** to HTML entities on export.
- **Live preview area** — paste markdown + entities and see the rendered result exactly as Lichess would display it.
- **Emoji ↔ HTML entity converter** for quick one-off conversions.
- **Download the result** as `team_bio_your_team_name.md`.
- **5 languages**: English, Español, Français, Deutsch, Português.
- **Auto-detection** of browser language and system light/dark theme.
- **Manual blue theme** on top of light and dark modes.
- **Offline**: everything runs in the browser, no servers, no APIs.

---

## 🚀 How to use

1. Open the page.
2. Enter the **team name** (required, 3–30 characters).
3. Write the **biography** in the editor.
4. Press **Export markdown** to see the result with emojis already converted.
5. Press **Download .md** to save the file, or **Copy** to copy it.

Paste the result into your team description on Lichess — done.

---

## 🎨 Color modes

| Mode | Background | Logo |
|---|---|---|
| Light | light blue-white | `logo.png` |
| Dark | night blue | `logo_black_blue.png` |
| Blue | bright blue | `logo_black_blue.png` |

- Light/dark mode is picked **automatically** from your operating system.
- Blue mode is **manual only** — press the theme button to cycle it in.
- The button cycles: light → dark → blue → light.

---

## 🌍 Languages

The interface ships in:

- 🇬🇧 English
- 🇪🇸 Español
- 🇫🇷 Français
- 🇩🇪 Deutsch
- 🇵🇹 Português

The language is detected from `navigator.language` on load. You can override it with the selector in the header.

---

## 🧠 How the conversion works

Every emoji in Unicode has an assigned decimal number. For example:

| Emoji | Decimal | HTML entity |
|---|---|---|
| 😀 | 128512 | `&#128512;` |
| 🎉 | 127881 | `&#127881;` |
| ♟️ | 9823 | `&#9823;` |

Lichess uses these **HTML entities** internally because they survive encoding changes, font swaps, and copy-paste between platforms. A raw emoji can be lost or turned into a box; `&#128512;` always means the same thing.

The editor reads each character with `codePointAt(0)`, gets the number, and wraps it with `&#` and `;`. That's it.

**Note:** it works with any emoji in the Unicode standard, today or in the future, with no lists or updates required.

---

## 📝 Markdown supported by Lichess

| Name | Syntax | Renders as |
|---|---|---|
| Heading 2 | `## Text` | Large **Text** |
| Heading 3 | `### Text` | Slightly smaller |
| Heading 4–6 | `#### Text` | Minor headings |
| Bold | `**Text**` | **Text** |
| Italic | `*Text*` | *Text* |
| Bold + italic | `***Text***` | ***Text*** |
| Strikethrough | `~~Text~~` | ~~Text~~ |
| Bullet list | `- Item` | • Item |
| Numbered list | `1. Item` | 1. Item |
| Link | `[Text](url)` | [Text](url) |
| Inline code | `` `code` `` | `code` |
| Divider | `---` | Horizontal rule |
| Emoji | `&#128512;` | 😀 |

---

## 📁 Project structure

```

Lichess-Marckdown-Studio/
├── index.html              # Main editor
├── 404.html                # Copy of index.html for GitHub Pages
├── logo.png                # Logo for the light theme
├── logo_black_blue.png     # Logo for dark and blue themes
└── README.md               # This file

```

---

## 🛠️ Tech

- **HTML5** + **CSS3** + **vanilla JavaScript**.
- **No dependencies**, no frameworks, no build step.
- Single self-contained HTML file.
- CSS variables for the three themes.
- Inline SVG icons (sprite in `<defs>`).

---

## 📄 License

Released under the **MIT License**.

Full terms: https://github.com/MeowDev1011/Lichess-Marckdown-Studio-/blob/main/LICENSE

---

## 👤 Author

Created by **[GatoChess89](https://lichess.org/@/GatoChess89)**.

- Lichess: [@GatoChess89](https://lichess.org/@/GatoChess89)
- GitHub: [@MeowDev1011](https://github.com/MeowDev1011)

Source code: https://github.com/MeowDev1011/Lichess-Marckdown-Studio-

---

## ⚠️ Disclaimer

**Independent, unofficial tool.** Not affiliated with, endorsed by, or sponsored by Lichess. "Lichess" is a trademark of the Lichess Foundation; this project is a community contribution.
