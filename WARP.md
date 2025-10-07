# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Project Overview

This is a writing project repository designed for organizing documents, drafts, and research materials. The project follows a structured workflow for content creation and revision.

## Project Structure

- `docs/` - Final documents and completed writing pieces
- `drafts/` - Work-in-progress content and early drafts  
- `notes/` - Research notes, ideas, and brainstorming content
- `resources/` - Reference materials, images, and supporting files

## Writing Workflow

The project follows a three-stage writing process:
1. **Research & Planning**: Ideas and research materials start in `notes/`
2. **Drafting & Revision**: Active writing and editing happens in `drafts/`
3. **Publishing**: Completed work is moved to `docs/`

## Common Commands

Since this is a content/documentation project without traditional build tools, common operations are file management tasks:

### File Operations
```powershell
# Create a new draft
New-Item -Path "drafts\new-article.md" -ItemType File

# Move completed draft to docs
Move-Item -Path "drafts\completed-article.md" -Destination "docs\"

# List all markdown files
Get-ChildItem -Recurse -Filter "*.md" | Select-Object FullName

# Find content by keyword
Get-ChildItem -Recurse -Filter "*.md" | Select-String -Pattern "keyword"
```

### Content Management
```powershell
# Count words in a document (requires PowerShell)
(Get-Content "drafts\article.md" | Measure-Object -Word).Words

# Show recent changes to files
Get-ChildItem -Recurse | Sort-Object LastWriteTime -Descending | Select-Object -First 10
```

## File Conventions

- Use Markdown (.md) for text content
- Use descriptive filenames with hyphens: `my-article-title.md`
- Keep supporting files (images, data) in `resources/`
- Use consistent naming patterns within each directory

## Environment Notes

- This is a Windows environment using PowerShell
- Repository is now configured with GitHub for version control
- The repository contains structural directories and documentation