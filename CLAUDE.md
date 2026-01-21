# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Kapwa Labs is a static marketing website for a fractional CTO consulting business. Deployed via GitHub Pages.

## Local Development

Open `index.html` directly in a browser. No build step or dependencies required.

## Architecture

- **index.html** - Main production page (single-file site with inline CSS and JS)
- **kapwa.html** - Alternate/draft version of the site
- **SVG assets** - Brand asterisk logo in three color variants (orange, black, white)

## Design System

CSS variables defined in `:root`:
- `--color-bg: #F5F6F2` (light sage background)
- `--color-sage: #C5C9B8` (accent sections)
- `--color-accent: #F7931E` (orange brand color)
- `--color-dark: #1a1a1a` (text and dark sections)
- `--font-main: 'Helvetica Neue', Helvetica, Arial, sans-serif`

The Kapwa asterisk logo is implemented as inline SVG throughout the site for flexibility with colors and animations.
