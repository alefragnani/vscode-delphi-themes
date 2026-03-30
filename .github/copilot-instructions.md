# Delphi Themes Extension for VS Code

Always reference these instructions first and fall back to additional search or terminal commands only when project files do not provide enough context.

## Project Overview

This repository contains a Visual Studio Code themes extension that ships multiple Delphi-inspired color themes.

The extension is manifest/theme-file driven and does not require TypeScript runtime code for core behavior.

## Technology Stack

- Language: JSON
- Runtime: VS Code themes extension contributions
- Bundler: None (asset/manifest-driven)
- Linting: None (manual JSON/theme validation)
- Testing: Manual validation in VS Code

## Working Effectively

Typical workflow:

1. Edit theme JSON files under `themes/`.
2. Update theme contributions in `package.json` when adding/removing themes.
3. Validate theme colors in VS Code by installing/running the extension.

No mandatory TypeScript build pipeline is required for core theme maintenance.

## Build and Development Commands

There are no required npm build/lint/test scripts in this repository.

Validation focuses on:

- Theme JSON correctness.
- `contributes.themes` entries in `package.json`.
- Visual verification inside VS Code.

## Testing and Validation

Manual validation checklist:

1. Open a representative code sample in VS Code.
2. Switch to each contributed Delphi theme.
3. Validate editor foreground/background contrast.
4. Validate UI readability (activity bar, sidebar, status bar, tabs).
5. Verify all contributed theme paths in `package.json` resolve correctly.

## Project Structure and Key Files

```
themes/                   # Color theme definitions
├── delphi-classic-color-theme.json
├── delphi-default-color-theme.json
└── ...
```

## Coding Conventions and Patterns

### Indentation

- We spaces, not tabs.
- Use 4 spaces for indentation.

### Code Quality

- Keep JSON formatting consistent with existing file style.
- Preserve valid VS Code theme schema fields.
- Prefer incremental color updates with visual checks.
- Keep theme labels stable unless change is intentional and documented.

## Extension Features and Configuration

This extension contributes themes via `contributes.themes` in `package.json`.

For each theme entry, ensure:

1. `label` is clear and user-friendly.
2. `uiTheme` matches the intended brightness family (`vs` or `vs-dark`).
3. `path` points to an existing theme file.

## Dependencies and External Tools

- No runtime dependencies required for theme rendering.
- No external formatters/tools required for normal theme maintenance.

## Troubleshooting and Known Limitations

- If a theme does not appear, verify `contributes.themes` entry and JSON syntax.
- If syntax highlighting looks wrong, validate token color scopes and fallback behavior.
- Theme visual quality may vary across languages/extensions due to semantic token providers.

## CI and Pre-Commit Validation

Before committing:

1. Validate `package.json` and theme JSON syntax.
2. Manually test all themes in a local VS Code instance.
3. Update CHANGELOG/README when visuals or labels change.

## Common Tasks

Add a new theme:

1. Add a new `themes/*.json` file.
2. Add contribution under `package.json > contributes.themes`.
3. Validate appearance in VS Code.
4. Update documentation and changelog.

Adjust existing theme colors:

1. Edit target theme file.
2. Validate readability and contrast.
3. Re-test language samples and UI surfaces.


