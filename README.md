# PPT Mastery

**An AI presentation art director for Claude.** Turn a brief into a coherent story, a topic-specific visual identity, slide-by-slide design blueprints, and a quality-controlled PowerPoint handoff.

PPT Mastery is designed to help Claude move beyond generic AI slides. It combines narrative architecture, editorial art direction, composition selection, 100 visual design recipes, custom graphic-background direction, and blueprint-to-render creative review.

> **Important architecture note:** PPT Mastery is the creative director and acceptance authority. It does **not** build PowerPoint files itself. It delegates PowerPoint construction, rendering, editing, PDF export, and technical validation to Anthropic's separate official [PPTX skill](https://github.com/anthropics/skills/tree/main/skills/pptx). Keep that skill enabled alongside PPT Mastery.

## What it brings

- **Narrative architecture:** audience, thesis, story progression, evidence, and presenter handoffs.
- **User-led planning:** slide count, presenter count, palette direction, and image mode.
- **Topic-specific art direction:** original palette routes, typography, graphic language, and backgrounds.
- **100 visual design recipes:** adaptable patterns for compositions, imagery, diagrams, data, typography, and transitions.
- **Slide blueprints:** explicit composition, geometry, focal point, object relationships, and prohibited substitutions.
- **Visual quality control:** rendered-slide review, repetition checks, targeted repair requests, and creative acceptance.
- **Research and evidence discipline:** source-aware claims, qualifications, and factual-image integrity.

## Repository layout

```text
ppt-chef/
├── README.md
└── ppt-mastery/
    ├── SKILL.md
    ├── VERSION.txt
    ├── CHANGELOG.md
    ├── references/
    ├── scripts/
    └── examples/
```

## Install

### Claude Code — user-level install

Clone this repository, then copy the skill folder into Claude Code's user skills directory.

```bash
git clone https://github.com/rishabh514/ppt-chef.git
mkdir -p ~/.claude/skills
cp -R ppt-chef/ppt-mastery ~/.claude/skills/ppt-mastery
```

### Project-level install

Copy `ppt-mastery/` into your project's `.claude/skills/` directory:

```text
your-project/
└── .claude/
    └── skills/
        └── ppt-mastery/
            ├── SKILL.md
            ├── VERSION.txt
            ├── references/
            ├── scripts/
            └── examples/
```

### Windows PowerShell

```powershell
git clone https://github.com/rishabh514/ppt-chef.git
New-Item -ItemType Directory -Force "$HOME\.claude\skills"
Copy-Item -Recurse ".\ppt-chef\ppt-mastery" "$HOME\.claude\skills\ppt-mastery"
```

After installation, start a new Claude Code session and ask Claude to create a presentation. Ensure the official PPTX skill is installed and available too.

## Required companion skill

Install or enable Anthropic's official [`pptx` skill](https://github.com/anthropics/skills/tree/main/skills/pptx). PPT Mastery intentionally does not bundle or duplicate its implementation scripts, PowerPoint tooling, or technical instructions.

Read [the integration contract](ppt-mastery/references/pptx-skill-integration.md) for the exact role boundaries and required design-to-build handoff.

## Example prompts

- "Create a 12-slide university presentation on urban heat islands for a classroom audience."
- "Build a 15-slide market-entry strategy deck for a leadership review."
- "Turn this research report into a detailed technical presentation. Preserve the evidence and caveats."
- "Create a visual, image-free presentation using editable diagrams and shapes."

PPT Mastery will guide the planning choices that are not already specified, then prepare the story, art direction, and build instructions for the official PPTX skill.

## Validate the skill package

The skill includes a dependency-free structural validator:

```bash
python ppt-mastery/scripts/validate_skill.py
```

The optional PPTX layout inspector has its own dependency:

```bash
pip install -r ppt-mastery/scripts/requirements.txt
```

The inspector is supplementary; it does not create or render PowerPoint files and does not replace the official PPTX skill's technical validation.

## Version

Current package version: **6.1.0**. See [the changelog](ppt-mastery/CHANGELOG.md).

## Contributions and feedback

Bug reports, reproducible examples, and improvements to the design recipes or evaluation scenarios are welcome. When reporting a visual issue, include the prompt, Claude model, resulting slide or screenshot, and what the expected composition should have been.

## License

No open-source license has been added yet. Until a license is selected and included, standard copyright applies; public availability does not by itself grant permission to reuse, redistribute, or modify the contents.
