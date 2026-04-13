# 📊 json-to-excel

> Convert JSON & MongoDB data to Excel instantly — runs entirely in your browser, no server needed.

**Live demo →** [your-vercel-url.vercel.app](https://your-vercel-url.vercel.app)

---

## ✨ Features

- **Paste & export** — paste any JSON array or object and download a `.xlsx` file in one click
- **MongoDB support** — paste raw MongoDB shell / Compass output directly (handles `NumberInt`, `ISODate`, `ObjectId`, unquoted keys, single quotes, and more)
- **Auto-detection** — automatically detects MongoDB format, no need to manually switch
- **Live preview** — see your data as a table before exporting (up to 100 rows)
- **Smart column widths** — Excel columns are auto-sized based on your data
- **Nested objects** — choose to stringify or flatten nested objects with dot notation (e.g. `address.city`)
- **Date handling** — keep dates as strings or convert ISO strings to native Excel date cells
- **Drag & drop** — drop a `.json` file directly onto the editor
- **File upload** — click to browse and upload a `.json` or `.txt` file
- **Keyboard shortcut** — `Ctrl + Enter` to export instantly
- **100% private** — all processing happens in your browser, zero data is sent to any server
- **No install, no signup, no backend** — a single HTML file

---

## 🚀 Getting Started

### Option 1 — Use the live app
Just open the deployed URL and start pasting data. No setup required.

### Option 2 — Run locally
```bash
git clone https://github.com/arundidauli/json-to-excel.git
cd json-to-excel

# Simply open in your browser — no build step needed
open index.html
```

### Option 3 — Deploy your own to Vercel
```bash
npm i -g vercel
vercel --prod
```
Or drag the folder into [vercel.com/new](https://vercel.com/new).

---

## 📋 Supported Input Formats

### Standard JSON
```json
[
  { "name": "Alice", "age": 30, "city": "Delhi" },
  { "name": "Bob",   "age": 25, "city": "Mumbai" }
]
```

### MongoDB Shell / Compass Output
```js
[
  {
    cost: NumberInt('500'),
    createdAt: ISODate('2026-03-24T20:30:07.450Z'),
    subscriberUsername: 'AirSir',
    subscriberEmail: 'arthurvax@gmail.com',
    subscriberName: 'Arthur Vax',
    athleteName: 'Alex Johnston'
  }
]
```

### MongoDB type mappings

| MongoDB Type | Converted To |
|---|---|
| `NumberInt('500')` | `500` (integer) |
| `NumberLong('...')` | number |
| `NumberDecimal('3.14')` | `3.14` (float) |
| `ISODate('...')` | ISO date string (or Excel date) |
| `ObjectId('...')` | string |
| `BinData(...)` | `"<BinData>"` |
| Unquoted keys | quoted keys |
| Single-quoted strings | double-quoted strings |
| Trailing commas | removed |
| `undefined` | `null` |

---

## 🛠 Tech Stack

| Tool | Purpose |
|---|---|
| Vanilla HTML / CSS / JS | UI & logic — zero framework, zero dependencies |
| [SheetJS (xlsx)](https://sheetjs.com) | Excel file generation, loaded from CDN |
| [Google Fonts](https://fonts.google.com) | Inter + JetBrains Mono |
| Vercel | Hosting |

No build step. No `node_modules`. No backend. Just one file.

---

## 📁 Project Structure

```
json-to-excel/
└── index.html   # The entire app — HTML, CSS, and JS in one file
└── README.md
```

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

1. Fork the repo
2. Create your branch: `git checkout -b feature/my-feature`
3. Commit your changes: `git commit -m 'Add my feature'`
4. Push to the branch: `git push origin feature/my-feature`
5. Open a Pull Request

---

## 📄 License

MIT © [Arun Kumar](https://github.com/arundidauli)

---

<p align="center">Built with ❤️ by <a href="https://github.com/arundidauli">Arun Kumar</a></p>
