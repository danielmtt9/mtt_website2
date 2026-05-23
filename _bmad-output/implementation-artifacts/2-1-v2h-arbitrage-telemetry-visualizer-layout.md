# Story 2.1: V2H Arbitrage Telemetry & Visualizer Layout

Status: ready-for-dev

<!-- Note: Validation is optional. Run validate-create-story for quality check before dev-story. -->

## Story

As a Homeowner or Energy Auditor,
I want to view V2H arbitrage calculations and EV battery protection metrics in a structured telemetry table card,
so that I can evaluate utility rate optimization (ULO) spreads and battery health at a glance.

## Acceptance Criteria

1. **Given** the user is viewing the V2H Arbitrage Visualizer card in the Bento grid
2. **When** they read the metrics
3. **Then** the card must display the grid rate (e.g. `35.2¢/kWh`), battery state of charge (e.g. `82%`), and EV battery health (e.g. `98%`) in high contrast `JetBrains Mono` text (`#F5F5F5` on `#141414`)
4. **And** it must display dynamic visual badges for rate tier levels (e.g. `ULO PEAK` in alert amber `#FFB74D` or `ULO OFF-PEAK` in success green `#66BB6A`) with ambient pulsing glow indicators
5. **And** the card container must support the hardware-accelerated 3D mouse tilt interaction on desktop viewports ($\ge 1024px$) matching `UX-DR4` (`perspective(1000px)` transform rotation bound to cursor coordinates `--x` and `--y`), which must be disabled on tablet/mobile touch screens

## Tasks / Subtasks

- [ ] Task 1: Design layout and metrics display in CardHero.astro (AC: 1, 2, 3)
  - [ ] Structure the telemetry grid using `JetBrains Mono` typography
  - [ ] Add specific tags and text for `GRID_RATE` (e.g. `35.2¢/kWh`), `BATTERY_SOC` (e.g. `82%`), and `BATTERY_SOH` (e.g. `98%`)
- [ ] Task 2: Configure utility rate badges and glow animations (AC: 4)
  - [ ] Implement rate badges for ULO pricing tiers (e.g., ULO PEAK in `#FFB74D` and ULO OFF-PEAK in `#66BB6A`)
  - [ ] Set up soft CSS drop shadow glow animation keyframes (`@keyframes pulse`) around the badges
- [ ] Task 3: Implement 3D card tilt animation (AC: 5)
  - [ ] Add mouse event listeners to track the cursor's coordinates relative to the card container
  - [ ] Compute rotational angles using perspective matrix transforms (`perspective(1000px) rotateX(...) rotateY(...)`)
  - [ ] Wrap listeners in a media query check (`window.matchMedia("(hover: hover)")`) to automatically disable tilt transforms on touch viewports

## Dev Notes

- **Astro Integration**: The component is declared in `CardHero.astro`.
- **Performance Bounds**: The 3D tilt calculation runs on `requestAnimationFrame` or simple mousemove bounds, and must be hardware-accelerated using standard CSS transforms (`will-change: transform`) to prevent screen lag (NFR-P4).
- **Accessibility**: Verify contrast ratios of telemetry labels against card BG exceed $4.5:1$.

### Project Structure Notes

- V2H card layout resides in `astro/src/components/CardHero.astro`.
- Base style variables are imported from `astro/src/styles/global.css`.

### References

- [Source: _bmad-output/planning-artifacts/prd.md#2.-Vehicle-to-Home-(V2H)-Arbitrage-Visualizer]
- [Source: _bmad-output/planning-artifacts/architecture.md#ADR-03:-V2H-Telemetry-Interface-&-Data-Schema]
- [Source: _bmad-output/planning-artifacts/epics.md#Story-2.1]

## Dev Agent Record

### Agent Model Used

Google DeepMind Antigravity

### Debug Log References

### Completion Notes List

### File List
