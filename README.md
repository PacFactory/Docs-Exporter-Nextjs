# README.md
# Documentation to PDF Converter

A Python script that clones documentation from a Git repository (default: Next.js), processes it, and generates a well-formatted PDF with table of contents, proper formatting, and consistent styling.

## Features

- Clones specific documentation directories from Git repositories
- Processes Markdown and MDX files
- Generates table of contents with proper numbering
- Handles code blocks with filename annotations
- Processes frontmatter for metadata
- Supports image path transformations
- Creates PDF with customizable headers and footers
- Includes cover page and proper page breaks

## Requirements

### System Requirements
- Python 3.7+
- Git installed and accessible from command line
- Internet connection for cloning repositories

### Python Dependencies
Install all required packages using:
```bash
pip install -r requirements.txt
```

Then install Playwright's browser:
```bash
playwright install chromium
```

## Setup

1. Clone this repository:
```bash
git clone 
cd 
```

2. Install dependencies:
```bash
pip install -r requirements.txt
playwright install chromium
```

3. Ensure you have a `styles.css` file in the same directory as the script. This file should contain your desired CSS styling for the PDF output.

## Usage

1. Basic usage with default settings (Next.js documentation):
```bash
python docs_to_pdf.py
```

2. The script will:
   - Clone/update the specified Git repository
   - Process all documentation files
   - Generate a PDF with proper formatting
   - Include a cover page and table of contents

## Configuration

You can modify these variables in the script for different configurations:

```python
repo_dir = "nextjs-docs"  # Local directory for cloned repo
repo_url = "https://github.com/vercel/next.js.git"  # Repository URL
branch = "canary"  # Branch to clone
docs_dir = "docs"  # Directory containing documentation

# Image URL transformation settings
Change_img_url = True
base_path = "https://nextjs.org/_next/image?url="
path_args = "&w=1920&q=75"
```

## PDF Output Settings

The PDF generation includes:
- A4 format
- Custom margins
- Page numbers in header
- Generation date in footer
- Background colors/images
- Proper page breaks between sections

## File Organization

- `docs_to_pdf.py`: Main script file
- `requirements.txt`: Python dependencies
- `styles.css`: CSS styling for PDF output
- `README.md`: This documentation

## Troubleshooting

1. If the PDF file is locked:
   - Ensure the output PDF is not open in any application
   - Check file permissions

2. If images are not loading:
   - Verify internet connection
   - Check if image URLs are accessible
   - Adjust the `wait_for_load_state` timing if needed

3. If the repository won't clone:
   - Verify Git is installed and accessible
   - Check internet connection
   - Ensure you have access to the repository

## Notes

- The script creates temporary files during processing
- Large documentation sets may take several minutes to process
- Memory usage depends on the size of the documentation
- The script requires active internet connection for repository cloning and image processing

## CSS Recommendations

Your `styles.css` should include at least these basic styles for proper PDF formatting:

```css
body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    margin: 0;
    padding: 20px;
}

.master-container {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
}

.container {
    text-align: center;
}

.title {
    font-size: 24px;
    font-weight: bold;
    margin-bottom: 20px;
}

.date {
    font-size: 16px;
}

.page-break {
    page-break-after: always;
}

code {
    background-color: #f4f4f4;
    padding: 2px 4px;
    border-radius: 4px;
}

pre {
    background-color: #f8f8f8;
    padding: 15px;
    border-radius: 5px;
    overflow-x: auto;
}

.code-header {
    background-color: #e0e0e0;
    padding: 5px 10px;
    border-radius: 5px 5px 0 0;
}

table {
    border-collapse: collapse;
    width: 100%;
    margin: 15px 0;
}

th, td {
    border: 1px solid #ddd;
    padding: 8px;
    text-align: left;
}

th {
    background-color: #f5f5f5;
}
```