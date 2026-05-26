## Context

The current Notes App only supports dark mode. We need to introduce a light mode theme while maintaining our premium visual aesthetic and allowing users to toggle between them.

## Goals / Non-Goals

**Goals:**
* Define light-mode overrides for all primary CSS color variables.
* Add an interactive theme toggle button in the header.
* Persist theme choice under localStorage key `theme_preference`.
* Prevent flash-of-dark-mode on page reload if light mode is selected.

**Non-Goals:**
* Auto-detecting system theme (out of scope for this simple refinement).

## Decisions

### Decision 1: Theme implementation via class injection
* **Choice**: Inject `.light-theme` class on the `<body>` element.
* **Rationale**: This is the standard vanilla CSS approach. The CSS stylesheet will contain variable overrides scoped under `body.light-theme`.
* **Alternatives Considered**: Modifying elements directly via JavaScript. Rejected because CSS variables are cleaner, maintainable, and transition smoothly.

### Decision 2: Theme Persistence Key
* **Choice**: LocalStorage key `notes_theme`.
* **Rationale**: Simple key value string (`"dark"` or `"light"`).
* **Alternatives Considered**: Storing it as part of a larger settings JSON object. Rejected as unnecessary overhead for a single setting.

## Risks / Trade-offs

* **Risk**: Flash of dark theme on initial page render.
* **Mitigation**: Place the script to check localStorage and apply the class immediately at the top of `<body>` so it runs before any DOM content is painted.
