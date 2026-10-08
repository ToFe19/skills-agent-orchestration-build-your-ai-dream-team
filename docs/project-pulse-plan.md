# Project Pulse dashboard plan

## Summary

Mona's Project Pulse dashboard is a lightweight static web app that helps contributors quickly understand which projects are active, who owns them, their current status, recent activity, level of priority, and a short contributor-friendly summary. The work will be split across a Planner-led implementation sequence, with the Designer shaping the UX and the Coder building the final static HTML, CSS, and JSON data files.

## Implementation phases

### Phase 1: Define the data contract

- File ownership: `app/project-data.json`
- Owner: Coder
- Goal: Create a top-level `projects` array with each project including `name`, `owner`, `status`, `recentActivity`, and `priority`.
- Dependencies: This file provides the data source for the dashboard cards and summary display.

### Phase 2: Build the dashboard structure

- File ownership: `app/index.html`
- Owner: Coder
- Goal: Create semantic HTML for the dashboard shell, project cards, status badges, and summary content.
- Dependencies: The structure depends on the data fields defined in `app/project-data.json` and should be designed to support the Designer's layout guidance.

### Phase 3: Apply visual polish and responsiveness

- File ownership: `app/styles.css`
- Owner: Designer
- Goal: Create a polished dashboard UI with readable spacing, project cards, badge styling, clear hierarchy, and responsive behavior.
- Dependencies: CSS should align with the dashboard structure in `app/index.html` and the data shape from `app/project-data.json`.

### Phase 4: Add a runnable launch configuration

- File ownership: `.vscode/launch.json`
- Owner: Coder
- Goal: Create a strict JSON launch configuration named `Run Project Pulse Dashboard` that serves the `app/` directory and opens `index.html`.
- Dependencies: This should be created after the app files are stable and should support local preview without a directory listing.

## Agent responsibilities

### Planner

- Research the repository and the brief.
- Identify dependencies, file ownership, and sequencing.
- Communicate validation expectations and edge cases.

### Orchestrator

- Break the work into phases.
- Delegate task scope to the Designer and Coder.
- Verify that outputs fit together before the handoff.

### Designer

- Guide the information hierarchy and visual layout.
- Prioritize readability, accessibility, and a polished dashboard feel.
- Review the CSS and markup for consistency with a professional Project Pulse interface.

### Coder

- Implement the project data, HTML structure, and launch config.
- Ensure the static app meets the field and file requirements from the brief.
- Validate the final files and the .vscode launch setup.

## Dependencies between workstreams

- `app/project-data.json` must exist before the HTML can render project information reliably.
- `app/index.html` must be structured to match the visual system described by the Designer.
- `app/styles.css` depends on the final HTML structure and project data keys.
- `.vscode/launch.json` depends on the final app file layout and should be added once implementation is stable.

## Parallel work decisions

- The Designer and Coder can work in parallel on their respective files once the data contract is agreed upon.
- The CSS and HTML work should be coordinated so styling matches the markup structure.
- The launch configuration should be created near the end, after the dashboard files are in place.

## Validation expectations

The dashboard should be considered complete when:

- `app/project-data.json` uses a top-level `projects` array.
- Each project includes `name`, `owner`, `status`, `recentActivity`, and `priority`.
- `app/index.html` renders a dashboard UI with visible project cards and readable status information.
- `app/styles.css` includes polished dashboard styling such as `.dashboard`, `.project-card`, rounded corners, and shadow treatment.
- `.vscode/launch.json` is valid JSON and opens the app's `index.html` from the `app/` directory.
- The app can be opened using the `Run Project Pulse Dashboard` launch configuration.

## Key risks and edge cases

- Inconsistent field names between the JSON and the rendered HTML.
- Styling that looks generic instead of clearly like a Project Pulse dashboard.
- Launch configuration that opens the directory rather than the dashboard page.
- Missing validation for accessibility and responsive behavior.

## Proposed execution order

1. Confirm data model in `app/project-data.json`.
2. Build the HTML shell in `app/index.html`.
3. Apply the polished dashboard styling in `app/styles.css`.
4. Add the launch configuration in `.vscode/launch.json`.
5. Validate the completed app for structure, CSS, and launch readiness.
