---
stepsCompleted: [1, 2, 3, 4]
inputDocuments: [
  "/home/danielaroko/applications/mtt/_bmad-output/planning-artifacts/prd.md",
  "/home/danielaroko/applications/mtt/_bmad-output/planning-artifacts/ux-design-specification.md",
  "/home/danielaroko/applications/mtt/screens.json"
]
---

# mtt - Epic Breakdown

## Overview

This document provides the complete epic and story breakdown for mtt, decomposing the requirements from the consumer-focused PRD and system design specifications into implementable, trackable user stories.

## Requirements Inventory

### Functional Requirements

*   **FR1:** Visitors can view the studio's brand logo in the main header.
*   **FR2:** Visitors can navigate between "Ventures", "Technology", and "About" sections using header links.
*   **FR3:** Visitors see their current section path highlighted dynamically in the header.
*   **FR4:** Visitors can view the studio's operational status through a dynamic status indicator.
*   **FR5:** Visitors can access standardized legal and compliance links in the website's footer.
*   **FR6:** Visitors can toggle the visual theme of the entire application.
*   **FR7:** Visitors can view real-time utility tariff tier badges.
*   **FR8:** Visitors can view live home battery state of charge (SoC) metrics.
*   **FR9:** Visitors can view battery health percentage readouts.
*   **FR10:** Visitors can observe an animated energy flow diagram illustrating directions between utility grid, home solar array, home consumption load, and EV battery.
*   **FR11:** Visitors can trigger interactive 3D perspective shifts on the arbitrage visualizer container.
*   **FR12:** The system can detect when mouse cursor movements occur and apply corresponding visual tilt transforms.
*   **FR13:** Visitors can input rooftop solar system size.
*   **FR14:** Visitors can input utility electricity rate tariff.
*   **FR15:** The system calculates and displays the estimated annual solar energy yield based on system size.
*   **FR16:** The system calculates and displays the estimated annual savings based on inputs.
*   **FR17:** The system calculates and displays the payback period in years.
*   **FR18:** Visitors manipulate slider controls with touch gestures to adjust numeric inputs.
*   **FR19:** The system detects when external telemetry API data fetches fail or time out.
*   **FR20:** The system displays an isolated fallback state indicating data unavailability for affected components.
*   **FR21:** The system keeps other components functional and interactive during an isolated API failure.
*   **FR22:** Visitors can view details and links for featured ventures in a responsive bento card.
*   **FR23:** Visitors can view an interactive invoice preview card.

### Non-Functional Requirements

*   **NFR-P1 (PageSpeed Score):** The application must maintain a Google PageSpeed Insights performance score of >= 90 for both mobile and desktop profiles.
*   **NFR-P2 (Initial Paint):** The Time to First Contentful Paint (FCP) must be less than 500ms under standard 3G network throttle settings.
*   **NFR-P3 (Input Response):** Dynamic inputs (sliders in the Solar ROI Calculator) must calculate and redraw output values within 50ms of user input release or change events, avoiding visual stuttering.
*   **NFR-P4 (Animation Smoothness):** CSS-animated SVG flow paths must run at a minimum of 60 frames per second (fps) on devices with standard hardware acceleration.
*   **NFR-A1 (WCAG Conformance):** The website must fully conform to Web Content Accessibility Guidelines (WCAG) 2.1 Level AA.
*   **NFR-A2 (Contrast Ratios):** All foreground text and icons must maintain a minimum contrast ratio of 4.5:1 against the dark background (`#0A0A0A` or `#141414`).
*   **NFR-A3 (Keyboard Navigation):** All keyboard-interactive elements must be accessible via standard Tab key sequences. Focus rings must be styled with a clear electric blue outline (`2px solid #29B6F6`) and offset (`4px`) to ensure high visibility.
*   **NFR-S1 (Data Privacy):** The application must store user-configured parameters (such as localStorage client overrides) locally in the client browser. No local inputs or variables may be sent to Maple Tyne's backend servers without user initiation.
*   **NFR-S2 (HTTPS and TLS):** The application must be served over secure HTTPS utilizing TLS 1.3 or higher.
*   **NFR-R1 (Component Isolation):** An API request timeout or error on the telemetry fetch must not disrupt, crash, or freeze the rest of the landing page.
*   **NFR-R2 (Degraded Fallback Rate):** If the telemetry server is unreachable, the affected components must display fallback static mock visual data within 3 seconds of connection attempt.

### Additional Requirements

*   **AR1 (Astro Custom Styling System):** The project must utilize Astro components coupled with custom design token variables declared in `global.css` (inheriting from theme variables in `:root` and `[data-theme="dark"]`).
*   **AR2 (Modular Localized CSS):** Style sheets must be scoped locally inside individual Astro components where possible to isolate styles and prevent global pollution.
*   **AR3 (Zero-JS UI Flows):** Interactive indicators (pulsing glow effects) and flow vectors must be implemented using pure CSS keyframes rather than loading external JavaScript canvas/animation libraries.

### UX Design Requirements

*   **UX-DR1 (Dark Mode Aesthetics):** The system must enforce a dark-mode-first aesthetic using Deep Tech Dark (`#0A0A0A`), Card containers (`#141414`), Grid boundaries (`#262626`), Success Green (`#66BB6A`), Info Blue (`#29B6F6`), Alert Amber (`#FFB74D`), and High-Contrast White (`#F5F5F5`).
*   **UX-DR2 (Typography System):** The typography must balance editorial brand authority and monospaced technical details: `Fraunces` for titles, `Outfit` for body/copy, and `JetBrains Mono` for code, coordinates, and telemetry badges.
*   **UX-DR3 (Ambient Glow Badges):** Status indicator labels must utilize soft CSS shadow glow animation pulses around color circles to represent live connectivity without loud flashing alerts.
*   **UX-DR4 (Bento Card Hover Tilt):** The `<BentoCard />` container must dynamically tilt slightly on a 3D axis based on cursor position (`--x`, `--y` custom coordinates) on desktop viewports.
*   **UX-DR5 (CSS-Driven Path Animation):** The `<ArbitrageFlow />` SVG paths must animate using dash arrays (`stroke-dashoffset` CSS animation loops) to show current charging/discharging cycles.

### FR Coverage Map

*   **FR1:** Epic 1 Story 1.2 (Header logo)
*   **FR2:** Epic 1 Story 1.2 (Header navigation links)
*   **FR3:** Epic 1 Story 1.2 (Section path highlighting)
*   **FR4:** Epic 1 Story 1.2 (Operational status indicator)
*   **FR5:** Epic 1 Story 1.4 (Footer legal compliance links)
*   **FR6:** Epic 1 Story 1.1 (Visual theme toggle)
*   **FR7:** Epic 2 Story 2.1 (Utility tariff tier badge)
*   **FR8:** Epic 2 Story 2.1 (Live battery SoC metrics)
*   **FR9:** Epic 2 Story 2.1 (Battery health readout)
*   **FR10:** Epic 2 Story 2.2 (Animated energy flow diagram)
*   **FR11:** Epic 2 Story 2.1 (3D perspective shift)
*   **FR12:** Epic 2 Story 2.1 (Cursor tilt transforms)
*   **FR13:** Epic 3 Story 3.1 (Solar system size slider input)
*   **FR14:** Epic 3 Story 3.1 (Electricity rate slider input)
*   **FR15:** Epic 3 Story 3.1 (Estimated annual solar yield calculations)
*   **FR16:** Epic 3 Story 3.1 (Estimated annual savings calculations)
*   **FR17:** Epic 3 Story 3.1 (Payback period calculations)
*   **FR18:** Epic 3 Story 3.1 (Touch gesture slider controls)
*   **FR19:** Epic 2 Story 2.3 (Detect telemetry fetch failure/timeout)
*   **FR20:** Epic 2 Story 2.3 (Display isolated fallback state for affected card)
*   **FR21:** Epic 2 Story 2.3 (Keep rest of the page functional during failure)
*   **FR22:** Epic 1 Story 1.3 (Featured ventures bento cards - Invoice & EcoAudit)
*   **FR23:** Epic 1 Story 1.3 (Interactive invoice preview card)

---

## Epic List

### Epic 1: Global Branding & Layout Grid Framework
Establish the premium dark-mode venture studio brand identity and responsive Bento layout. Users can browse the core branding, navigate links, and interact with baseline portfolio card containers.
*   **FRs Covered:** FR1, FR2, FR3, FR4, FR5, FR6, FR22, FR23
*   **NFRs Covered:** NFR-P1, NFR-P2, NFR-A1, NFR-A2, NFR-A3, NFR-S2
*   **ARs & UX-DRs Covered:** AR1, AR2, UX-DR1, UX-DR2, UX-DR3

### Epic 2: AI-Native V2H Energy Arbitrage Visualizer
Provide immediate visual credibility for V2H energy orchestration. Users can view realtime VLO/ULO energy spreads and observe dynamic power transfer loops via CSS-animated SVG path flows, backed by robust error boundaries.
*   **FRs Covered:** FR7, FR8, FR9, FR10, FR11, FR12, FR19, FR20, FR21
*   **NFRs Covered:** NFR-P1, NFR-P2, NFR-P4, NFR-A1, NFR-A2, NFR-A3, NFR-R1, NFR-R2
*   **ARs & UX-DRs Covered:** AR3, UX-DR1, UX-DR4, UX-DR5

### Epic 3: Interactive Solar ROI Calculator
Expose high-utility estimation tools for homeowners to compute financial payback. Homeowners can estimate solar ROI in real-time using touch-optimized controls with immediate client-side formula evaluation.
*   **FRs Covered:** FR13, FR14, FR15, FR16, FR17, FR18
*   **NFRs Covered:** NFR-P1, NFR-P3, NFR-A1, NFR-A2, NFR-A3, NFR-S1
*   **ARs & UX-DRs Covered:** AR2, UX-DR1, UX-DR2

---

## Epic 1: Global Branding & Layout Grid Framework

### Story 1.1: Design Token CSS Variables, Layout Frame & Favicon
**As a** Visitor,
**I want** the site to render in a dark-mode-first premium tech layout with proper typography, brand identity, and favicon,
**So that** I can immediately experience Maple Tyne's engineering brand identity with zero layout shift.

**Acceptance Criteria:**
*   **Given** the visitor opens the landing page in their browser
*   **When** the document loads
*   **Then** the background must render in deep tech dark (`#0A0A0A`), body copy must render in Outfit (`#F5F5F5`), and headings/titles must render in Fraunces, achieving a color contrast ratio of $> 4.5:1$
*   **And** the monospace elements and telemetry tags must render in JetBrains Mono (`#29B6F6`)
*   **And** the theme configuration must be read from `localStorage` (defaulting to dark theme) via an inline blocking script in `Layout.astro` to prevent flashes of light background
*   **And** the browser favicon must be configured in `Layout.astro` to use the custom Maple Tyne logo asset instead of any default Astro branding

### Story 1.2: Sticky Glassmorphic Header & System Status Telemetry
**As a** Builder or Client,
**I want** a persistent, glassmorphic sticky header containing primary site links, a theme toggle, and a dynamic system status badge,
**So that** I can navigate the site easily and see the dynamic status of the operations center at a glance.

**Acceptance Criteria:**
*   **Given** the visitor scrolls down the page
*   **When** scrolling past the header threshold
*   **Then** the header must remain stickied to the top viewport with a glassmorphic background blur (`backdrop-filter: blur(12px)`) and semi-transparent dark background (`rgba(10, 10, 10, 0.8)`)
*   **And** it must display the company logo brand mark (using the custom SVG logo asset, scaled to a max height of `32px`) next to the company name, replacing any default Astro logo
*   **And** it must display navigation links for *Ventures*, *Technology*, and *About*, showing a distinct active state blue outline (`outline: 2px solid #29B6F6`, `outline-offset: 4px`) when focused via keyboard
*   **And** it must feature a dynamic telemetry badge containing the text `SYS_STATUS: ACTIVE` in `JetBrains Mono` font, with a pulsing green indicator dot (pulsing between opacity 0.4 and 1.0 using pure CSS keyframes)

### Story 1.3: Responsive Bento Grid Layout Framework
**As a** Visitor,
**I want** to view Maple Tyne's venture studio portfolio organized in a responsive tactile grid,
**So that** I can interactively explore distinct venture capabilities and redirect to external apps easily.

**Acceptance Criteria:**
*   **Given** the visitor is browsing on different devices
*   **When** the screen size changes
*   **Then** the Bento Grid must adjust layout rules: 12-column grid on desktop viewports ($\ge 1024px$), 6-column grid on tablet viewports ($768px - 1023px$), and collapse to a single-column vertical stack on mobile viewports ($< 768px$)
*   **And** each card container (`.tactile-card`) must render with corner radii of `12px` and a grid border (`#262626`), lifting upward and shifting border color to the brand accent green (`#66BB6A`) on cursor hover
*   **And** the portfolio showcase cards must include *Invoice Generator* (Active Micro-SaaS card spanning 4 columns) and *EcoAudit Canada* (Venture card spanning 12 columns at the bottom to balance the grid layout)

### Story 1.4: Dynamic Footnotes & Footer Links
**As a** Visitor,
**I want** to see navigation links in the footer,
**So that** I can access auxiliary company protocols and compliance information.

**Acceptance Criteria:**
*   **Given** the user scrolls to the bottom of the page
*   **When** they inspect the footer
*   **Then** the footer must render a top grid border line (`#262626`) and feature links for Regional Operations, Technical Docs, Privacy Protocol, and Terms of Orchestration
*   **And** these links must render in monospaced uppercase typography (`JetBrains Mono`)

---

## Epic 2: AI-Native V2H Energy Arbitrage Visualizer

### Story 2.1: V2H Arbitrage Telemetry & Visualizer Layout
**As a** Homeowner or Energy Auditor,
**I want** to view V2H arbitrage calculations and EV battery protection metrics in a structured telemetry table card,
**So that** I can evaluate utility rate optimization (ULO) spreads and battery health at a glance.

**Acceptance Criteria:**
*   **Given** the user is viewing the V2H Arbitrage Visualizer card in the Bento grid
*   **When** they read the metrics
*   **Then** the card must display the grid rate (e.g. `35.2¢/kWh`), battery state of charge (e.g. `82%`), and EV battery health (e.g. `98%`) in high contrast `JetBrains Mono` text (`#F5F5F5` on `#141414`)
*   **And** it must display dynamic visual badges for rate tier levels (e.g. `ULO PEAK` in alert amber `#FFB74D` or `ULO OFF-PEAK` in success green `#66BB6A`) with ambient pulsing glow indicators
*   **And** the card container must support the hardware-accelerated 3D mouse tilt interaction on desktop viewports ($\ge 1024px$) matching `UX-DR4` (`perspective(1000px)` transform rotation bound to cursor coordinates `--x` and `--y`), which must be disabled on tablet/mobile touch screens

### Story 2.2: CSS-Animated Energy Flow SVG Diagram
**As a** Homeowner,
**I want** to see a real-time animated SVG flow diagram mapping current flowing paths between Solar, EV Battery, Home, and Grid,
**So that** I can visually trace power sourcing cycles (e.g., Grid to Battery vs Battery to Home).

**Acceptance Criteria:**
*   **Given** the user is viewing the V2H Arbitrage Visualizer card
*   **When** the page renders
*   **Then** the system must display an inline responsive SVG diagram connecting four node markers: Solar, EV Battery, Home, and Grid
*   **And** the connection vectors (lines/curves) must animate using CSS `stroke-dashoffset` keyframes to represent active flow directions (e.g. dashed strokes moving from Battery to Home) with zero external JS animation libraries (complying with `AR3`)
*   **And** the SVG must be fully accessible and scalable, resizing smoothly across desktop, tablet, and mobile grid cells without clipping or distortion

### Story 2.3: Telemetry Failure Resilience & Graceful Degradation
**As a** Homeowner or Energy Auditor,
**I want** the V2H Arbitrage visualizer to detect when external telemetry API data fetches fail or timeout,
**So that** the affected card gracefully degrades to an isolated fallback UI without freezing or breaking other interactive components on the page.

**Acceptance Criteria:**
*   **Given** the visitor opens the page
*   **When** the external telemetry API fetch fails or times out
*   **Then** the V2H Arbitrage card status badge must update from `V2H_ACTIVE` (green pulsing) to `CONFIG REQUIRED` (amber warning badge)
*   **And** the telemetry metrics panel must hide and a fallback panel containing `SYSTEM_FAULT: NO_DATA // RUN DIAGNOSTICS` must be displayed in a high-contrast amber/red warning layout
*   **And** the user must be able to click the `[RUN_DIAGNOSTICS]` button to initiate a diagnostic run, showing a monospace text spinner (`\`, `|`, `/`, `-`) for 1.5 seconds, then restoring/toggling the simulated live data to allow verification of both states
*   **And** all other interactive components (such as the Solar ROI Calculator sliders and links) must remain fully interactive and functional (complying with NFR-R1 and NFR-R2)

---

## Epic 3: Interactive Solar ROI Calculator

### Story 3.1: Interactive Solar ROI Calculator Widget
**As a** Homeowner,
**I want** to interactively calculate regional solar yield and return on investment in real time by entering solar panel size inputs,
**So that** I can evaluate the financial viability of installing solar panels on my property.

**Acceptance Criteria:**
*   **Given** the user is viewing the Solar ROI Calculator card
*   **When** they enter or change the solar panel system size (e.g., using a touch-optimized slider or input field with a minimum touch target size of `48px x 48px`)
*   **Then** the widget must dynamically compute and display the estimated regional solar yield (kWh/year) and ROI (years) in real time without refreshing the page
*   **And** the output calculations must update instantly (within 50ms), rendering in high contrast `Outfit` and `JetBrains Mono` typography
*   **And** the math formulas must utilize Ontarian region coefficients (average 1,150 kWh/kW annual yield) and net-metering accumulation logic (surplus generation credited to reduce utility consumption)
