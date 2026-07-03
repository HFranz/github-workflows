---
applyTo: 'wp-content/plugins/**,wp-content/themes/**,**/*.php,**/*.inc,**/*.js,**/*.jsx,**/*.ts,**/*.tsx,**/*.css,**/*.scss,**/*.json'
description: 'WordPress development guidelines'
---

# WordPress Development

## General
- Follow WordPress Coding Standards (WPCS).
- Never modify WordPress core.
- Extend via actions and filters.
- Use unique prefixes or PHP namespaces.
- Keep functions small and focused.
- Preserve existing architecture.

## Security
- Escape output.
- Sanitize and validate all external input.
- Verify capabilities before privileged actions.
- Protect forms, AJAX and REST endpoints with nonces.
- Always use `$wpdb->prepare()` for database queries.
- Validate uploads before processing.

## Internationalization
- Wrap all user-facing strings in WordPress i18n functions.
- Use the correct text domain consistently.

## Performance
- Enqueue assets; never inline JS or CSS.
- Load assets only when needed.
- Cache expensive operations where appropriate.
- Avoid unnecessary queries and large loops.

## REST API
- Always define `permission_callback`.
- Validate and sanitize request arguments.
- Return proper REST responses.

## Gutenberg
- Prefer `block.json`.
- Use `@wordpress/*` packages.
- Use server-side rendering only when needed.

## Admin
- Use the Settings API.
- Sanitize every setting.
- Escape all rendered output.

## Testing
- Add or update tests for new functionality.
- Cover sanitization, permissions, hooks and REST endpoints.
- Prefer WordPress test utilities and factories.

## Copilot
Ensure generated code:

- follows WPCS
- is secure by default
- is performant
- is testable
- uses hooks instead of core modifications
- escapes output
- sanitizes input
- includes capability and nonce checks where required
- uses i18n
- avoids unnecessary dependencies