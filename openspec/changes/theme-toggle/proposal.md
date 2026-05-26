## Why

The current Notes App only supports dark mode. To improve accessibility, user choice, and comfort in different ambient lighting conditions, users should be able to toggle between a light theme and a dark theme.

## What Changes

* Add a theme toggle button to the main header.
* Define alternate CSS variables for a light mode theme.
* Persist the user's theme preference in localStorage.
* Load the saved theme preference on page load.

## Capabilities

### New Capabilities

### Modified Capabilities
- `notes-management`: Modifying specifications to include theme selection, display properties, and theme persistence.

## Impact

* `index.html` will be modified to support light/dark theme variables and toggle behaviors.
