# Story 3.1: Interactive Solar ROI Calculator Widget

Status: ready-for-dev

<!-- Note: Validation is optional. Run validate-create-story for quality check before dev-story. -->

## Story

As a Homeowner,
I want to interactively calculate regional solar yield and return on investment in real time by entering solar panel size inputs,
so that I can evaluate the financial viability of installing solar panels on my property.

## Acceptance Criteria

1. **Given** the user is viewing the Solar ROI Calculator card
2. **When** they enter or change the solar panel system size (e.g., using a touch-optimized slider or input field with a minimum touch target size of `48px x 48px`)
3. **Then** the widget must dynamically compute and display the estimated regional solar yield (kWh/year) and ROI (years) in real time without refreshing the page
4. **And** the output calculations must update instantly (within 50ms), rendering in high contrast `Outfit` and `JetBrains Mono` typography
5. **And** the math formulas must utilize Ontarian region coefficients (average 1,150 kWh/kW annual yield) and net-metering accumulation logic (surplus generation credited to reduce utility consumption)

## Tasks / Subtasks

- [ ] Task 1: Design touch-friendly slider controls in CardSolarROI.astro (AC: 1, 2)
  - [ ] Add sliders for system size (kW) and utility electricity rates (CAD/kWh)
  - [ ] Style the range inputs ensuring the touch target height is $\ge 48\text{px}$ on mobile layouts (NFR-A1/NFR-A3)
- [ ] Task 2: Implement dynamic math calculation script (AC: 3, 5)
  - [ ] Implement Ontario yield conversion formula: $E_{\text{annual}} = S \times 1150$
  - [ ] Implement payback period math logic: $P = 2800 / (1150 \times R)$ where $R$ is electricity rate input (derived from constant ratio $2.4348 / R$)
- [ ] Task 3: Bind updates to DOM elements instantly (AC: 4)
  - [ ] Attach listeners for input updates and direct DOM modifications to output fields
  - [ ] Measure rendering times to guarantee calculations resolve in $<50\text{ms}$ (NFR-P3)

## Dev Notes

- **Performance targets**: Keep math and DOM bindings lightweight and isolated. Do not load external visualization packages.
- **Regulatory alignment**: Add explicit text disclaimers indicating calculations are region-based estimates for Ontario net-metering structures and not professional audits.

### Project Structure Notes

- ROI calculator logic is inside `astro/src/components/CardSolarROI.astro`.
- Disclaimers utilize styling from local component templates.

### References

- [Source: _bmad-output/planning-artifacts/prd.md#3.-Solar-ROI-Calculator]
- [Source: _bmad-output/planning-artifacts/architecture.md#ADR-04:-Solar-ROI-Mathematical-Formulas-&-Regional-Constants]
- [Source: _bmad-output/planning-artifacts/epics.md#Story-3.1]

## Dev Agent Record

### Agent Model Used

Google DeepMind Antigravity

### Debug Log References

### Completion Notes List

### File List
