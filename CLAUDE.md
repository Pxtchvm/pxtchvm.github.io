# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Commands

### Environment Setup
```bash
uv venv .venv
source .venv/Scripts/activate  # On Windows with Git Bash
# or: source .venv/bin/activate  # On Unix/macOS
uv pip install -r requirements.txt
```

### Generate Portfolio Site
```bash
python generate_portfolio.py
```

This command generates `index.html` and `resume.html` from their respective templates using data from `portfolio.json`.

## Architecture Overview

This is a static portfolio website generator using Python and Jinja2 templates.

### Core Components

- **`generate_portfolio.py`**: Main generator script that renders HTML templates with JSON data
- **`portfolio.json`**: Central data file containing all portfolio content (personal info, projects, experience, etc.)
- **`index_template.html`**: Jinja2 template for the main portfolio page
- **`resume_template.html`**: Jinja2 template for the resume page

### Data Structure

The `portfolio.json` file contains structured data with these main sections:
- Personal information (name, contact, summary)
- Social links with embedded SVG icons
- Work experience with highlights
- Projects with image galleries
- Volunteer experience
- Education details
- Skills with proficiency levels
- Interests/hobbies with images
- Languages and fluency
- References

### Template System

- Templates use Jinja2 syntax for data binding
- SVG icons are dynamically loaded from `img/` directory and embedded inline
- Current year is automatically injected for copyright/date references
- Templates support conditional rendering of sections based on data presence

### Static Assets

- **`css/`**: Stylesheets including normalize, main styles, and resume-specific styles
- **`img/`**: Social media icons as SVG files and portfolio images
- **`portfolio_media/`**: Project images and profile photos
- **`js/app.js`**: Client-side JavaScript functionality

The site generates static HTML files suitable for GitHub Pages or any static hosting service.