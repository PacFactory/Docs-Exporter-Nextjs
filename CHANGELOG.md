# CHANGELOG.md

---

## General Changes
1. **Code Refactoring**
   - Significant restructuring of the functions to improve readability and maintainability.
   - Added Playwright to replace wkhtmltopdf.
   - Introduction of meaningful function and variable names for better clarity.
   
2. **Error Handling**
   - Enhanced error handling with `try-except` blocks, especially for frontmatter parsing and file operations.

---

## New Features
1. **HTML Preprocessing**
   - Added functions `preprocess_code_blocks` and `process_image_paths` to handle custom Markdown syntax and image path updates for rendering consistency.

2. **Frontmatter Parsing**
   - Introduced `parse_frontmatter`, `preprocess_frontmatter`, and `restore_html_tags` functions to manage YAML frontmatter in Markdown files, enhancing metadata handling.

3. **Repository Cloning**
   - Added `clone_repo` to handle Git repository cloning with sparse checkout support, improving integration with remote documentation sources.

4. **PDF Generation**
   - Integrated Playwright for rendering and generating PDFs from HTML content.
   - Added support for custom headers, footers, and styles in the generated PDFs.

5. **Table of Contents (ToC)**
   - Automatically generates a ToC from parsed metadata with proper hierarchy and numbering.

---

## Bug Fixes
1. **File Sorting**
   - Fixed sorting issues in `get_files_sorted` to prioritize `index.md` and `index.mdx` files.

2. **Open File Check**
   - Added `is_file_open` to ensure output files are not already open, preventing write conflicts.

3. **Version Detection**
   - Improved `find_latest_version` logic to detect and sort unique versions from HTML content.

---

## Performance Improvements
- Optimized file processing loop to handle large repositories more efficiently.
- Improved Playwright's rendering performance by preloading images and resources.

---