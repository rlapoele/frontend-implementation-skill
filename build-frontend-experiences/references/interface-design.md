# Interface Design

Use this reference when creating or changing controls, interaction, layout,
typography, color, or responsive behavior.

## Audience and domain

- Tailor information density, navigation, terminology, visual style, and
  interaction patterns to the actual audience and frequency of use.
- Operational products such as SaaS, CRM, administration, and productivity tools
  should generally feel quiet, efficient, and work-focused. Favor organized
  information, predictable navigation, restrained styling, scanning, comparison,
  and repeated action over decorative or editorial composition.
- Games, creative tools, editorial experiences, and entertainment products may be
  more expressive, animated, illustrative, or playful when appropriate.
- Make common workflows coherent. Where relevant to scope, users should be able to
  enter, complete, cancel, recover from, and revisit important tasks without
  becoming lost.

## Choose controls by meaning

Use the control that communicates the interaction most clearly:

- familiar icons or icon buttons for compact tool actions;
- icon-and-text or text buttons when a label materially improves comprehension;
- swatches for colors;
- segmented controls for a small set of mutually exclusive modes;
- checkboxes or switches for binary choices;
- inputs, sliders, or steppers for numeric values;
- menus or selects for option sets; and
- tabs for peer views.

Use the project's icon library. If none exists, prefer one consistent library,
such as Lucide, over manually drawn versions of familiar icons. Do not replace a
clear label with an ambiguous icon to save space. Give every icon-only control an
accessible name and add a tooltip when its meaning may not be obvious. Do not rely
on hover alone.

## Accessibility and interaction

- Maintain logical focus order, visible focus indicators, sufficient contrast,
  associated form labels, and usable touch targets.
- Make instructions and feedback available to keyboard, touch, and assistive
  technology users.
- Provide concise onboarding, contextual help, empty-state guidance, or safety
  instructions when users genuinely need them. Avoid text that merely narrates
  obvious interface features or visual styling.
- Do not let motion obstruct reading or task completion. Respect reduced-motion
  preferences.

## Layout and hierarchy

- Use cards for meaningful boundaries such as repeated items, records, modals,
  inspectors, or genuinely framed tools. Avoid cards nested inside cards and do
  not turn every page section into a floating card.
- Prefer unframed layouts or full-width sections with constrained inner content
  for primary page structure.
- Keep card radii at 8px or less unless the established design system or requested
  direction specifies otherwise.
- Reserve display-scale typography for genuine hero content. Use compact headings
  in dashboards, panels, sidebars, cards, and tool surfaces.
- Give fixed-format controls, boards, grids, tiles, toolbars, and media stable but
  responsive dimensions. Dynamic content and interaction states must not
  unexpectedly resize or shift the layout.
- Make wrapping, clipping, or truncation intentional. Test long words, translated
  strings, validation messages, loading states, and user-provided content. Text
  must not overlap or hide adjacent content.
- Prefer relative units, container-aware rules, and bounded `clamp()` values when
  fluid typography is useful. Do not tie all typography directly to viewport
  width. Use letter spacing appropriate to the typeface and avoid excessively
  tight tracking.

## Color and decoration

- Define clear roles for surfaces, text, borders, actions, focus, selection,
  success, warning, and error.
- Avoid accidental one-hue interfaces unless the treatment is intentional or
  brand-led.
- Do not default to purple gradients, beige editorial palettes, dark slate
  dashboards, orange-brown themes, gradient orbs, bokeh blobs, or other fashionable
  decoration without a domain or brand reason.
- Decoration must support the subject or interaction rather than compensate for
  weak structure. Inspect final color usage for contrast, hierarchy, repetition,
  and consistency.
