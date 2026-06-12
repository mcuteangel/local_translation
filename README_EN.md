# 🌐 Local Translation Tool

🌍 [Persian Version](README.md)

A lightweight, zero-dependency, client-side tool designed for string-by-string localization of **Android XML**, **JSON**, **YAML**, **Properties**, **CSV**, **INI** and **PO (Gettext)** files. It enables translators to easily manage project language assets locally without breaking nested or strict file structures.

🔗 **Live Version:** [https://mcuteangel.github.io/local_translation/](https://mcuteangel.github.io/local_translation/)

![Screenshot](Screenshot.png)

---

## ✨ Key Features

### 🗂️ 7 Standard Format Support
Intelligent parsing and serialization of Android `strings.xml` files, nested `JSON` files, `YAML` files, `Properties`, `CSV`, `INI`, and `PO (Gettext)` files.

### 🔒 Complete Privacy (Local-First) + AES-256 Encryption
No server or database required; all processing happens in your browser and data is stored in `LocalStorage`. Optionally encrypt your data with **AES-256-GCM** algorithm.

### 🛡️ Smart Output & Standard Fallback
- Untranslated keys are removed during export to maintain automatic fallback mechanism.
- Prevents incorrect copying of source text to target.

### 🔍 Advanced Filtering & Search
Filter strings by status: "All", "Translated", "Missing" + search in keys and text content.

### 🌍 Multi-Language Support
Add and switch between multiple target languages, translating each independently.

### 🤖 Auto Translation via API
Support for **Google Translate API** and **DeepL API** for automatic string translation.

### ✏️ Batch Editing
Find & replace, prefix/suffix application, and bulk clearing of translations.

### 📋 Diff View
Side-by-side comparison of source and current translations for accurate change review.

### 📚 Version Management
Save, restore, and delete translation versions with history tracking.

### 🧩 Plugin System
Extensible plugin architecture for adding custom features without modifying core code.

### ⚡ Optimized UX
- Quick-insert buttons for variables and special characters (`%s`, `%d`, `{0}`, etc.).
- `Ctrl + Enter` shortcut to save and auto-jump to next empty field.
- Flexible pagination + Virtual Scrolling for large files.
- Auto-save to LocalStorage.

---

## 🆕 New Features

| Feature | Description |
|---------|-------------|
| **CSV Format** | Parse and export comma/tab-separated files |
| **INI Format** | Support for INI configuration files |
| **PO Format** | Support for Gettext PO files |
| **Google Translate API** | Auto-translate with Google Translate |
| **DeepL API** | Auto-translate with DeepL (Free & Pro) |
| **AES-256 Encryption** | Encrypt data with Web Crypto API |
| **Multi-Language** | Add and switch between multiple languages |
| **Batch Editing** | Find/replace, prefix/suffix, bulk clearing |
| **Diff View** | Side-by-side source vs translation comparison |
| **Version Management** | Save, restore, and delete translation versions |
| **Plugin System** | Extensible architecture for custom features |
| **Virtual Scrolling** | Performance optimization for large files |

---

## 🛠️ Tech Stack

* **HTML5** (Semantic structure)
* **Tailwind CSS** (Responsive & Modern UI)
* **Vanilla JavaScript (ES6+)** (No frameworks, pure performance)
* **Web Crypto API** (AES-256-GCM encryption)
* **Web Workers** (Background processing)

---

## 🚀 How to Use

### 1. Load Source File
Upload your project's primary language file (e.g., `strings.xml`, `en.json`, `en.yaml`, `en.properties`, `en.csv`, `en.ini` or `en.po`). The tool extracts keys and converts the tree structure to a flat format.

### 2. Load Target File (Optional)
If you have previously translated part of the file, you can upload the incomplete target file to populate your previous translations in the fields.

### 3. Translate & Navigate
Start translating strings. After completing each string, pressing **`Ctrl + Enter`** automatically moves your position to the next untranslated string.

### 4. Export
When finished, click Export and select your desired format. The final file is cleanly serialized, reconstructing the original structure.

---

## ⚙️ Translation API Setup

1. Click the **Settings** button (gear icon).
2. Select your service: **Google Translate** or **DeepL**.
3. Enter your API key.
4. For DeepL, select your account type (Free or Pro).
5. Click **Save API Settings**.

After configuration, use the **AI Translate** button to auto-translate all untranslated strings.

---

## 🔐 Data Encryption

1. Go to **Settings**.
2. In the encryption section, enter a password.
3. Click **Enable**.
4. Your data will be encrypted with AES-256-GCM going forward.

> **Warning:** Do not forget your password! Data cannot be recovered without it.

---

## 🌍 Working with Multiple Languages

1. After loading the source file, add target languages from the **Language** section in the sidebar.
2. Switch between languages and translate each independently.
3. Each language is saved separately.

---

## 📚 Version Management

- At any point, click **Save Version** to backup the current state.
- Click **Restore** to revert to previous versions.
- Up to 20 recent versions are stored.

---

## 🧩 Plugin Development

To write a plugin, use the following structure:

```javascript
PluginSystem.register({
  name: 'my-plugin',
  description: 'Plugin description',
  hooks: {
    'before-save': (data) => {
      // Transform data before saving
      return modifiedData;
    },
    'after-load': (data) => {
      // Transform data after loading
      return modifiedData;
    }
  }
});
```

### Available Hooks:
- `before-save`: Before saving data to LocalStorage
- `after-load`: After loading data from storage

---

## 🧪 Running Tests

Open `tests.html` in your browser:

```bash
open tests.html
```

All tests run in the browser and display results.

---

## 📦 Installation

This project is a **Single-page Static Web App**. To run it, simply clone the repository and open `index.html` in your browser:

```bash
# Clone the repository
git clone https://github.com/mcuteangel/local_translation.git

# Enter the project directory
cd local_translation

# Run (just open the file in your browser)
open index.html
```

---

## 📝 License

This project is released under the [MIT](https://www.google.com/search?q=LICENSE) license. Use and development for personal and commercial purposes is completely free.
