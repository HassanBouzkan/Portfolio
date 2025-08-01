# Copilot Instructions for This Project

## Overview
- This is a minimal Flask web application serving a static homepage.
- Main files:
  - `app.py`: Flask app entry point, defines a single route (`/`) rendering `index.html`.
  - `templates/index.html`: Jinja2 HTML template for the homepage.
  - `static/style.css`: Stylesheet for the homepage.

## Architecture & Patterns
- Follows standard Flask structure: `app.py` at root, `templates/` for HTML, `static/` for assets.
- All HTML rendering uses Jinja2 templates. Static files are referenced via `url_for('static', ...)`.
- No database, authentication, or external API integrations present.

## Developer Workflows
- **Run locally:**
  - Use `python app.py` to start the development server (runs on `localhost:5000` by default).
  - Debug mode is enabled by default (`debug=True`).
- **No build or test scripts** are present. Add tests in a `tests/` directory if needed.
- **No external dependencies** beyond Flask (install with `pip install flask`).

## Project-Specific Conventions
- Keep all HTML templates in `templates/` and static assets in `static/`.
- Use Jinja2 syntax for dynamic content in HTML (e.g., `{{ url_for('static', filename='...') }}`).
- Route definitions should be added to `app.py`.

## Extending the Project
- To add new pages, create new HTML files in `templates/` and define new routes in `app.py`.
- For additional static files (CSS, JS, images), place them in `static/` and reference via `url_for`.

## Example: Adding a New Page
1. Add `about.html` to `templates/`.
2. Add a route in `app.py`:
   ```python
   @app.route('/about')
   def about():
       return render_template('about.html')
   ```
3. Link to the new page in `index.html` if desired.

---
For more, see [Flask documentation](https://flask.palletsprojects.com/).
