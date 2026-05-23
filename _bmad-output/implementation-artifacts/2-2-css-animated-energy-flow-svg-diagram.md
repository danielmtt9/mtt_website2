# Story 2.2: CSS-Animated Energy Flow SVG Diagram

Status: ready-for-dev

<!-- Note: Validation is optional. Run validate-create-story for quality check before dev-story. -->

## Story

As a Homeowner,
I want to see a real-time animated SVG flow diagram mapping current flowing paths between Solar, EV Battery, Home, and Grid,
so that I can visually trace power sourcing cycles (e.g., Grid to Battery vs Battery to Home).

## Acceptance Criteria

1. **Given** the user is viewing the V2H Arbitrage Visualizer card
2. **When** the page renders
3. **Then** the system must display an inline responsive SVG diagram connecting four node markers: Solar, EV Battery, Home, and Grid
4. **And** the connection vectors (lines/curves) must animate using CSS `stroke-dashoffset` keyframes to represent active flow directions (e.g. dashed strokes moving from Battery to Home) with zero external JS animation libraries (complying with `AR3`)
5. **And** the SVG must be fully accessible and scalable, resizing smoothly across desktop, tablet, and mobile grid cells without clipping or distortion

## Tasks / Subtasks

- [ ] Task 1: Construct SVG nodes and path connections in ArbitrageFlow.astro (AC: 1, 2, 3)
  - [ ] Add the inline SVG structure defining standard viewport size and coordinates
  - [ ] Draw the four node circles (Solar, EV Battery, Home, Grid) with corresponding icon tags and high-contrast labels
  - [ ] Construct path vectors connecting the nodes (e.g., Grid to EV, EV to Home)
- [ ] Task 2: Implement zero-JS CSS animations on paths (AC: 4)
  - [ ] Define dashed stroke styling on the SVG path vectors using `stroke-dasharray`
  - [ ] Implement keyframe animations using `stroke-dashoffset` loops to simulate energy movement directionally
- [ ] Task 3: Ensure SVG responsiveness and scaling (AC: 5)
  - [ ] Apply layout parameters: `viewBox` coordinates and fluid CSS scaling to prevent distortion across bento column changes

## Dev Notes

- **Zero-JS Requirement**: Animations must run entirely on the CSS animation thread (using standard properties like `animation: dash 2s linear infinite`). Never call Javascript canvas/draw routines.
- **Accessibility**: Provide an explicit `aria-label` or link the SVG to a screen-reader summary table (`.sr-only` class) detailing current energy transfers.

### Project Structure Notes

- Inline SVG components reside in `astro/src/components/ArbitrageFlow.astro`.
- Integrated directly within `CardHero.astro`.

### References

- [Source: _bmad-output/planning-artifacts/prd.md#MVP---Minimum-Viable-Product-(Phase-1)]
- [Source: _bmad-output/planning-artifacts/ux-design-specification.md#3.-<ArbitrageFlow-/>]
- [Source: _bmad-output/planning-artifacts/epics.md#Story-2.2]

## Dev Agent Record

### Agent Model Used

Google DeepMind Antigravity

### Debug Log References

### Completion Notes List

### File List
