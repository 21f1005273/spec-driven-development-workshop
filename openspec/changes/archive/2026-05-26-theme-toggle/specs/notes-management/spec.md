## ADDED Requirements

### Requirement: Theme Selection
The system SHALL allow users to toggle between a Light theme and a Dark theme.

#### Scenario: Toggle theme successfully
- **WHEN** a user clicks the theme toggle button in the header
- **THEN** the system SHALL switch the color theme of the interface and update the toggle icon.

### Requirement: Theme Persistence
The system SHALL persist the chosen theme preference across sessions using localStorage.

#### Scenario: Load saved theme preference
- **WHEN** the application is loaded
- **THEN** the system SHALL load the saved theme preference from localStorage and apply it to the user interface (defaulting to Dark theme if no preference is saved).
