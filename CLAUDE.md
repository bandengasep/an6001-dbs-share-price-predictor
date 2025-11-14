# CLAUDE.md - AI Assistant Guide for AN6001 AI Big Data MSBA Project

This document provides comprehensive guidance for AI assistants working with this codebase.

## Project Overview

**Project Name:** AN6001 AI Big Data MSBA
**Type:** Educational Flask Web Application
**Primary Language:** Python 3
**Framework:** Flask
**Purpose:** Course project foundation for AI and Big Data learning in MSBA program
**Maturity Level:** Early-stage/Educational - Basic Flask setup ready for feature expansion

## Repository Structure

```
an6001-ai-big-data-msba/
├── app.py                  # Flask application entry point (10 lines)
├── static/                 # Static web assets
│   └── styles.css         # Responsive CSS styling (97 lines)
├── templates/              # Flask Jinja2 templates
│   └── index.html         # Main HTML template (22 lines)
└── .vscode/                # VSCode workspace configuration
    └── settings.json      # Python environment settings
```

### Directory Purposes

- **`app.py`**: Main Flask application file containing route definitions, application initialization, and entry point
- **`static/`**: Static assets directory for CSS, JavaScript, images, and other client-side resources
- **`templates/`**: Flask Jinja2 template files for HTML rendering
- **`.vscode/`**: IDE-specific configuration (VSCode workspace settings)

## Technology Stack

### Backend
- **Flask**: Python web framework for routing and template rendering
- **Jinja2**: Template engine (built into Flask)
- **Python 3**: Primary backend language

### Frontend
- **HTML5**: Markup language with semantic elements
- **CSS3**: Styling with modern features (Flexbox, CSS Grid, media queries)
- **Responsive Design**: Mobile-first approach with breakpoint at 768px

### Development Tools
- **Git**: Version control
- **VSCode**: Configured IDE with Python environment management
- **System Python**: No virtual environment currently configured

## Key Files Reference

| File | Purpose | Lines | Key Features |
|------|---------|-------|--------------|
| `app.py` | Flask app entry point | 10 | Single route handler, template rendering, GET/POST support |
| `templates/index.html` | Main webpage | 22 | Welcome page, responsive viewport, Jinja2 syntax |
| `static/styles.css` | Application styling | 97 | Flexbox layout, mobile responsive, blue theme (#007bff) |
| `.vscode/settings.json` | IDE config | 4 | Python environment settings |

## Development Workflows

### Running the Application

```bash
# Install Flask (if not already installed)
pip install flask

# Run the Flask development server
python app.py

# Access the application at http://127.0.0.1:5000
```

### Git Workflow

**Current Branch:** `claude/claude-md-mhynj7cvrjh1jbcb-01RsV65H5NoiNejgXzuT2sU1`

**Important Git Rules:**
- Always develop on Claude-specific branches (prefix: `claude/`)
- Use descriptive commit messages
- Push with `-u origin <branch-name>` to set upstream
- Branch names must match session ID format for push authorization

**Recent Commit History:**
```
160914e - "added some files" (templates, static, config)
b877263 - "Initialize Flask app in app.py" (initial setup)
```

## Code Conventions & Patterns

### Python Conventions
- **Indentation**: 4 spaces
- **Route Decorators**: Use `@app.route()` decorator pattern
- **Import Organization**: Flask imports first, then application modules
- **Entry Point**: Use `if __name__ == "__main__":` pattern
- **Naming**: Snake_case for functions and variables

### Flask-Specific Patterns
- **Project Structure**: Standard Flask layout (app.py, templates/, static/)
- **Template Rendering**: Use `render_template()` for all HTML responses
- **Static Files**: Reference via `url_for('static', filename='...')` in templates
- **Route Methods**: Explicitly declare HTTP methods in `@app.route()` decorator

### Frontend Conventions
- **CSS Class Naming**: Descriptive class names (`.container`, `.image-class`)
- **Responsive Design**: Mobile-first approach with media queries
- **Color Scheme**: Blue theme - Primary: #007bff, Hover: #0056b3
- **Layout**: Flexbox for centering, CSS Grid for complex layouts
- **Comments**: Include descriptive comments for complex CSS rules

### HTML/Template Patterns
- **Mobile Viewport**: Always include viewport meta tag for responsive design
- **Flask Helpers**: Use `url_for()` for static asset and route references
- **Jinja2 Syntax**: Follow Flask template conventions for variable interpolation

## Current State & Known Issues

### Active Features
✅ Basic Flask application initialized
✅ Single route handler at "/" endpoint
✅ Template rendering functional
✅ Responsive CSS styling implemented
✅ GET and POST method support configured

### Missing Components
❌ **No requirements.txt** - Dependencies not documented
❌ **No .gitignore** - All files tracked, including IDE configs
❌ **No README.md** - Setup instructions not documented
❌ **No testing framework** - No pytest or unittest configured
❌ **No error handling** - No try/except blocks or error pages
❌ **No database** - No data persistence layer
❌ **No virtual environment** - Uses system Python
❌ **No CI/CD** - No automated testing or deployment
❌ **No logging** - No application logging configured

### Code Quality Notes
⚠️ **Unused Import**: `request` imported in app.py but not used
⚠️ **No validation**: No input validation or sanitization
⚠️ **No authentication**: No user authentication or authorization
⚠️ **Hardcoded values**: No configuration management (no .env file)

## Working with This Codebase

### Before Making Changes

1. **Read the existing code** - Understand current structure before adding features
2. **Check for unused imports** - Remove or use the `request` import in app.py
3. **Consider dependencies** - Create requirements.txt if adding new packages
4. **Test locally** - Run Flask app to verify changes work
5. **Maintain conventions** - Follow existing patterns for consistency

### Adding New Features

**For new routes:**
```python
@app.route("/your-route", methods=["GET", "POST"])
def your_function():
    # Handle request
    return render_template("your_template.html")
```

**For new templates:**
1. Create HTML file in `templates/` directory
2. Link to static files using `url_for('static', filename='...')`
3. Include viewport meta tag for responsive design
4. Follow existing HTML structure

**For new styling:**
1. Add CSS rules to `static/styles.css`
2. Maintain mobile-first responsive approach
3. Use existing color scheme for consistency
4. Add comments for complex rules

### Best Practices for AI Assistants

1. **Always create requirements.txt** when adding Python dependencies
2. **Add error handling** for production-ready code
3. **Create .gitignore** to exclude venv/, __pycache__/, *.pyc, .env
4. **Document new features** in code comments and README
5. **Test routes** before committing (verify GET/POST behavior)
6. **Maintain responsive design** when modifying CSS
7. **Use environment variables** for configuration (create .env file)
8. **Add input validation** for user-submitted data
9. **Consider security** - sanitize inputs, use CSRF protection
10. **Keep code DRY** - Extract repeated patterns into functions

### Common Tasks

**Adding a new dependency:**
```bash
# Install the package
pip install package-name

# Document in requirements.txt (create if doesn't exist)
echo "package-name==version" >> requirements.txt
```

**Creating a new route with form handling:**
```python
@app.route("/form", methods=["GET", "POST"])
def handle_form():
    if request.method == "POST":
        # Process form data
        data = request.form.get("field_name")
        # Validate and handle data
        return redirect(url_for("index"))
    return render_template("form.html")
```

**Adding CSS for a new component:**
```css
/* Component name and purpose */
.component-class {
    /* Desktop styles */
}

@media (max-width: 768px) {
    .component-class {
        /* Mobile styles */
    }
}
```

## File Modification Guidelines

### When modifying app.py:
- Import only what you use (remove unused `request` if not needed)
- Add docstrings for new functions
- Handle both GET and POST methods appropriately
- Add error handling with try/except blocks
- Use meaningful function names

### When modifying templates:
- Maintain Jinja2 syntax consistency
- Use `url_for()` for all links and static references
- Include CSRF tokens for forms (when Flask-WTF added)
- Keep HTML semantic and accessible
- Test on multiple screen sizes

### When modifying CSS:
- Maintain mobile-first approach
- Use existing color variables/theme
- Add comments for complex selectors
- Test responsive breakpoints
- Keep specificity low for maintainability

## Security Considerations

⚠️ **Current Security Gaps:**
- No CSRF protection (add Flask-WTF)
- No input validation or sanitization
- No SQL injection protection (no database yet)
- No XSS prevention measures
- Debug mode may be enabled in production

**When adding security features:**
1. Install Flask-WTF for CSRF protection
2. Use Flask-SQLAlchemy with parameterized queries
3. Validate and sanitize all user inputs
4. Disable debug mode in production
5. Use environment variables for secrets
6. Add rate limiting for API endpoints

## Testing Recommendations

**When adding tests:**
1. Use pytest as testing framework
2. Create `tests/` directory with `__init__.py`
3. Test route responses (status codes, content)
4. Test form validation logic
5. Mock database calls
6. Aim for >80% code coverage

**Example test structure:**
```
tests/
├── __init__.py
├── test_routes.py
├── test_forms.py
└── conftest.py
```

## Deployment Considerations

**Before deploying:**
- [ ] Set `debug=False` in production
- [ ] Use production WSGI server (Gunicorn, uWSGI)
- [ ] Configure environment variables
- [ ] Set up database (if needed)
- [ ] Add logging configuration
- [ ] Enable HTTPS
- [ ] Set up monitoring/error tracking
- [ ] Configure CORS if building API

## Course Context

This project is for **AN6001 AI Big Data** in an MSBA (Master of Science in Business Analytics) program. Expected future additions likely include:
- Machine learning model integration
- Data processing pipelines
- Big data storage/retrieval
- AI-powered analytics features
- Data visualization dashboards
- RESTful API endpoints for ML models

## Quick Reference Commands

```bash
# Run development server
python app.py

# Install dependencies (when requirements.txt exists)
pip install -r requirements.txt

# Create requirements.txt
pip freeze > requirements.txt

# Git commands for this branch
git status
git add .
git commit -m "Descriptive message"
git push -u origin claude/claude-md-mhynj7cvrjh1jbcb-01RsV65H5NoiNejgXzuT2sU1

# Check Flask routes
python -c "from app import app; print(app.url_map)"
```

## Contact & Resources

- **Flask Documentation**: https://flask.palletsprojects.com/
- **Jinja2 Templates**: https://jinja.palletsprojects.com/
- **Git Workflow**: Follow Claude AI branch naming conventions

---

**Last Updated:** 2025-11-14
**Repository Status:** Clean working tree
**Total Lines of Code:** 129 (10 Python, 22 HTML, 97 CSS)
**Commit Count:** 2 commits

---

## Notes for AI Assistants

When working with this codebase:
1. **Start simple** - This is an educational project, prioritize clarity over complexity
2. **Ask before major changes** - Confirm architectural decisions with the user
3. **Document everything** - Add comments, docstrings, and update this file
4. **Test incrementally** - Verify each change works before moving to the next
5. **Maintain structure** - Keep Flask conventions and project organization
6. **Consider the learning context** - Code should be educational and well-explained
7. **Check git branch** - Always verify you're on the correct Claude branch before pushing
8. **Create requirements.txt** - Document dependencies for reproducibility
9. **Add .gitignore** - Prevent committing unnecessary files
10. **Security first** - Even in learning projects, follow security best practices
