<!--
Adapted in part from OpenAI frontend guidance and subsequently modified,
reorganized, and extended. See the repository LICENSE and NOTICE files.
-->

# Landing Pages, Media, Games, and 3D

Read only when the task involves a landing page, hero, prominent media, generated
imagery, canvas, animation, a game, or 3D.

## Landing pages and heroes

- Make the primary subject recognizable in the first viewport.
- Use an H1 that identifies the product, brand, person, place, category, or literal
  offer. Put detailed value propositions in supporting copy.
- Do not put hero text inside a decorative card by default.
- Avoid a generic split-screen text-and-image composition unless the content or
  established design system makes it appropriate.
- When it does not compromise the primary experience, leave a visual cue on mobile
  and desktop that more content follows.

## Images and illustration

- Use visual assets when they materially improve understanding, identity,
  atmosphere, or gameplay. Do not add imagery merely to satisfy a quota.
- Prefer media that shows the real product, place, object, person, gameplay, or
  meaningful state. Avoid generic stock imagery, overly dark or blurred media, and
  aggressive cropping when users need to inspect the subject.
- Prefer relevant real, searched, or generated bitmap imagery for photographic
  subjects. Use SVG for interface graphics, diagrams, scalable illustrations, and
  game assets when SVG is the appropriate medium.
- Use only assets the project is permitted to use. Avoid fragile hotlinks and
  preserve required attribution or license information.

## Games, canvas, animation, and 3D

- Use proven libraries for established rules, physics, parsing, or AI engines when
  they materially reduce implementation risk.
- Use the project's existing 3D renderer when available; otherwise prefer a mature
  library such as Three.js.
- Make a primary 3D experience spacious and intentional rather than enclosing it
  in an arbitrary decorative preview card.
- Verify that canvas and media output is nonblank, correctly framed, responsive,
  interactive or moving when required, and free from unintended overlap.
- For animation and 3D, verify reduced-motion behavior and avoid motion that makes
  controls, text, or navigation difficult to use.
