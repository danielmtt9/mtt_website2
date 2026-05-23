# Story 1.1: Design Token CSS Variables, Layout Frame & Favicon

Status: ready-for-dev

<!-- Note: Validation is optional. Run validate-create-story for quality check before dev-story. -->

## Story

As a Visitor,
I want the site to render in a dark-mode-first premium tech layout with proper typography, brand identity, and favicon,
so that I can immediately experience Maple Tyne's engineering brand identity with zero layout shift.

## Acceptance Criteria

1. **Given** the visitor opens the landing page in their browser
2. **When** the document loads
3. **Then** the background must render in deep tech dark (`#0A0A0A`), body copy must render in Outfit (`#F5F5F5`), and headings/titles must render in Fraunces, achieving a color contrast ratio of $> 4.5:1$
4. **And** the monospace elements and telemetry tags must render in JetBrains Mono (`#29B6F6`)
5. **And** the theme configuration must be read from `localStorage` (defaulting to dark theme) via an inline blocking script in `Layout.astro` to prevent flashes of light background
6. **And** the browser favicon must be configured in `Layout.astro` to use the custom Maple Tyne logo asset instead of any default Astro branding

## Tasks / Subtasks

- [ ] Task 1: Initialize design tokens in global.css (AC: 3, 4)
  - [ ] Define colors: background (`#0A0A0A`), card BG (`#141414`), border (`#262626`), success (`#66BB6A`), info (`#29B6F6`), alert (`#FFB74D`), high-contrast white (`#F5F5F5`)
  - [ ] Configure font-families for `Fraunces` (titles), `Outfit` (body), and `JetBrains Mono` (telemetry/monospaced)
  - [ ] Assert color contrast ratios conform to WCAG 2.1 Level AA ($> 4.5:1$)
- [ ] Task 2: Configure Layout Frame & Brand Assets in Layout.astro (AC: 5, 6)
  - [ ] Add an inline, blocking script in Layout.astro to retrieve theme preference from `localStorage` and set it on the document root before content rendering to avoid light-mode flashing
  - [ ] Configure browser favicon meta tags to load the custom SVG/favicon branding
  - [ ] Establish high-visibility electric blue focus rings (`outline: 2px solid #29B6F6; outline-offset: 4px;`) on all focusable targets

## Dev Notes

- **Astro SSG (ADR 01)**: The layout is statically generated. Ensure the theme-detection script is inline and blocks rendering so the document compiles and loads without visual layout shift (CLS).
- **CSS Variable Definitions**: Utilize variables in `global.css` for background, text, borders, and accents to support component styling consistency.
- **Focus Rings**: Universal style rules for keyboard focus must be declared globally.

### Project Structure Notes

- Global style variables reside in `astro/src/styles/global.css`.
- The main HTML frame and wrapper reside in `astro/src/layouts/Layout.astro`.
- Favicon asset should be verified in `astro/public/`.

### References

- [Source: _bmad-output/planning-artifacts/prd.md#Project-Type-Overview]
- [Source: _bmad-output/planning-artifacts/architecture.md#ADR-02:-Scoped-Styling-&-Design-Token-System]
- [Source: _bmad-output/planning-artifacts/epics.md#Story-1.1]

## Dev Agent Record

### Agent Model Used

Google DeepMind Antigravity

### Debug Log References

### Completion Notes List

### File List
