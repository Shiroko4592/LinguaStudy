# LinguaStudy

## Overview
LinguaStudy is a simple, static web application that displays GitHub Wiki content in an easy-to-navigate format. The application fetches markdown files from a GitHub Wiki repository and renders them with a sidebar navigation.

## Project Type
- **Type**: Static HTML/CSS/JavaScript application
- **Framework**: Vanilla JavaScript with marked.js for markdown rendering
- **Language**: Korean (ko)

## Architecture

### Structure
- `index.html` - Single-page application containing all HTML, CSS, and JavaScript

### Features
- Sidebar navigation that loads wiki page list from GitHub API
- Dynamic markdown content rendering using marked.js library
- Hash-based routing for navigation between pages
- Error handling for failed API requests and missing pages

### GitHub Integration
The application fetches content from:
- **User**: Shiroko4592
- **Repository**: LinguaStudy.wiki
- **Raw Content URL**: `https://raw.githubusercontent.com/Shiroko4592/LinguaStudy.wiki/master`
- **API URL**: `https://api.github.com/repos/Shiroko4592/LinguaStudy.wiki/contents`

## Development Setup

### Running Locally
The application runs on a simple Python HTTP server on port 5000:
```bash
python -m http.server 5000
```

### Deployment
- **Deployment Type**: Static site
- **Public Directory**: `.` (root directory)
- The application can be deployed as a static site since it has no backend dependencies

## Recent Changes (November 21, 2025)
- Added error handling to `loadTOC()` function to gracefully handle API failures
- Added error handling to `loadPage()` function to display user-friendly error messages
- Configured Replit workflow to serve the application on port 5000
- Set up static deployment configuration

## Dependencies
- **Runtime**: Python 3.11 (for development HTTP server only)
- **External Libraries**: 
  - marked.js (loaded via CDN) - for markdown parsing and rendering

## Notes
- The application may show errors if the GitHub Wiki is not publicly accessible or if GitHub API rate limits are reached
- Error messages are displayed gracefully to users instead of causing application crashes
- No build process or package manager required
