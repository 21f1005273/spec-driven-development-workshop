## Why

To enhance the visual premium feel and functional usability of the Notes App:
1. Solid ribbons on note cards are replaced by dynamic, category-colored glowing shadows.
2. A collapsible sidebar is introduced to allow users to hide the editing form and maximize the note grid workspace.

## What Changes

* Remove the colored top ribbon (`::before` border) from note cards.
* Add category-colored box shadows to note cards that glow on hover.
* Add a sidebar toggle button next to the logo in the header.
* Implement transitions to smoothly animate the sidebar collapsing (sliding out) and the notes grid expanding to fill the screen.
* Persist the sidebar toggle state (open/closed) in `localStorage` or memory.

## Capabilities

### New Capabilities

### Modified Capabilities
- `notes-management`: Modifying specifications to adjust card styling rules and layout navigation controls.

## Impact

* Modifies CSS layouts and JavaScript elements in `index.html`.
