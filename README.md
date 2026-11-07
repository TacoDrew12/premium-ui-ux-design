# Premium UI/UX Design Skill

A reusable Agent Skill for designing, building, and polishing modern apps and mini-programs with consistent visual systems, meaningful micro-interactions, responsive layouts, accessible motion, and reliable functionality.

## Repository structure

```text
premium-ui-ux-design/
├── README.md
└── skills/
    └── premium-ui-ux-design/
        └── SKILL.md
```

## What's included

The skill covers:

- Six interaction patterns: completion feedback, checkbox-driven UI updates, stacked card expansion, draggable snap cards and connecting lines, inertial wheel pickers, and circular reveal transitions.
- Six copy-ready implementation prompts.
- A reusable UI/UX design system.
- A four-step design, build, polish, and test workflow.
- A final quality checklist for coding agents.

## Use with an AI agent

Give your agent the `SKILL.md` file or install the skill folder using the agent's supported Agent Skills workflow.

Example instruction:

> Use the `premium-ui-ux-design` skill to build and polish this application. Inspect the existing project before editing, apply only interaction patterns that fit the product, and test the result.

## Publish this repository on GitHub

1. Create a new empty repository on GitHub named `premium-ui-ux-design`.
2. Upload the contents of this folder, keeping the directory structure.
3. Commit the files to the repository's default branch.
4. Share the repository URL with your other AI agent.

After publishing, the skill file will be available at a URL in this format:

```text
https://raw.githubusercontent.com/<YOUR-GITHUB-USERNAME>/premium-ui-ux-design/main/skills/premium-ui-ux-design/SKILL.md
```

Replace `<YOUR-GITHUB-USERNAME>` with your GitHub username. The raw URL can be used by agents that support fetching remote skill files.

## Updating the skill

Edit `skills/premium-ui-ux-design/SKILL.md`, then commit and push the change to GitHub. Agents fetching the raw `main` URL will receive the latest committed version.
