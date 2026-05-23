# Story 1.3: Responsive Bento Grid Layout Framework

Status: ready-for-dev

<!-- Note: Validation is optional. Run validate-create-story for quality check before dev-story. -->

## Story

As a Visitor,
I want to view Maple Tyne's venture studio portfolio organized in a responsive tactile grid,
so that I can interactively explore distinct venture capabilities and redirect to external apps easily.

## Acceptance Criteria

1. **Given** the visitor is browsing on different devices
2. **When** the screen size changes
3. **Then** the Bento Grid must adjust layout rules: 12-column grid on desktop viewports ($\ge 1024px$), 6-column grid on tablet viewports ($768px - 1023px$), and collapse to a single-column vertical stack on mobile viewports ($< 768px$)
4. **And** each card container (`.tactile-card`) must render with corner radii of `12px` and a grid border (`#262626`), lifting upward and shifting border color to the brand accent green (`#66BB6A`) on cursor hover
5. **And** the portfolio showcase cards must include *Invoice Generator* (Active Micro-SaaS card spanning 4 columns) and *EcoAudit Canada* (Venture card spanning 12 columns at the bottom to balance the grid layout)

## Tasks / Subtasks

- [ ] Task 1: Setup Bento Grid layout in BentoGrid.astro and index.astro (AC: 1, 2, 3)
  - [ ] Implement desktop layout with CSS Grid layout system: grid template columns of `repeat(12, minmax(0, 1fr))`
  - [ ] Configure media queries for tablet viewports (`max-width: 1023px`) to fall back to a 6-column layout
  - [ ] Configure mobile viewports (`max-width: 767px`) to collapse to a single-column vertical stack
- [ ] Task 2: Implement tactile-card hover and focus states (AC: 4)
  - [ ] Set default card properties: background color `#141414`, borders `#262626`, border-radius `12px`, and hardware-accelerated transitions
  - [ ] Configure hover state behaviors: shift card upward via transform `translateY(-4px)` and change border color to success green `#66BB6A`
- [ ] Task 3: Align and balance venture portfolio cards (AC: 5)
  - [ ] Verify `CardInvoice` spans 4 columns on desktop
  - [ ] Verify `CardVenture` (EcoAudit) spans 12 columns on desktop to balance the bottom of the grid

## Dev Notes

- **CSS Grid Layout**: Standard Bento Card dimensions are:
  - `CardHero` (V2H Arbitrage): Span 8, row span 2 on desktop.
  - `CardSolarROI`: Span 4, row span 1 on desktop.
  - `CardInvoice`: Span 4, row span 1 on desktop.
  - `CardVenture` (EcoAudit): Span 12, row span 1 on desktop.
- **Micro-interactions**: Transition modifications must be optimized using CSS transitions to prevent visual stuttering and guarantee a PageSpeed score of $\ge 90$.

### Project Structure Notes

- Bento grid frame resides in `astro/src/components/BentoGrid.astro` and `astro/src/pages/index.astro`.
- Venture and Invoice cards are in `astro/src/components/CardVenture.astro` and `astro/src/components/CardInvoice.astro`.

### References

- [Source: _bmad-output/planning-artifacts/prd.md#Responsive-Design-&-Bento-Grid]
- [Source: _bmad-output/planning-artifacts/ux-design-specification.md#Responsive-Grid-System-(Bento-Grid)]
- [Source: _bmad-output/planning-artifacts/epics.md#Story-1.3]

## Dev Agent Record

### Agent Model Used

Google DeepMind Antigravity

### Debug Log References

### Completion Notes List

### File List
