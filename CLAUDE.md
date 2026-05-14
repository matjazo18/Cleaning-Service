# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static marketing website for CleanLine Ljubljana, a Slovenian cleaning company. No build process, no package manager, no dependencies — open `index.html` directly in a browser to develop.

## Architecture

**Everything lives in `index.html`** (~1546 lines):
- Lines 12–973: embedded `<style>` block (all CSS)
- Lines 974–1498: HTML markup
- Lines 1499–1544: embedded `<script>` block (all JS)

`styles.css` exists in the repo but is **unused** — do not write styles there.

The site is a single-page scroll with anchor-based navigation. Sections, in order: `.nav` → `.hero` → `#storitve` (services) → `#zakaj` (why us) → `#postopek` (process) → `#reference` (results/testimonials) → `#faq` → `#kontakt` (contact form) → `.footer`.

## Design System

CSS custom properties are declared at `:root` inside the embedded `<style>` block. Brand palette: Navy (#0B1433–#172658), Cyan (#39D6E8), Gold. Typography: Manrope (sans-serif body), Fraunces (serif accent). Max container width: 1240px. Responsive breakpoints: 980px (tablet), 560px (mobile).

## JavaScript

Two features only:
1. **Contact form** (`#contact-form`) — intercepts submit and opens a `mailto:cleanlineljubljana@gmail.com` link with the message body.
2. **FAQ accordion** — `requestAnimationFrame`-based height transition for smooth expand/collapse.

## Content Language

All user-visible text is in **Slovenian**. Keep new copy in Slovenian to match.
