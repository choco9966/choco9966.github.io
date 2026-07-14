# Design

## Source of truth
- Status: Active
- Last refreshed: 2026-07-14
- Primary product surfaces: Single-page personal research portfolio (`index.html`)
- Evidence reviewed: `index.html`, `stylesheet.css`, `pictures/profile.jpg`; no prior design docs, mockups, or visual-regression baselines were present.

## Brand
- Personality: Rigorous, calm, credible, and technically accomplished.
- Trust signals: Named employers and projects, publication venues, linked papers, competition rankings, and direct professional profiles.
- Avoid: Dashboard styling, decorative gradients, oversized hero copy, dense card grids, novelty motion, and visual effects that compete with research content.

## Product goals
- Goals: Help research and engineering peers quickly understand Hyeonwoo Kim's focus, current work, publications, experience, and notable achievements.
- Non-goals: Marketing lead generation, blogging, project demos, or an interactive application experience.
- Success signals: Primary identity is clear at first glance; any major section is reachable immediately; dates, venues, companies, and project titles can be scanned without reading every paragraph.

## Personas and jobs
- Primary personas: Research collaborators, hiring managers, conference peers, and engineers evaluating professional background.
- User jobs: Establish credibility, locate publications, understand career progression, and reach external professional profiles.
- Key contexts of use: Desktop research browsing, mobile link sharing, and quick review from search or profile links.

## Information architecture
- Primary navigation: Research, News, Publications, Experience, Awards, Talks.
- Core routes/screens: One static page with anchored sections.
- Content hierarchy: Identity and current role → research focus → current news → publications → professional experience → awards → talks → contact footer.

## Design principles
- Editorial before ornamental: Use typography, alignment, and whitespace to create hierarchy instead of card chrome.
- Optimize for scanning: Keep labels and dates predictable, align repeated metadata, and separate long entries with rhythm rather than heavy rules.
- Tradeoffs: Favor a calm, information-dense academic presentation over a visually louder portfolio; keep all existing content visible rather than collapsing it behind interactions.

## Visual language
- Color: Warm off-white canvas, near-black ink, muted slate metadata, restrained deep-blue links, and subtle warm-gray rules.
- Typography: System sans-serif for durable cross-platform rendering; strong display scale for identity, compact uppercase labels for navigation and metadata.
- Spacing/layout rhythm: Wide editorial canvas with a narrow section-label column and readable content column; 8px-based rhythm.
- Shape/radius/elevation: Small radii; borders and tonal surfaces instead of shadows.
- Motion: Minimal native scrolling only; respect reduced-motion preferences.
- Imagery/iconography: Reuse the existing portrait; no icon library or decorative imagery.

## Components
- Existing components to reuse: Intro portrait, research list, news list, publication entries, experience entries, award rank tags, and footer links.
- New/changed components: Skip link, anchored section navigation, editorial section grid, profile-link pills, and stronger timeline metadata alignment.
- Variants and states: Default, hover, keyboard focus, and responsive stacked layouts.
- Token/component ownership: CSS custom properties in `stylesheet.css`; no separate design-system dependency.

## Accessibility
- Target standard: WCAG 2.2 AA where applicable to the static page.
- Keyboard/focus behavior: Visible `:focus-visible` treatment, keyboard-reachable anchored navigation, and a skip-to-content link.
- Contrast/readability: Body and metadata colors must remain readable on the page background; do not convey hierarchy by color alone.
- Screen-reader semantics: Semantic header, navigation, main, sections with headings, lists, and footer.
- Reduced motion and sensory considerations: Disable smooth scrolling when reduced motion is requested; no flashing or motion-dependent content.

## Responsive behavior
- Supported breakpoints/devices: Modern mobile and desktop browsers from 360px viewport width upward.
- Layout adaptations: Two-column intro and section grid on desktop; single-column content and stacked metadata on narrow screens; navigation becomes horizontally scrollable.
- Touch/hover differences: Maintain generous touch targets; hover is supplementary and focus styles provide equivalent feedback.

## Interaction states
- Loading: Browser-native static document loading; content remains useful without scripts.
- Empty: Not applicable while curated content is present.
- Error: Broken external resources must not prevent local content from rendering; portrait alt text conveys purpose if the image fails.
- Success: Anchor destinations receive clear viewport positioning below the sticky navigation.
- Disabled: Not applicable.
- Offline/slow network, if applicable: All layout, typography, and portrait assets are local; external links remain optional.

## Content voice
- Tone: Direct, factual, research-oriented, and modestly confident.
- Terminology: Preserve established model, benchmark, venue, and employer names.
- Microcopy rules: Use concise labels; retain English as the primary page language and Korean only where it is part of names or source titles.

## Implementation constraints
- Framework/styling system: Static semantic HTML and handwritten CSS only.
- Design-token constraints: Extend the existing CSS custom-property approach; no new framework or dependency.
- Performance constraints: No JavaScript, remote fonts, icon packages, or unnecessary media.
- Compatibility constraints: Preserve GitHub Pages compatibility and all existing content URLs.
- Test/screenshot expectations: Check semantic structure, link/content preservation, keyboard focus, overflow, and layouts at 1440px, 1024px, 768px, and 390px when a browser renderer is available.

## Open questions
- [ ] None currently. Revisit this document if the site adds projects, a résumé download, dark mode, or a separate publication index.
