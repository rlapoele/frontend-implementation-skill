<!--
Adapted in part from OpenAI frontend guidance and subsequently modified,
reorganized, and extended. See the repository LICENSE and NOTICE files.
-->

# Verification and Handoff

Use this checklist in proportion to the scope and risk of the implementation. Skip
an item only when it is genuinely irrelevant or the environment cannot perform it.

## Automated checks

- Discover and run the repository's applicable formatter, linter, type checker,
  automated tests, and production build.
- Do not invent commands or substitute a different package manager without a
  project reason.
- If a check fails, determine whether the change caused it. Fix caused failures;
  preserve and report unrelated pre-existing failures.

## Runtime and browser checks

- Start the application when its behavior requires a server. If the preferred port
  is occupied, use another available port. For standalone HTML, use a direct file
  link when the environment supports it.
- Exercise the primary changed workflow and its relevant loading, empty, error,
  validation, success, disabled, and recovery states.
- Inspect representative mobile and desktop viewports for visual or responsive
  changes.
- Check keyboard navigation, focus visibility, text overflow, broken assets,
  console errors, unintended layout shifts, and horizontal scrolling where
  applicable.
- Capture and inspect screenshots for meaningful visual changes rather than
  relying only on DOM assertions or a successful build.
- For canvas, animation, or 3D, confirm that meaningful pixels render at each
  tested viewport and that required motion or interaction works.

When browser, screenshot, or filesystem tools are unavailable, do not pretend to
have performed those checks. Complete the safe checks the environment supports and
state the limitation.

## Final handoff

Report:

- what was implemented;
- which checks passed;
- which checks failed or could not run, and why;
- material assumptions, exceptions, and remaining limitations; and
- the local URL or file link needed to inspect the result, when available.

Keep the handoff concise, but preserve evidence and uncertainty. Do not describe an
implementation as complete while known in-scope defects remain.
