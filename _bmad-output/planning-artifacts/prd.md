---
stepsCompleted:
  - 'step-01-init'
  - 'step-02-discovery'
  - 'step-02b-vision'
  - 'step-02c-executive-summary'
  - 'step-03-success'
  - 'step-04-journeys'
  - 'step-05-domain'
  - 'step-06-innovation'
  - 'step-07-project-type'
  - 'step-08-scoping'
  - 'step-09-functional'
  - 'step-10-nonfunctional'
  - 'step-11-polish'
releaseMode: 'phased'
inputDocuments:
  - "/home/danielaroko/applications/mtt/_bmad-output/planning-artifacts/ux-design-specification.md"
  - "/home/danielaroko/applications/mtt/_bmad-output/planning-artifacts/epics.md"
  - "/home/danielaroko/applications/mtt/_bmad-output/planning-artifacts/architecture.md"
  - "/home/danielaroko/applications/mtt/_bmad-output/planning-artifacts/implementation-readiness-report-2026-05-22.md"
documentCounts:
  briefCount: 0
  researchCount: 0
  brainstormingCount: 0
  projectDocsCount: 4
classification:
  projectType: 'web_app'
  domain: 'energy'
  complexity: 'high'
  projectContext: 'brownfield'
workflowType: 'prd'
---

# Product Requirements Document - mtt

**Author:** Danielaroko
**Date:** 2026-05-22

## Executive Summary

Maple Tyne Technologies operates as a premier Tech Venture Studio and Engineering Firm specializing in high-utility, automated orchestration. The primary vision of **mtt** is to establish absolute trust and credibility with venture partners and homeowners by showcasing real-time, zero-setup AI-native energy management. The target users are Energy Autonomists (homeowners seeking automated solar and stationary battery optimization) and prospective Venture Partners. The platform solves the complexity of energy arbitrage and solar return estimations by translating high-density technical telemetry into intuitive, immediate visual data without requiring account sign-up or cognitive overhead.

### What Makes This Special

mtt differentiates itself through a high-fidelity, performance-optimized Bento Grid landing hub that combines consumer utility with engineering transparency. While traditional energy visualizers rely on heavy client-side JavaScript or generic descriptions, mtt leverages Zero-JS CSS stroke path animations on inline SVGs to map active electricity flows between grid, solar, home, and battery nodes. Furthermore, rather than exposing developer-facing configuration components (such as webhook consoles or raw tech stacks) which clutter the consumer narrative, the website provides immediate, actionable user utility via a touch-friendly, client-side Solar ROI calculator. Core system credibility is maintained using ambient pulsing telemetry statuses showing real-time grid rates, state-of-charge (SoC), and battery health metrics.

## Project Classification

*   **Project Type:** Web Application (statically compiled Astro components using scoped Vanilla CSS)
*   **Domain:** Energy / Utility (high-utility fintech calculations)
*   **Complexity Level:** High
*   **Project Context:** Brownfield (optimizing and refactoring an existing Astro layout to align with updated branding and user experience constraints)

## Success Criteria

### User Success

*   **Real-time Yield Estimates:** Users calculate solar ROI in real-time using touch-friendly range sliders, obtaining immediate estimates with zero configuration or registration.
*   **Intuitive Arbitrage Visuals:** Users understand Vehicle-to-Home (V2H) charging/discharging loops instantly through clear, CSS-animated inline SVG flow lines.
*   **Accessible Visual Telemetry:** Homeowners verify battery health and SoC status indicators at a glance without reading raw terminal logs.

### Business Success

*   **Venture Trust Building:** Present Maple Tyne Technologies as a highly capable engineering studio by showcasing working, responsive consumer utilities.
*   **Brand Clarification:** Eliminate developer-facing settings (like webhook console diagnostics and tech stack details) from the public site to keep the primary brand narrative focused on clean energy orchestration.
*   **Engagement Rate:** Achieve a 25% increase in interactive sessions via the inline Solar ROI Calculator.

### Technical Success

*   **Performance Bounds:** Maintain a Google PageSpeed score of >= 90 on both desktop and mobile viewports by compiling static pages and avoiding heavy JS/CSS frameworks.
*   **Layout Compliance:** Implement a 12-column responsive Bento Grid layout that degrades cleanly to 6 columns on tablet and 1 column on mobile without layout breaks or text overlaps.
*   **Accessibility Standards:** Achieve WCAG 2.1 Level AA compliance, featuring high-contrast colors and an electric blue keyboard focus outline (`outline: 2px solid #29B6F6`, `outline-offset: 4px`) on all focusable targets.
*   **Failure Isolation:** Ensure telemetry data failures degrade gracefully, swapping only the affected card's contents to a static fallback (`NO_DATA // RUN DIAGNOSTICS`) without blocking other bento elements.

### Measurable Outcomes

*   **Input Latency:** Real-time components update calculations within 50ms of a slider or text input modification.
*   **Touch Targets:** All buttons and slider controls maintain a touch target size of `>= 48px` on mobile screens.

## Product Scope

### MVP - Minimum Viable Product (Phase 1)

*   **Core Bento Grid Layout:** A responsive 12-column Bento Grid structure using scoped Vanilla CSS.
*   **Glassmorphic Sticky Header:** A translucent top bar featuring active underlines, custom Maple Tyne brand logo, and a pulsing status indicator (`SYS_STATUS: ACTIVE`).
*   **V2H Arbitrage Visualizer:** A flagship telemetry card featuring SoC metrics, ULO peak badges, desktop-only 3D cursor tilt transformations, and a mock diagnostic error fallback.
*   **Arbitrage CSS Flow SVG:** An inline SVG diagram animating energy directions between Grid, Solar, Home, and EV Battery using pure CSS dash-offset animations.
*   **Solar ROI Calculator:** An interactive card with custom-styled range sliders and inline calculation logic for yield, savings, and payback period.
*   **Cleaned Footer:** Contains uppercase monospaced compliance links and a copyright notice. No coordinates, heartbeats, or build versions.
*   **Auxiliary Showcase Cards:** Showcase cells for *Invoice Generator* and *EcoAudit Canada*.

### Growth Features (Phase 2 - Post-MVP)

*   **Real API Polling:** Connecting the V2H card telemetry fields to live Ontario utility rates and home battery API feeds.
*   **Tariff Selector:** Expanding the Solar ROI Calculator to support selecting between Ontario TOU (Time of Use) and ULO (Ultra-Low Overnight) structures.
*   **Interactive Invoice Card:** Transforming the *Invoice Generator* card into a functional micro-billing widget.

### Vision (Phase 3 - Future)

*   **EcoAudit Platform Launch:** Launching *EcoAudit Canada* as a full, dedicated SaaS platform linked from the Bento grid.
*   **Smart Automation Dispatch:** Automatic charging execution based on machine learning price predictions.

## User Journeys

### 1. Primary User - Success Path (Sarah, Suburban Energy Manager)

*   **Persona Profile:** Sarah is a homeowner in Ontario who recently installed a solar rooftop system and wants to maximize savings using Time-of-Use (TOU) or Ultra-Low Overnight (ULO) rates. She has minimal technical background but is highly motivated by cost savings and reducing carbon footprint.
*   **Opening Scene:** Sarah arrives at the Maple Tyne website on her mobile phone after searching for clean energy optimization tools. She is looking for an interactive tool to estimate solar payback periods.
*   **Rising Action:** The page loads in under 150ms. She instantly spots the glowing green `SYS_STATUS: ACTIVE` indicator in the header, assuring her the platform is live. She scrolls down to the **Solar ROI Calculator** card and adjusts the system size slider to `7.5 kW` and the utility rate slider. The estimated annual yield and payback period update immediately as she slides, with no lagging or reloading.
*   **Climax:** Sarah looks at the **V2H Arbitrage Visualizer** card. She sees an animated, smooth diagram showing energy paths pulsing between Solar, EV Battery, Home, and Grid. She watches the line representing the EV battery flow back into the Home, illustrating exactly how "arbitrage" works during peak hours.
*   **Resolution:** Without registering, Sarah gains a clear understanding of solar returns and battery flow. She clicks the "Venture" link in the header, which smoothly scrolls or navigates, leaving her feeling empowered and confident in Maple Tyne's technology.

### 2. Primary User - Edge Case (Sarah, Offline / Degraded State)

*   **Opening Scene:** Sarah returns to the site while traveling in an area with poor cellular connection.
*   **Rising Action:** The static HTML loads successfully due to the lack of heavy framework JS. However, the external API server that feeds the live battery SoC and grid rate telemetry to the **V2H Arbitrage Visualizer** fails to respond.
*   **Climax:** Instead of the entire layout crashing or freezing, the V2H Arbitrage card isolates the failure. It displays `NO_DATA // RUN DIAGNOSTICS` in monospaced red/amber text, while the rest of the cards (including the local JS-driven Solar ROI Calculator) remain fully interactive and functional.
*   **Resolution:** Sarah is able to continue playing with the Solar ROI calculator without interruption. The website gracefully degrades rather than presenting a broken white screen, preserving trust.

### 3. Venture Partner - Success Path (Julian, Capital Investment Director)

*   **Persona Profile:** Julian is a venture investor looking for an engineering firm to build a high-volume utility automation platform. He values responsiveness, performance, and attention to detail.
*   **Opening Scene:** Julian is reviewing mtt's portfolio on his high-resolution desktop monitor.
*   **Rising Action:** He hovers his mouse over the **V2H Arbitrage Visualizer** card and notices it tilt dynamically on a 3D axis matching his cursor position. He sees the compliance navigation link in the footer styled in clean `JetBrains Mono` and clicks the focusable elements, noticing the sharp electric blue keyboard outlines.
*   **Climax:** He runs a Google PageSpeed Lighthouse audit on the URL. The page scores `98` on performance because it contains no bloated libraries, relying entirely on static Astro and scoped Vanilla CSS.
*   **Resolution:** Julian is convinced of Maple Tyne's technical excellence and attention to performance/accessibility standards. He contacts them to discuss partnership.

### 4. Technical Auditor - Keyboard Accessibility & Compliance (Marcus, QA Engineer)

*   **Persona Profile:** Marcus is a compliance and accessibility auditor verifying vendor security and layout standards.
*   **Opening Scene:** Marcus accesses the website using only a keyboard to test WCAG 2.1 Level AA compliance.
*   **Rising Action:** He presses `TAB` to move through the header links. He notices a clear, high-contrast focus indicator around the "Ventures", "Technology", and "About" links.
*   **Climax:** He tabs into the interactive range inputs of the Solar ROI Calculator. The sliders receive clear electric blue outlines, and the labels are screen-reader accessible.
*   **Resolution:** Marcus confirms that the UI handles focus states perfectly and complies with contrast requirements, checking off the vendor compliance requirement.

### Journey Requirements Summary

*   **Immediate Local Math:** Client-side JavaScript must handle slider updates locally to guarantee <50ms response times.
*   **Zero-JS SVG Animations:** Energy flow lines must use CSS keyframes (`stroke-dashoffset`) to minimize Javascript bundle sizes and achieve >90 PageSpeed.
*   **Independent Component Error Boundaries:** Astro pages must isolate telemetry queries so that if an API fails, only the specific card shows `NO_DATA // RUN DIAGNOSTICS`.
*   **Accessible Keyboard Navigation:** Focusable elements must implement `outline: 2px solid #29B6F6` with `outline-offset: 4px` for WCAG AA compliance.
*   **Aesthetic Responsive Grid:** The bento grid must collapse gracefully to 1 column on mobile to prevent overlapping touch targets.

## Domain-Specific Requirements

### Compliance & Regulatory

*   **Net-Metering & Interconnection:** Ensure calculations for solar payback reflect typical Ontario Energy Board (OEB) net-metering regulations, where surplus generation is credited against consumption rather than directly cashed out.
*   **Safety Disclosure:** Since this is a public visualizer, display clear disclaimers indicating that solar ROI calculations are estimations and do not substitute for professional engineering site audits or utility interconnection assessments.

### Technical Constraints

*   **Mathematical Precision:** Payback and yield calculations must match standardized NREL PVWatts formulas for the Ontario region (average 1,150 kWh yield per kW installed annually) to maintain engineering credibility.
*   **Latency Bounds:** Real-time client-side calculation loops must run inside the browser thread without blocking UI interaction, ensuring inputs remain responsive.

### Integration Requirements

*   **Utility Rate Tariffs:** Support Ontario's standard tariff structures:
    *   **Time-of-Use (TOU):** Peak, Mid-Peak, and Off-Peak pricing tiers.
    *   **Ultra-Low Overnight (ULO):** High-spread rates designed to incentivize overnight EV charging.
*   **Dynamic Telemetry:** Feed the V2H visualizer with realistic mock telemetry data mirroring typical stationary battery storage specs (e.g., 10 kWh nominal capacity, 5 kW peak charge/discharge rates).

### Risk Mitigations

*   **Inaccurate Rate Expectations:** Users might assume utility rates are static.
    *   *Mitigation:* Label calculations clearly as estimations using the latest OEB rate schedules, prompting users to check their local LDC (Local Distribution Company) rates.
*   **Telemetry Outage:** The system relies on a mock or real API fetch for real-time rates.
    *   *Mitigation:* Fall back cleanly to preset fallback rates and show the `NO_DATA // RUN DIAGNOSTICS` status, keeping the calculator interactive.

## Innovation & Novel Patterns

### Detected Innovation Areas

*   **Zero-JS SVG Animation Engine:** Traditional web applications rely on thick JS framework updates to render dynamic electrical flows. mtt implements a zero-overhead, CSS-only stroke path animation model. This utilizes CSS keyframes for stroke-dashoffset transitions, delivering smooth 60fps animations at 0ms bundle weight.
*   **Bento Grid Inline Configuration:** Configurable client-side overrides (like custom API URLs) are embedded directly as active tabs inside the Bento Grid dashboard itself, eliminating nested configuration pages and keeping the visitor focused on the main layout.

### Market Context & Competitive Landscape

*   **Landscape Analysis:** Standard developer and engineering portfolios are typically static or feature heavy, slow-to-load React dashboards that score poorly on mobile PageSpeed (<70). By combining static Astro generation with micro-utilities, mtt offers high-density telemetry alongside instant (sub-150ms) initial paint times.

### Validation Approach

*   **Lighthouse Performance Testing:** Assert that mobile PageSpeed scores remain >= 90.
*   **Touch and Axis Calibration:** Verify that mouse-hover 3D tilt effects degrade cleanly on touch-only viewports to avoid layout jittering or unexpected touch behaviors.

### Risk Mitigation

*   **CSS Stroke Support:** Older mobile browsers might render stroke-dashoffset animations inefficiently.
    *   *Mitigation:* Use simple solid color flow lines fallback if hardware acceleration is unavailable, and include basic visibility toggles.

## Web Application Specific Requirements

### Project-Type Overview

*   **Architecture Pattern:** Multi-Page Application (MPA) built using **Astro**, enabling static pre-rendering (SSG) to deliver minimal initial page payload weights.
*   **Interactivity Model:** Zero-framework client-side JavaScript. Real-time features (such as ROI calculations and telemetry badging) run on Vanilla JS directly compiled by Astro, avoiding React/Vue runtimes.

### Technical Architecture Considerations

*   **Static Generation (SSG):** All structure is statically compiled at build time. The client only downloads lightweight HTML, isolated CSS stylesheets, and mini-JS scripts.
*   **Scoped Styling:** Component styles are strictly scoped to Astro components, preventing class name leakage.

### Browser Matrix & Support

*   **Target Browsers:** Evergreen desktop and mobile browsers (Chrome 90+, Safari 15+, Firefox 90+, Edge 90+).
*   **Feature Detection:** Standard modern APIs (like `localStorage` for configuration persistence and `requestAnimationFrame` for cursor hover effects) must degrade gracefully if unsupported.

### Responsive Design & Bento Grid

*   **Responsive Breakpoints:**
    *   **Desktop (>= 1024px):** 12-column Bento Grid.
    *   **Tablet (>= 768px and < 1024px):** 6-column grid.
    *   **Mobile (< 768px):** 1-column grid layout, ensuring touch target spacing.
*   **Card Grid Layout (Desktop):**
    *   `CardHero`: Span 8, row span 2.
    *   `CardSolarROI`: Span 4, row span 1.
    *   `CardInvoice`: Span 4, row span 1.
    *   `CardVenture` (EcoAudit): Span 12, row span 1 (Row 3, balancing the grid).

### Performance Targets & SEO Strategy

*   **Lighthouse Performance:** Google PageSpeed Insights >= 90 on both desktop and mobile viewports.
*   **SEO Optimization:**
    *   **Metadata:** Explicit `<title>` and `<meta name="description">` tags.
    *   **Semantic HTML:** Strict usage of `<header>`, `<main>`, `<section>`, `<footer>`, and heading hierarchy (single `<h1>`).
    *   **Interactive Identifiers:** Every button and interactive control contains a unique `id` attribute.

### Accessibility Level (WCAG 2.1 AA)

*   **Contrast Ratios:** Text must maintain a contrast ratio of >= 4.5:1 against card backgrounds.
*   **Focus Ring:** All keyboard-focusable elements must display a high-visibility outline on focus: `outline: 2px solid #29B6F6; outline-offset: 4px;`.

## Functional Requirements

### 1. Navigation & Brand Presentation

*   **FR1:** Visitors can view the studio's brand logo in the main header.
*   **FR2:** Visitors can navigate between "Ventures", "Technology", and "About" sections using header links.
*   **FR3:** Visitors see their current section path highlighted dynamically in the header.
*   **FR4:** Visitors can view the studio's operational status through a dynamic status indicator.
*   **FR5:** Visitors can access standardized legal and compliance links in the website's footer.
*   **FR6:** Visitors can toggle the visual theme of the entire application.

### 2. Vehicle-to-Home (V2H) Arbitrage Visualizer

*   **FR7:** Visitors can view real-time utility tariff tier badges.
*   **FR8:** Visitors can view live home battery state of charge (SoC) metrics.
*   **FR9:** Visitors can view battery health percentage readouts.
*   **FR10:** Visitors can observe an animated energy flow diagram illustrating directions between utility grid, home solar array, home consumption load, and EV battery.
*   **FR11:** Visitors can trigger interactive 3D perspective shifts on the arbitrage visualizer container.
*   **FR12:** The system can detect when mouse cursor movements occur and apply corresponding visual tilt transforms.

### 3. Solar ROI Calculator

*   **FR13:** Visitors can input rooftop solar system size.
*   **FR14:** Visitors can input utility electricity rate tariff.
*   **FR15:** The system calculates and displays the estimated annual solar energy yield based on system size.
*   **FR16:** The system calculates and displays the estimated annual savings based on inputs.
*   **FR17:** The system calculates and displays the payback period in years.
*   **FR18:** Visitors manipulate slider controls with touch gestures to adjust numeric inputs.

### 4. Telemetry Graceful Degradation & Resilience

*   **FR19:** The system detects when external telemetry API data fetches fail or time out.
*   **FR20:** The system displays an isolated fallback state indicating data unavailability for affected components.
*   **FR21:** The system keeps other components functional and interactive during an isolated API failure.

### 5. Venture Portfolio Showcase

*   **FR22:** Visitors can view details and links for featured ventures in a responsive bento card.
*   **FR23:** Visitors can view an interactive invoice preview card.

## Non-Functional Requirements

### Performance

*   **NFR-P1 (PageSpeed Score):** The application must maintain a Google PageSpeed Insights performance score of >= 90 for both mobile and desktop profiles.
*   **NFR-P2 (Initial Paint):** The Time to First Contentful Paint (FCP) must be less than 500ms under standard 3G network throttle settings.
*   **NFR-P3 (Input Response):** Dynamic inputs (sliders in the Solar ROI Calculator) must calculate and redraw output values within 50ms of user input release or change events, avoiding visual stuttering.
*   **NFR-P4 (Animation Smoothness):** CSS-animated SVG flow paths must run at a minimum of 60 frames per second (fps) on devices with standard hardware acceleration.

### Accessibility

*   **NFR-A1 (WCAG Conformance):** The website must fully conform to Web Content Accessibility Guidelines (WCAG) 2.1 Level AA.
*   **NFR-A2 (Contrast Ratios):** All foreground text and icons must maintain a minimum contrast ratio of 4.5:1 against the dark background (`#0A0A0A` or `#141414`).
*   **NFR-A3 (Keyboard Navigation):** All interactive elements must be accessible via standard Tab key sequences. Focus rings must be styled with a clear electric blue outline (`2px solid #29B6F6`) and offset (`4px`) to ensure high visibility.

### Security & Privacy

*   **NFR-S1 (Data Privacy):** The application must store user-configured parameters (such as localStorage client overrides) locally in the client browser. No local inputs or variables may be sent to Maple Tyne's backend servers without user initiation.
*   **NFR-S2 (HTTPS and TLS):** The application must be served over secure HTTPS utilizing TLS 1.3 or higher.

### Reliability & Resilience

*   **NFR-R1 (Component Isolation):** An API request timeout or error on the telemetry fetch must not disrupt, crash, or freeze the rest of the landing page.
*   **NFR-R2 (Degraded Fallback Rate):** If the telemetry server is unreachable, the affected components must display fallback static mock visual data within 3 seconds of connection attempt.
