# skill-forge

[![conda-forge](https://img.shields.io/badge/prefix.dev%2Fskill--forge-F7CC49?style=flat-square)](https://prefix.dev/channels/melund-skill-forge)
[![pixi-skills](https://img.shields.io/badge/pavelzw%2Fpixi--skills-181717?style=flat-square&logo=github)](https://github.com/pavelzw/pixi-skills)

+> [!NOTE] This is fork of [skill-forge](https://github.com/pavelzw/skill-forge) for building my own hosted/trusted skills.

A collection of agent skills packaged as conda packages and published to the [melund-skill-forge](https://prefix.dev/channels/melund-skill-forge) channel on prefix.dev.

Agent skills are markdown files that give AI coding agents specialized knowledge about libraries, tools, and domains.
They are managed by [pixi-skills](https://github.com/pavelzw/pixi-skills) and can be installed into any pixi project.

For more background on why distributing agent skills through package managers makes sense, check out the blog post [Managing Agent Skills with Your Package Manager](https://pavel.pink/blog/pixi-skills).

## Available skills

| Skill | Package | Description |
|-------|---------|-------------|
| [conda-forge](https://conda-forge.org) | `agent-skill-conda-forge` | conda-forge packaging operations |
| [JOSS Review](https://joss.readthedocs.io) | `agent-skill-joss-review` | Reviewing Journal of Open Source Software submissions |
| [Matplotlib Data Visualization](https://matplotlib.org) | `agent-skill-matplotlib-data-visualization` | Chart design and data storytelling guidelines |
| Presentation Design | `agent-skill-presentation-design` | Slide design and storytelling guidelines |
| Literature Review | `agent-skill-literature-review` | Systematic literature reviews with citation verification |
| Peer Review | `agent-skill-peer-review` | Scientific peer review following academic standards |
| [Polars](https://pola.rs) | `agent-skill-polars` | DataFrame library for fast data manipulation |
| [rattler-build](https://rattler.build) | `agent-skill-rattler-build` | Build conda packages with rattler-build |
| [SQLAlchemy](https://www.sqlalchemy.org) | `agent-skill-sqlalchemy` | Python SQL toolkit and ORM |
| [Google Workspace CLI](https://github.com/googleworkspace/cli) | [92 packages](recipes/gws-cli/SKILLS.md) | Google Workspace services (Gmail, Calendar, Drive, etc.) |
| Human Writing (English) | `agent-skill-human-writing-en` | Human-sounding English writing style for AI agents |
| [Typst](https://typst.app) | `agent-skill-typst` | Modern markup-based typesetting system |

## Usage

### Managing skills with pixi-skills

The recommended way to use agent skills is through [pixi-skills](https://github.com/pavelzw/pixi-skills).
Install it with:

```bash
pixi exec pixi-skills manage
```

This will interactively guide you through adding skills to your project.

### Manual setup

Add the `skill-forge` channel and the desired skill packages to your `pixi.toml`:

```toml
[workspace]
channels = ["conda-forge", "https://prefix.dev/melund-skill-forge"]
platforms = ["linux-64", "osx-arm64", "win-64"]

[dependencies]
polars = ">=1,<2"

[feature.dev.dependencies]
agent-skill-polars = "*"
```
