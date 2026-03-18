# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Instagram caption formatter for the **SG_threelittlepigs** food review account. It generates styled captions with Unicode fonts, pig emoji ratings, dish details, and sign-off templates. Users fill in a form and copy the formatted caption to their clipboard.

## Architecture

This is a **single-file static web app** — all HTML, CSS, and JavaScript live in `SG_threelittlepigs Caption Formatter.html`. There is no build system, no package manager, and no dependencies beyond Google Fonts (DM Sans, DM Serif Display).

Key sections of the HTML file:
- **Lines 1–400**: HTML structure and `<style>` block (CSS variables, responsive layout, component styles)
- **Lines 400–500**: `<script>` setup — font options array, sign-off templates array, emoji constant, and state variables
- **Lines 500–675**: Core JavaScript functions — Unicode font converters (`toBold`, `toBoldItalic`, `toScript`, `toDouble`), dish CRUD, live preview rendering (`render()`), and clipboard copy

The `render()` function is the central data flow — every input change calls it, and it rebuilds the caption string from current state and writes it to the preview panel.

## Deployment

Hosted on **Vercel** as a static site (`vercel.json` routes all requests to `index.html`).

**Note:** `vercel.json` references `index.html`, but the actual file is named `SG_threelittlepigs Caption Formatter.html`. The file may need to be renamed or the config updated for deployment to work.

## Development

Open the HTML file directly in a browser — no server or build step required. Edit the file and refresh to see changes.
