# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static landing page for **BLOB Paris** (Bureau Laboratoire en Olfaction et Bien-être), a French perfumery company founded by Delphine Jacquemart. No build system, no dependencies, no package manager — just HTML, CSS, and inline JS.

## Structure

- `index.html` — single-page site with a two-column layout: full-height video on the left (75%), info sidebar on the right (25%)
- `style.css` — all styles, including responsive breakpoints for mobile portrait and landscape
- `blob.mp4` / `blob.mov` — background video (autoplay, muted, looping)
- `logo_blob.png` / `blob.png` — logo and brand image assets
- `piscine.mp4` — additional video asset

## Layout Architecture

The page uses a flex row layout (`.layout`): a video panel (`.video-panel`) and a sidebar (`.sidebar`). The sidebar contains the logo, company title (`h1`), and a `<nav>` with three native `<details>`/`<summary>` accordion sections: Services, À propos, and Contact.

Sound toggle is handled by inline JS — clicking anywhere on `.video-panel` mutes/unmutes the video and swaps the Font Awesome icon. Font Awesome 6.5 is loaded from cdnjs.

Responsive behavior:
- Mobile portrait (`≤768px, portrait`): stacks video above sidebar, page scrolls normally
- Mobile landscape (`≤500px height, landscape`): keeps side-by-side layout, sidebar scrolls independently

## Development

Open `index.html` directly in a browser — no server required. To preview with a local server:

```bash
python3 -m http.server 8080
```
