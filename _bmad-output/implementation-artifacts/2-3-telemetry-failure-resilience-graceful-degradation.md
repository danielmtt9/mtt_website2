# Story 2.3: Telemetry Failure Resilience & Graceful Degradation

Status: ready-for-dev

<!-- Note: Validation is optional. Run validate-create-story for quality check before dev-story. -->

## Story

As a Homeowner or Energy Auditor,
I want the V2H Arbitrage visualizer to detect when external telemetry API data fetches fail or timeout,
so that the affected card gracefully degrades to an isolated fallback UI without freezing or breaking other interactive components on the page.

## Acceptance Criteria

1. **Given** the visitor opens the page
2. **When** the external telemetry API fetch fails or times out
3. **Then** the V2H Arbitrage card status badge must update from `V2H_ACTIVE` (green pulsing) to `CONFIG REQUIRED` (amber warning badge)
4. **And** the telemetry metrics panel must hide and a fallback panel containing `SYSTEM_FAULT: NO_DATA // RUN DIAGNOSTICS` must be displayed in a high-contrast amber/red warning layout
5. **And** the user must be able to click the `[RUN_DIAGNOSTICS]` button to initiate a diagnostic run, showing a monospace text spinner (`\`, `|`, `/`, `-`) for 1.5 seconds, then restoring/toggling the simulated live data to allow verification of both states
6. **And** all other interactive components (such as the Solar ROI Calculator sliders and links) must remain fully interactive and functional (complying with NFR-R1 and NFR-R2)

## Tasks / Subtasks

- [ ] Task 1: Implement telemetry data fetch and timeout handling (AC: 1, 2)
  - [ ] Implement query loop to `/api/telemetry-data-does-not-exist`
  - [ ] Set up fetch error handling block to intercept failures and a 3-second timeout logic
- [ ] Task 2: Configure UI fallback layout transition (AC: 3, 4)
  - [ ] Add `.degraded-panel` container styled in high contrast warning format, displaying `SYSTEM_FAULT: NO_DATA // RUN DIAGNOSTICS`
  - [ ] Implement class toggling: hide the telemetry container class and expose the degraded panel on catch
  - [ ] Update the status badge class to `.amber` and change the inner text to `CONFIG REQUIRED`
- [ ] Task 3: Build diagnostic recovery simulation (AC: 5, 6)
  - [ ] Add event listener to `[RUN_DIAGNOSTICS]` trigger button
  - [ ] Run interval loop displaying monospace text spinner `\`, `|`, `/`, `-` for 1.5 seconds
  - [ ] Toggle back and forth between active metrics and degraded layouts to support complete verification testing
  - [ ] Ensure all exceptions are contained within the `initTelemetry()` execution scope to prevent page halts

## Dev Notes

- **Isolated Failures (NFR-R1)**: JavaScript errors from the fetch call must not propagate to the main window thread. Use standard `try-catch` structures inside local modules.
- **Diagnostics Verification**: Toggling between mock states on click lets users test both active V2H telemetry and config warnings easily.

### Project Structure Notes

- Error boundaries and fetch routines are inside the script tag of `astro/src/components/CardHero.astro`.
- Styling for warning layouts is declared in local `<style>` of `CardHero.astro`.

### References

- [Source: _bmad-output/planning-artifacts/prd.md#4.-Telemetry-Graceful-Degradation-&-Resilience]
- [Source: _bmad-output/planning-artifacts/architecture.md#ADR-05:-Isolated-Fault-Containment]
- [Source: _bmad-output/planning-artifacts/epics.md#Story-2.3]

## Dev Agent Record

### Agent Model Used

Google DeepMind Antigravity

### Debug Log References

### Completion Notes List

### File List
