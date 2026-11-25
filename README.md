# unslop

A Claude Code skill that helps Claude design and review UI so it looks made by a careful designer, not generated.

It combines three things:

- **UX principles**: proximity, Von Restorff, Tesler's law, progressive disclosure, peak-end rule and more, each with concrete ways to apply it.
- **Craft rules**: typography, color, spacing, buttons, shadows, forms, tables and empty states.
- **Slop tells**: the giveaways of generated design (pills above the headline, three icon cards, sparkle icons, cream backgrounds, made-up stats) and what to do instead.

Claude uses it automatically when building or reviewing interfaces. You can also call it directly with `/unslop`, or say "unslop this".

## Install

Clone it into your personal skills folder:

```sh
git clone https://github.com/frohrer/unslop ~/.claude/skills/unslop
```

On Windows (PowerShell):

```powershell
git clone https://github.com/frohrer/unslop "$HOME\.claude\skills\unslop"
```

Start a new Claude Code session and the skill shows up as `unslop`.

## Update

```sh
git -C ~/.claude/skills/unslop pull
```
