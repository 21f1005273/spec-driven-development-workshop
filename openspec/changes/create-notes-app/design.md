## Context

The workshop requires comparing the implementation of a Notes App built with vibe coding versus Spec-Driven Development. To make the comparison direct, we will build a client-side only single-page application (SPA) running entirely in the browser.

## Goals / Non-Goals

**Goals:**
* Build a self-contained single-page application.
* Implement custom state management using an in-memory array synced with `localStorage`.
* Build a responsive visual interface using native CSS variables.

**Non-Goals:**
* Multi-user support or server-side authentication.
* Syncing notes with a remote cloud database.

## Decisions

### Decision 1: Self-contained Architecture
* **Choice**: Single file `index.html` containing CSS, HTML structure, and JS logic.
* **Rationale**: This matches the design of the `vibe-coding` branch exactly, making it easy to compare the resulting code file side-by-side.
* **Alternatives Considered**: Multi-file project (with separate `style.css` and `app.js`). Rejected because a single-file SPA is simpler to verify in the workshop context.

### Decision 2: Storage and State Management
* **Choice**: Browser `localStorage` using key `sdd_notes` and an in-memory notes array.
* **Rationale**: Simple, zero-dependency persistence that matches browser API capabilities. State updates are written to memory and immediately flushed to disk.
* **Alternatives Considered**: IndexedDB. Rejected as over-engineered for a simple notes app.

## Risks / Trade-offs

* **Risk**: LocalStorage capacity limit (approx 5MB per origin).
  * **Mitigation**: Notes are plain text and highly compact. Average note sizes are <1KB, allowing thousands of notes.
* **Risk**: In-memory search performance.
  * **Mitigation**: In-memory searching over a few hundred notes is instantaneous (<1ms).
