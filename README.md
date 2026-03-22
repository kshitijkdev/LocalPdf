# LocalPDF 📄
**A private, AI-powered PDF toolkit that runs entirely in your browser — no uploads, no servers, no tracking.**

🔗 **Live Demo:** https://kshitijkdev.github.io/LocalPdf/CODE/LocalPDF.html

---

## ✨ Features

### 📁 Organize
| Tool | Description |
|------|-------------|
| **Merge** | Combine multiple PDFs into one. Drag to reorder files before merging. |
| **Split** | Split a PDF by each page, custom ranges, or every N pages. |
| **Extract** | Keep only the pages you want. Click thumbnails or enter a range. |
| **Reorder** | Drag and drop page thumbnails to rearrange them. |

### ✏️ Modify
| Tool | Description |
|------|-------------|
| **Rotate** | Rotate all, odd, even, or specific pages by any angle. |
| **Watermark** | Add custom text watermarks with control over size, opacity, color, and position. |
| **Page Numbers** | Stamp page numbers in multiple formats and positions. |
| **Compress** | Reduce file size by stripping metadata and unused data. |

### 🔒 Security
| Tool | Description |
|------|-------------|
| **Protect** | Password-protect a PDF with granular permissions (edit, copy, print). |
| **Unlock** | Remove password protection from a PDF. |

### 🖼️ Convert
| Tool | Description |
|------|-------------|
| **PDF to Images** | Export pages as PNG or JPEG at multiple DPI settings. |

### 🤖 AI Tools (powered by local Ollama)
| Tool | Description |
|------|-------------|
| **Summarize** | Generate short, detailed, or bullet-point summaries of any PDF. |
| **Chat with PDF** | Ask questions about your document in a multi-turn conversation. |
| **Auto-rename** | AI suggests a descriptive, clean filename based on document content. |

> **All AI processing happens locally via [Ollama](https://ollama.com). Your files never leave your machine.**

---

## 🚀 Usage

### Option 1 — Use Online (PDF tools only)
Just open the live demo link in any modern browser. No install needed.

### Option 2 — Run Locally with AI features
To use the AI tools, you need [Ollama](https://ollama.com) running locally.

**1. Install Ollama** from https://ollama.com

**2. Pull a model:**
```bash
ollama pull llama3
```

**3. Start Ollama with CORS enabled:**
```bash
OLLAMA_ORIGINS="*" ollama serve
```
On Windows (PowerShell):
```powershell
$env:OLLAMA_ORIGINS="*"; ollama serve
```

**4. Serve the HTML file locally:**
```bash
cd LocalPdf/CODE
python -m http.server 8080
```

**5. Open in browser:**
```
http://localhost:8080/LocalPDF.html
```

**6. Configure Ollama in the app:**
- Click **⚙ Ollama Settings** in the sidebar
- URL: `http://localhost:11434`
- Model: `llama3` (or any model you pulled)
- Click **Test connection** → you should see ✓ Connected

---

## 🛠️ Tech Stack

- **Vanilla HTML / CSS / JavaScript** — zero frameworks, zero dependencies
- **[pdf-lib](https://pdf-lib.js.org/)** — PDF creation and manipulation
- **[PDF.js](https://mozilla.github.io/pdf.js/)** — PDF rendering and text extraction
- **[Ollama](https://ollama.com)** — local LLM inference for AI features

---

## 🔐 Privacy

- All PDF processing happens in your browser using JavaScript
- No files are uploaded to any server
- AI features run via Ollama on your local machine (`localhost:11434`)
- No analytics, no tracking, no cookies
- Works fully offline (except for loading CDN libraries on first open)

---

## 📦 Project Structure

```
LocalPdf/
├── CODE/
│   └── LocalPDF.html    # The entire app — one single file
├── files.zip
└── README.md
```

---

## 🤖 Supported Ollama Models

Any model that works with Ollama's `/api/chat` endpoint will work. Recommended:

| Model | Size | Best for |
|-------|------|----------|
| `llama3` | 4.7 GB | Best quality |
| `mistral` | 4.1 GB | Fast + accurate |
| `phi3` | 2.3 GB | Lightweight |
| `tinyllama` | 600 MB | Fastest, basic |

---

## 📄 License

MIT — free to use, modify, and share.

---

*Built with ❤️ by [kshitijkdev](https://github.com/kshitijkdev)*
