# 🌐 Local Translation Tool

🌍 [Persian Version](README.md)

A lightweight, zero-dependency, client-side tool designed for string-by-string localization of **Android XML** and **JSON** files. It enables translators to easily manage project language assets locally without breaking nested or strict file structures.

🔗 **Live Version:** [https://mcuteangel.github.io/local_translation/](https://mcuteangel.github.io/local_translation/)

![Screenshot](Screenshot.png)

---

## ✨ Key Features

* **🗂️ Standard Format Support:** Intelligent parsing and serialization of Android `strings.xml` files and nested `JSON` files.
* **🔒 Complete Privacy (Local-First):** No server or database required; all processing happens in your browser and data is stored in `LocalStorage`.
* **🛡️ Smart Output & Standard Fallback:**
  * Untranslated keys are removed during export to maintain automatic Fallback mechanism (switching to primary language) in Android or web apps.
  * Prevents incorrect copying of source text to target to maintain filter accuracy in subsequent loads.
* **🔍 Advanced Filtering & Search:** Filter strings by status including "All", "Translated", and "Missing".
* **⚡ Optimized User Experience (UX):**
  * Support for quick insertion of variables and special characters (like `%s`, `%d`, `{0}`, etc.).
  * `Ctrl + Enter` shortcut to save and automatically jump to the next empty field.
  * Flexible pagination system for high efficiency with large files.

---

## 🛠️ Tech Stack

* **HTML5** (Semantic structure)
* **Tailwind CSS** (Responsive & Modern UI)
* **Vanilla JavaScript (ES6+)** (No frameworks, pure performance)

---

## 🚀 How to Use

### 1. Load Source File
Upload your project's primary language file (e.g., English `strings.xml` or `en.json`). The tool extracts keys and converts the tree structure to a flat format.

### 2. Load Target File (Optional)
If you have previously translated part of the file, you can upload the incomplete target file (e.g., `fa.xml` or `fa.json`) to populate your previous translations in the fields.

### 3. Translate & Navigate
Start translating strings. After completing each string, pressing **`Ctrl + Enter`** automatically moves your position to the next untranslated string.

### 4. Export
When finished, select your desired format and export. The final file is cleanly serialized or un-flattened, reconstructing the original structure (including arrays in XML and tree structures in JSON).

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
