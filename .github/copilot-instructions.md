# Copilot Instructions

## Project Overview

This is a starter template for beginners learning HTML and CSS at 4Geeks Academy. It provides a minimal boilerplate with a Flask development server (`server.py`) that serves static files from the root directory. Students modify `index.html` and `styles.css` to build their first website.

## Architecture & File Structure

- **index.html** - Main entry point; students create their HTML structure here
- **styles.css** - External stylesheet linked in `<head>` of index.html
- **server.py** - Flask development server (port 3000) that serves static files with caching disabled
- **learn.json** - Metadata file for 4Geeks Academy platform (includes i18n for en/es)

## Key Workflows

### Starting the Development Server
```bash
pip3 install flask && python3 server.py
```
Server runs on `http://localhost:3000` with debug mode enabled and automatic reload on file changes.

### Optional Python Backend
If an `app.py` file exists in the root, the server redirects the `/` route to execute it instead of serving `index.html`. This allows students to add a Python backend if needed.

## Critical Developer Patterns

1. **Static File Serving**: Flask serves all files from the root directory; CSS, JS, and images are accessed as relative paths from root (e.g., `href="styles.css"`)

2. **HTML & CSS Linking**: All CSS must be linked in the `<head>` tag using `<link rel="stylesheet" href="styles.css">`

3. **Caching Disabled**: Development server has caching explicitly disabled (`SEND_FILE_MAX_AGE_DEFAULT = 0`) to ensure changes appear immediately

4. **Error Handling**: Missing `index.html` shows a 404 error with a helpful message; Flask `app.py` errors display in the browser as `<pre>` with red text

5. **Internationalization**: `learn.json` uses nested objects with language codes (en, es, us) for titles and descriptions

## Common Modifications

- **Adding CSS**: Create new CSS files and link them in `<head>`; avoid inline styles initially
- **Adding JavaScript**: Create `.js` files at root level and link with `<script src="file.js"></script>` before `</body>`
- **Multi-page Projects**: Create additional `.html` files at root; Flask serves them at equivalent routes

## Integration Points

- The template integrates with the 4Geeks Academy learning platform via `learn.json`
- Students may later add `app.py` to introduce Python backend concepts
- No database or external dependencies required for basic projects
