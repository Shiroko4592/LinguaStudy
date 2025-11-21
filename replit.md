# LinguaStudy

## Overview
LinguaStudy is a simple, static web application that displays markdown wiki content in an easy-to-navigate format. The application supports both local markdown files and optional GitHub Wiki integration.

## Project Type
- **Type**: Static HTML/CSS/JavaScript application
- **Framework**: Vanilla JavaScript with marked.js for markdown rendering
- **Language**: Korean (ko)

## Architecture

### Structure
- `index.html` - Single-page application containing all HTML, CSS, and JavaScript
- `wiki/` - Directory containing local markdown files
  - `Home.md` - Main page
  - `About.md` - About page
  - `Tutorial.md` - Tutorial page

### Features
- Sidebar navigation with page list
- Dynamic markdown content rendering using marked.js library
- Hash-based routing for navigation between pages
- Error handling for failed API requests and missing pages
- **Dual mode support**: Local files or GitHub Wiki

### Content Modes

#### Local Mode (Default - Currently Active)
- Uses markdown files from the `wiki/` directory
- No external dependencies
- Fully functional offline
- Set `USE_GITHUB_WIKI = false` in `index.html`
- Add pages to the `LOCAL_PAGES` array

#### GitHub Wiki Mode (Optional)
- Fetches content from GitHub Wiki repository
- Requires public wiki access
- Set `USE_GITHUB_WIKI = true` in `index.html`
- Configure `USER` and `REPO` variables
- Example: Shiroko4592/LinguaStudy.wiki

## Development Setup

### Running Locally
The application runs on a simple Python HTTP server on port 5000:
```bash
python -m http.server 5000
```

### Adding New Pages (Local Mode)
1. Create a new `.md` file in the `wiki/` directory
2. Add the page name (without `.md`) to the `LOCAL_PAGES` array in `index.html`
3. The page will appear in the sidebar automatically

### Switching to GitHub Wiki Mode
1. Open `index.html`
2. Set `USE_GITHUB_WIKI = true`
3. Update `USER` and `REPO` with your GitHub username and repository name
4. Ensure your GitHub Wiki is public and contains `.md` files

### Deployment
- **Deployment Type**: Static site
- **Public Directory**: `.` (root directory)
- The application can be deployed as a static site since it has no backend dependencies

## Recent Changes (November 21, 2025)
- Added local wiki support with sample markdown files (Home, About, Tutorial)
- Implemented dual mode: local files or GitHub Wiki
- Added error handling to `loadTOC()` and `loadPage()` functions
- Created `wiki/` directory with Korean sample content
- Configured Replit workflow to serve the application on port 5000
- Set up static deployment configuration

## Dependencies
- **Runtime**: Python 3.11 (for development HTTP server only)
- **External Libraries**: 
  - marked.js (loaded via CDN) - for markdown parsing and rendering

## File Structure
```
.
├── index.html          # Main application file
├── wiki/              # Local markdown files
│   ├── Home.md        # Home page
│   ├── About.md       # About page
│   └── Tutorial.md    # Tutorial page
├── replit.md          # Project documentation
└── .gitignore         # Git ignore rules
```

## Notes
- Currently using local mode with Korean sample content
- Local mode works offline and has no external dependencies
- Switch to GitHub Wiki mode when you have a public wiki repository
- Error messages are displayed gracefully to users instead of causing application crashes
- No build process or package manager required
