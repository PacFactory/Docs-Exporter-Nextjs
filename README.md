# README.md

## Export Nextjs Docs Script

The script automates the process of cloning documentation repositories, converting Markdown files to HTML, and generating PDF files. This README covers installation and usage.

Fork of the original [Docs-Exporter](https://github.com/Riyooo/Docs-Exporter). Thanks to Riyoo for the original!

---

## Features

- Clone remote repositories with sparse checkout.
- Convert Markdown files to HTML with code block and image path preprocessing.
- Generate PDFs with custom headers, footers, and styles.
- Automatically create a hierarchical Table of Contents (ToC).
- Detect the latest version of the documentation.
- Handles YAML frontmatter for metadata-rich documentation.

---

## Installation

### Prerequisites

- Python 3.8+
- Required Python packages:
  - `markdown`
  - `yaml`
  - `tqdm`
  - `playwright`
  - `gitpython`
- Ensure you have Playwright installed and configured:
  ```bash
  pip install playwright
  playwright install
  ```

### Clone the Repository and Install
Clone the project repository, create a virtual environment, activate it, and install requirements.

---
	```bash
	git clone https://github.com/pacnpal/Docs-Exporter.git
	cd Docs-Exporter
	python -m venv .venv
	source .venv/bin/activate
	pip install -r requirements.txt
	playwright install
	```
## Usage

### 1. Clone and Update Nextjs Repository
Run the script to clone or update the remote documentation repository:
```bash
python export-docs.py
```

### 2. Convert Markdown to HTML
The script automatically processes `.md` and `.mdx` files, converting them to styled HTML.

### 3. Generate PDF
A PDF is created with a generated title and ToC. Ensure no other process is using the output file.

### Example Configuration
```python
repo_url = "https://github.com/vercel/next.js.git"
branch = "canary"
docs_dir = "docs"
```

### Output
- PDF file: `Next.js_Docs_vXX.XX.X_YYYY-MM-DD.pdf` or `Next.js_Documentation.pdf`
- Logs: Process information printed to the terminal.

---

## LICENSE

This project is governed by the [LICENSE](LICENSE) file. Please ensure compliance when redistributing or modifying the script.
