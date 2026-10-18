# Build Frontend Experiences

`build-frontend-experiences` is a portable agent skill for implementing
production-quality user interfaces. It guides an AI coding agent to build or
modify frontend experiences that are appropriate to their product domain,
accessible, responsive, secure, deliberately scoped, and verified in a real
browser.

The skill is framework-independent. It can be applied to pages, components,
application workflows, websites, games, and interactive tools without imposing a
particular JavaScript framework or design system.

## What the skill provides

- A clear priority order between user requirements, an existing product system,
  domain needs, and the skill's defaults.
- Guidance for semantic HTML, WCAG 2.2 AA accessibility, responsive behavior,
  interaction states, and safe client-side implementation.
- Domain-aware interface guidance for operational products and more expressive
  experiences.
- Additional guidance for landing pages, generated media, animation, canvas,
  games, and 3D interfaces.
- A verification and handoff workflow covering automated checks, browser testing,
  responsive inspection, accessibility, and honest reporting of unavailable
  checks.

The skill contains instructions only. It has no runtime dependencies and does not
install executable scripts.

## Repository structure

```text
build-frontend-experiences/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── interface-design.md
    ├── landing-media-and-3d.md
    └── verification-and-handoff.md
```

`SKILL.md` contains the core workflow. The reference files are loaded only when
they are relevant, keeping the agent's working context focused. `agents/openai.yaml`
adds optional Codex-specific display metadata; other agents can ignore it.

## Install in Codex

Codex discovers personal skills in `$HOME/.agents/skills` and project skills in
`.agents/skills` inside a repository. See the
[official Codex skills documentation](https://developers.openai.com/codex/skills)
for the current discovery rules.

### Option 1: ask Codex to install it

In a Codex chat, invoke the built-in skill installer with a request such as:

```text
$skill-installer Install the build-frontend-experiences skill from https://github.com/rlapoele/frontend-implementation-skill.git
```

Review the resulting installation path before accepting any changes. Restart
Codex if the newly installed skill does not appear immediately.

### Option 2: install it manually for your user account

The following commands are for macOS and Linux:

```sh
git clone --depth 1 https://github.com/rlapoele/frontend-implementation-skill.git
mkdir -p "$HOME/.agents/skills"
cp -R frontend-implementation-skill/build-frontend-experiences "$HOME/.agents/skills/"
```

Before copying, make sure
`$HOME/.agents/skills/build-frontend-experiences` does not already contain a
version you need to preserve.

### Option 3: install it for one project

From the target project's root directory:

```sh
mkdir -p .agents/skills
cp -R /path/to/frontend-implementation-skill/build-frontend-experiences .agents/skills/
```

Commit the copied skill if the whole team should receive the same instructions.

### Use it in Codex

Invoke the skill explicitly by name:

```text
Use $build-frontend-experiences to implement the account settings page from the approved specification.
```

You can also open Codex's `/skills` menu and select it. Codex may activate the
skill automatically when a request matches its description, but naming it is the
most predictable choice when you specifically want this workflow.

## Install in Claude Code

Claude Code discovers personal skills in `~/.claude/skills` and project skills in
`.claude/skills`. See the
[official Claude Code skills documentation](https://code.claude.com/docs/en/skills)
for current behavior.

### Install it for your user account

If you have not already cloned the repository:

```sh
git clone --depth 1 https://github.com/rlapoele/frontend-implementation-skill.git
```

Then copy the skill:

```sh
mkdir -p "$HOME/.claude/skills"
cp -R frontend-implementation-skill/build-frontend-experiences "$HOME/.claude/skills/"
```

Before copying, make sure
`$HOME/.claude/skills/build-frontend-experiences` does not already contain a
version you need to preserve.

### Install it for one project

From the target project's root directory:

```sh
mkdir -p .claude/skills
cp -R /path/to/frontend-implementation-skill/build-frontend-experiences .claude/skills/
```

Claude Code automatically discovers skills in these locations. If you created a
new top-level skill directory during an active session and it is not detected,
run `/reload-skills` or start a new session.

### Use it in Claude Code

Invoke the skill as a slash command:

```text
/build-frontend-experiences Implement the account settings page from the approved specification.
```

Claude Code may also load it automatically when the task matches the skill's
description.

## Use it with other models or agents

The repository follows the open
[Agent Skills specification](https://agentskills.io/specification): a named
directory containing a `SKILL.md` file, with supporting resources referenced by
relative paths. This gives other tools three practical integration options.

### Agent Skills-compatible tools

Copy the entire `build-frontend-experiences` directory into the skill location
documented by the tool. Preserve the directory structure so references such as
`references/interface-design.md` continue to resolve. The installation path and
invocation syntax are host-specific, so consult that tool's documentation rather
than assuming the Codex or Claude paths apply.

### Models with file or prompt context, but no skill system

Provide `build-frontend-experiences/SKILL.md` as standing developer or project
instructions. Make the `references/` directory available through file access,
retrieval, or additional context, and load only the references named by
`SKILL.md` that apply to the current task.

A suitable generic instruction is:

```text
Follow the attached build-frontend-experiences/SKILL.md while implementing this frontend. Resolve its relative references from the build-frontend-experiences directory, load only the references relevant to the task, and report any verification you cannot perform.
```

This approach supplies the guidance but does not reproduce automatic discovery,
activation, or progressive loading unless the surrounding application implements
those behaviors.

### Custom agent harnesses and APIs

A host application can implement the Agent Skills pattern directly:

1. Index each skill's `name` and `description` from its `SKILL.md` frontmatter.
2. Match the user's task against the description or allow explicit selection.
3. Add the selected `SKILL.md` to the model's instruction context.
4. Resolve linked resources relative to the skill directory and load them only
   when the core instructions call for them.
5. Keep system, platform, security, and explicit user instructions higher in the
   instruction hierarchy than the skill.

Models or hosts without filesystem, command execution, or browser access can
still use the design guidance, but they cannot complete every verification step.
They should state those limitations instead of claiming that checks ran.

## Validate the skill

Tools that implement the Agent Skills reference validator can check the package
with:

```sh
skills-ref validate ./build-frontend-experiences
```

Regardless of tooling, review any third-party skill before installing it. A skill
can influence agent behavior and may reference scripts or external resources;
this repository intentionally contains no executable scripts.
