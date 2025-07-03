# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a curated collection of high-quality, structured prompts for various AI-powered generation tasks. It serves as a resource library for content creation, design, development, and research. The repository contains no traditional code but rather specialized markdown files that function as prompt templates.

## Repository Structure

This is a **documentation-only repository** with no executable code, package.json, or build processes. The structure is organized by use case:

- **`article/`** - Prompts for human-like narrative articles
- **`book/`** - Book layout and typesetting prompts using web technologies
- **`deep_research/`** - Structured research prompt generators
- **`infomation_graphics/`** - HTML infographic generation prompts
- **`project/`** - Project planning and proposal assistants
- **`slides_prompts/`** - Interactive presentation generation (including data-driven SPA slides)
- **`subtitle-extract/`** - SRT subtitle format conversion
- **`vibe_coding/`** - Development framework and structure rules
- **`website/`** - Complete frontend code generation for various site types
- **`agent-rule/`** - AI assistant behavior rules and configurations

## Key Files and Conventions

### GEMINI.md
Contains specific instructions for AI assistants, including:
- Commit message generation rules (output to `COMMIT.tmp`)
- Language conventions (primarily Traditional Chinese Taiwan)
- Prompt usage guidelines

### File Naming Patterns
- Version indicators: `-v01`, `-v02`, `-v03`
- Language codes: `-zhTW` (Traditional Chinese Taiwan), `-en` (English)
- Variants: `-alpha`, `-beta`, `-v3a`, `-v3b`

## Language and Localization

**Primary Language**: Traditional Chinese (Taiwan) - most prompts and documentation are written for Taiwan users
**Secondary Language**: English - some prompts and this CLAUDE.md file

## Working with This Repository

### No Build/Test Commands
This repository contains no package.json, dependencies, or executable code. There are no build, test, or lint commands to run.

### Git Commit Message Generation
When generating commit messages:
- Only create messages for files the user has already staged
- Include commit emoji and write as plain text
- Output to `COMMIT.tmp` file (already in .gitignore)
- Do not stage files automatically
- Do not perform automated commits

### Prompt Development Workflow
1. Identify the appropriate category directory
2. Create or modify `.md` files with structured prompt templates
3. Follow existing naming conventions
4. Ensure Traditional Chinese localization for Taiwan users
5. Include version numbers for iterative improvements

### Architecture Understanding
The prompts are designed with these principles:
- **Modularity**: Clear, organized sections for easy customization
- **Data-driven approach**: Separation of content from presentation (especially in v3 slides)
- **Modern web integration**: Heavy use of HTML/CSS/JS with libraries like anime.js, Chart.js
- **Responsive design**: Mobile-first approach with RWD principles
- **Accessibility**: WCAG compliance considerations

## Special Features

### Advanced Slide Generation
The `slides_prompts/graphics-record-slides-v03.md` implements a sophisticated data-driven approach:
- JSON-structured input data
- Separation of content from presentation
- Dynamic flow chart generation with anime.js
- Progressive disclosure with auto-play and manual modes

### Large Codebase Analysis
The `vibe_coding/cluade_code_instruction-v01.md` provides guidance for analyzing large codebases using Gemini CLI with `@` syntax for file inclusion.

## Contributing Guidelines

When modifying prompts:
- Maintain the structured format and clear section divisions
- Preserve Traditional Chinese Taiwan language standards
- Include practical examples and use cases
- Follow the established versioning scheme
- Test prompts with target AI platforms (Gemini, ChatGPT, Claude)