# Story 1.4: Dynamic Footnotes & Footer Links

Status: ready-for-dev

<!-- Note: Validation is optional. Run validate-create-story for quality check before dev-story. -->

## Story

As a Visitor,
I want to see navigation links in the footer,
so that I can access auxiliary company protocols and compliance information.

## Acceptance Criteria

1. **Given** the user scrolls to the bottom of the page
2. **When** they inspect the footer
3. **Then** the footer must render a top grid border line (`#262626`) and feature links for Regional Operations, Technical Docs, Privacy Protocol, and Terms of Orchestration
4. **And** these links must render in monospaced uppercase typography (`JetBrains Mono`)

## Tasks / Subtasks

- [ ] Task 1: Setup layout structure in index.astro footer (AC: 1, 2)
  - [ ] Add standard footer element with border-top `#262626` and appropriate spacing/padding
  - [ ] Align content using flexbox/grid for desktop and mobile centering fallbacks
- [ ] Task 2: Configure compliance links and typography (AC: 3, 4)
  - [ ] Place links: REGIONAL_OPERATIONS, TECHNICAL_DOCS, PRIVACY_PROTOCOL, TERMS_OF_ORCHESTRATION
  - [ ] Apply uppercase monospace formatting using `JetBrains Mono` font
  - [ ] Configure keyboard focus outlines on the compliance link tags

## Dev Notes

- **Astro Component Setup**: Footer is declared directly in `index.astro` or extracted as a component. Ensure all links are accessible via keyboard tab sequence.
- **Branding Assets**: Standard footer must feature the custom company logo and copyright info, ensuring no physical coordinates or heartbeats are printed.

### Project Structure Notes

- Footer is located at the bottom of `astro/src/pages/index.astro`.
- Company logo utilizes `astro/src/components/Logo.astro`.

### References

- [Source: _bmad-output/planning-artifacts/prd.md#MVP---Minimum-Viable-Product-(Phase-1)]
- [Source: _bmad-output/planning-artifacts/ux-design-specification.md#4.-Footer-Specifications]
- [Source: _bmad-output/planning-artifacts/epics.md#Story-1.4]

## Dev Agent Record

### Agent Model Used

Google DeepMind Antigravity

### Debug Log References

### Completion Notes List

### File List
