# Story 1.2: Sticky Glassmorphic Header & System Status Telemetry

Status: ready-for-dev

<!-- Note: Validation is optional. Run validate-create-story for quality check before dev-story. -->

## Story

As a Builder or Client,
I want a persistent, glassmorphic sticky header containing primary site links, a theme toggle, and a dynamic system status badge,
so that I can navigate the site easily and see the dynamic status of the operations center at a glance.

## Acceptance Criteria

1. **Given** the visitor scrolls down the page
2. **When** scrolling past the header threshold
3. **Then** the header must remain stickied to the top viewport with a glassmorphic background blur (`backdrop-filter: blur(12px)`) and semi-transparent dark background (`rgba(10, 10, 10, 0.8)`)
4. **And** it must display the company logo brand mark (using the custom SVG logo asset, scaled to a max height of `32px`) next to the company name, replacing any default Astro logo
5. **And** it must display navigation links for *Ventures*, *Technology*, and *About*, showing a distinct active state blue outline (`outline: 2px solid #29B6F6`, `outline-offset: 4px`) when focused via keyboard
6. **And** it must feature a dynamic telemetry badge containing the text `SYS_STATUS: ACTIVE` in `JetBrains Mono` font, with a pulsing green indicator dot (pulsing between opacity 0.4 and 1.0 using pure CSS keyframes)

## Tasks / Subtasks

- [ ] Task 1: Style the Header in Layout.astro (AC: 1, 2, 3)
  - [ ] Add header element with standard properties: sticky top position, glassmorphic background (`backdrop-filter: blur(12px)`), dark background opacity, and standard height
  - [ ] Configure header container boundaries with appropriate max width and responsive paddings
- [ ] Task 2: Implement Branding & Navigation (AC: 4, 5)
  - [ ] Import and place the custom brand mark SVG component with high-fidelity scaling logic
  - [ ] Implement focus styling (`outline: 2px solid #29B6F6`, `outline-offset: 4px`) on header links (*Ventures*, *Technology*, *About*) and theme toggle
- [ ] Task 3: Build Telemetry Badge (AC: 6)
  - [ ] Add badge container with monospaced `SYS_STATUS: ACTIVE` text in JetBrains Mono font
  - [ ] Animate status circle using pure CSS animation keyframes to create a soft, non-intrusive glow pulse

## Dev Notes

- **Astro Integration**: The header sits in the main `Layout.astro` file to wrap all page routes.
- **Glassmorphic Filter**: Support fallback rules for older browsers that do not support backdrop filter.
- **Micro-Animations**: All indicators must use zero-JS CSS stroke/glow keyframes to maintain Lighthouse target performance.

### Project Structure Notes

- Header design is defined inside `astro/src/layouts/Layout.astro`.
- Brand logo rendering utilizes `astro/src/components/Logo.astro`.

### References

- [Source: _bmad-output/planning-artifacts/prd.md#MVP---Minimum-Viable-Product-(Phase-1)]
- [Source: _bmad-output/planning-artifacts/ux-design-specification.md#3.-Logo.astro]
- [Source: _bmad-output/planning-artifacts/epics.md#Story-1.2]

## Dev Agent Record

### Agent Model Used

Google DeepMind Antigravity

### Debug Log References

### Completion Notes List

### File List
