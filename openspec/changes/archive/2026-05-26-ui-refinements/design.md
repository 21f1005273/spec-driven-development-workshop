## Context

To make the SDD version's interface more functional and premium, we are implementing a collapsible sidebar menu and substituting solid top color ribbons with category-colored box shadows.

## Goals / Non-Goals

**Goals:**
* Animate the collapsible sidebar using smooth CSS grid transitions.
* Replace the rigid top ribbon on note cards with ambient glowing shadows derived from the note's custom color.
* Add a dedicated sidebar toggle icon button to the header layout.

**Non-Goals:**
* Changing form contents or field schemas.

## Decisions

### Decision 1: Collapsible Sidebar layout transition
* **Choice**: Toggle a class `.sidebar-collapsed` on `.main-container`. Set `.main-container` layout to grid and transition the `grid-template-columns` property.
* **Rationale**: Animating `grid-template-columns` from `360px 1fr` to `0px 1fr` allows the sidebar container and note grid to adjust widths synchronously. By combining this with `overflow: hidden`, `opacity: 0`, and `pointer-events: none` on the sidebar under collapsed states, the sidebar elements collapse cleanly without wrapping layout flows.
* **Alternatives Considered**: Absolute positioning overlay. Rejected because it hides notes rather than expanding their grid workspace.

### Decision 2: Category Glowing Shadows
* **Choice**: Apply native CSS variables to drive box-shadow glow intensity:
  * Rest state: `box-shadow: 0 4px 15px -3px rgba(0,0,0,0.4), 0 0 12px -3px var(--note-color);`
  * Hover state: `box-shadow: 0 10px 25px -5px rgba(0,0,0,0.5), 0 0 20px -1px var(--note-color);`
* **Rationale**: Utilizing `var(--note-color)` directly inside `box-shadow` avoids JS-computed RGBA values and gives a premium floating glow that responds smoothly to hover scale-up transforms.
* **Alternatives Considered**: Static colored icons. Rejected because glowing shadows create a much stronger premium dark-theme contrast.

## Risks / Trade-offs

* **Risk**: Layout jumping on mobile screens during collapse.
* **Mitigation**: Disable grid template animations on narrow screens under `@media (max-width: 900px)`.
