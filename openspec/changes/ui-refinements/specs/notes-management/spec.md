## ADDED Requirements

### Requirement: Collapsible Sidebar
The system SHALL support collapsing the sidebar editor to maximize the notes grid display width.

#### Scenario: Collapse sidebar successfully
- **WHEN** the user clicks the sidebar toggle button
- **THEN** the system SHALL transition the sidebar out of view and expand the notes grid to occupy the full width of the main container.

#### Scenario: Expand sidebar successfully
- **WHEN** the user clicks the sidebar toggle button while the sidebar is collapsed
- **THEN** the system SHALL transition the sidebar back into view and return the notes grid to its split-width layout.

### Requirement: Category-colored Glowing Cards
The note cards SHALL display category-colored glowing shadows instead of a top colored ribbon.

#### Scenario: Render glowing cards
- **WHEN** the notes are rendered in the grid
- **THEN** each note card SHALL display a subtle box shadow matching the note's category color.

#### Scenario: Hover glowing card
- **WHEN** the user hovers over a note card
- **THEN** the note card's category-colored box shadow SHALL expand and brighten, simulating a glowing lift effect.
