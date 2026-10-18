---
name: build-frontend-experiences
description: Builds or modifies user-facing frontends with domain-appropriate design, accessible interaction, responsive layout, controlled scope, and browser-verified delivery. Use when implementing pages, components, application workflows, websites, games, or interactive tools. Do not use for backend-only work or design critique without implementation.
license: Apache-2.0
---

<!--
Adapted in part from OpenAI frontend guidance and subsequently modified,
reorganized, and extended. See the repository LICENSE and NOTICE files.
-->

# Build Frontend Experiences

Build the requested frontend as a coherent, usable product experience. Apply these
instructions to implementation decisions, not as permission to expand the task.

## Decision priority

Do not compromise correctness, security, accessibility, or data integrity to
satisfy a visual preference or reproduce an existing convention.

Subject to those requirements, resolve conflicts in this order:

1. The user's explicit requirements and acceptance criteria
2. The existing product's architecture, design system, and conventions
3. The audience, domain, and supported platforms
4. This skill's defaults

Treat the defaults as strong guidance rather than universal laws. Make the
smallest justified exception when context requires one and disclose material
exceptions in the handoff.

## Understand the task

Before implementation:

- Identify the audience, primary workflow, supported devices and inputs, and the
  states relevant to the requested scope.
- In an existing product, inspect the relevant components, tokens, spacing,
  typography, icon library, navigation, state conventions, and dependencies.
- Reuse suitable established patterns. Do not introduce a competing visual
  language, component system, or dependency without a concrete need.
- Preserve established behavior unless the task requires changing it. Repair an
  incorrect, insecure, or inaccessible pattern as narrowly as possible.
- Keep product scope explicit. Do not invent major features to make the result
  appear more complete.

## Implement the experience

- Build the requested experience rather than a marketing page about the experience.
  Unless a landing page is requested or necessary, open on the primary usable workflow.
- Within scope, implement the states users can reasonably encounter, such as
  loading, empty, success, error, disabled, validation, and recovery states.
- Use semantic HTML before ARIA and target WCAG 2.2 AA unless the project defines
  a stricter standard.
- Support appropriate keyboard, pointer, touch, zoom, text resizing, reflow, and
  reduced-motion behavior. Provide visible focus and accessible names.
- Communicate validation errors and asynchronous status changes clearly. Do not
  use color alone to communicate meaning.
- Treat user-provided and external content as untrusted. Use safe defaults for
  external links, embeds, file handling, and browser storage. Do not inject
  unsanitized content; expose secrets or sensitive data in client code, logs,
  screenshots, or errors; or bypass established authentication, authorization,
  and data-handling boundaries.
- Prefer platform features and existing project capabilities before adding a
  dependency. Use a mature library when established domain logic would otherwise
  be risky to reproduce.

For controls, layout, typography, color, responsive behavior, and interface
states, read [references/interface-design.md](references/interface-design.md).

For landing pages, prominent media, generated imagery, canvas, animation, games,
or 3D, also read
[references/landing-media-and-3d.md](references/landing-media-and-3d.md).

## Verify and hand off

Verify in proportion to the size and risk of the change. For any runnable or
materially visual implementation, read
[references/verification-and-handoff.md](references/verification-and-handoff.md).

Do not claim a check passed unless it ran successfully. Fix defects introduced by
the work before finishing; report unrelated failures and unavailable checks
without disguising them as successful verification.
