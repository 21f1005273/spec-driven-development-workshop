## ADDED Requirements

### Requirement: Creating a note
The system SHALL allow users to create a note containing a title, text content, a category tag, a category color, and timestamps (creation and last update).

#### Scenario: Successfully create note
- **WHEN** a user enters a valid title and content, selects a category, and saves the note
- **THEN** the system SHALL save the note to localStorage and display it at the top of the notes grid.

### Requirement: Editing a note
The system SHALL allow users to edit an existing note's title, text content, category tag, and category color.

#### Scenario: Successfully edit note
- **WHEN** a user selects an existing note, modifies its fields, and saves the changes
- **THEN** the system SHALL update the note in localStorage and update its display in the grid with the updated contents and last-update timestamp.

### Requirement: Deleting a note
The system SHALL allow users to delete a note, which permanently removes it from the store after confirmation.

#### Scenario: Successfully delete note
- **WHEN** a user selects the delete option on a note and confirms the action
- **THEN** the system SHALL remove the note from localStorage and remove its card from the notes grid.

### Requirement: Searching notes
The system SHALL support real-time search of notes, filtering by matching text in either the title or body content.

#### Scenario: Filter notes in real-time
- **WHEN** a user enters a text query into the search field
- **THEN** the system SHALL immediately update the grid to display only notes whose title or body contains the query, case-insensitively.

### Requirement: Persistent storage
The system SHALL persist all notes across browser sessions using the browser's localStorage API.

#### Scenario: Load notes on page initialization
- **WHEN** the application is loaded
- **THEN** the system SHALL retrieve notes stored in localStorage and render them in the notes grid, sorting by last-updated timestamp descending.
