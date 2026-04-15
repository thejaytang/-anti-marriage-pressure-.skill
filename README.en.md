# anti-marriage-pressure-skill

[![简体中文](https://img.shields.io/badge/README-%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87-1f6feb?style=for-the-badge)](README.zh-CN.md)
[![English](https://img.shields.io/badge/README-English-111827?style=for-the-badge)](README.en.md)

An open-source skill for Codex, Claude Code, and other Agent Skills compatible tools that helps
users handle marriage pressure, forced matchmaking, fertility pressure, and intrusive questions
about relationship timelines.

## What This Skill Does

- Defaults to `defense mode` for calm, firm, spoken boundary-setting
- Switches to `attack mode` only when the user explicitly asks for a sharper reply
- Forces a safety-first override when the situation points to coercion, threats, or forced marriage risk
- Supports both Chinese and English outputs

This is not just a clapback pack. It is a controlled language tool: hold the boundary first,
then decide how sharp the reply should be.

## Installation

### Codex

```bash
git clone https://github.com/thejaytang/-anti-marriage-pressure-.skill.git anti-marriage-pressure-skill
cp -R anti-marriage-pressure-skill/anti-marriage-pressure ~/.codex/skills/
```

### Claude Code

```bash
git clone https://github.com/thejaytang/-anti-marriage-pressure-.skill.git anti-marriage-pressure-skill
cp -R anti-marriage-pressure-skill/anti-marriage-pressure ~/.claude/skills/
```

If you later rename the repository to `anti-marriage-pressure-skill`, replace the clone URL with
the new repository URL. The installed skill directory stays `anti-marriage-pressure/`.

## Usage Examples

### Defense Mode

```text
Use $anti-marriage-pressure in defense mode for:
"You're getting older. Why aren't you married yet? Your family must be worried."
```

### Attack Mode

```text
Use $anti-marriage-pressure in attack mode and make it sharper:
"Other people's kids are already in school. Why are you still not settled?"
```

### English Output

```text
Use $anti-marriage-pressure to draft a short English reply to:
"When are you getting married? Your parents must be worried."
```

## Before And After Examples

### Example 1: Dinner Table Marriage Pressure

Prompt:

> "You're getting older. Why aren't you married yet? Your family must be worried."

Typical plain-model answer:

> "I understand that my family is concerned, and I know they mean well. I will think carefully about my life plans and hope everyone can give me some time."

With the skill, defense mode:

> "I know you're concerned, but I will make that decision myself, and I am not discussing it today."

With the skill, attack mode:

> "Your urgency is your emotion, not my deadline. I am not treating marriage like a task I owe other people."

### Example 2: Comparison Pressure

Prompt:

> "Other people's kids are already in school. Why are you still not settled?"

Typical plain-model answer:

> "Everyone moves at a different pace in life, and I believe the right person will come at the right time."

With the skill, defense mode:

> "Other people's timelines are not my standard. That comparison is not helpful to me."

With the skill, attack mode:

> "Other people's marriages are their answer sheets, not a template for me to copy. Using comparison as pressure is not advice. It is overreach."

### Example 3: Fertility Pressure After Marriage

Prompt:

> "You're already married. When are you having kids? It'll be too late if you wait."

Typical plain-model answer:

> "Having children is an important decision, and we will think about it based on our own situation. Thank you for your concern."

With the skill, defense mode:

> "Family planning is private, and I am not answering that question. Please stop asking."

With the skill, attack mode:

> "Treating someone else's reproductive plan like a public topic is already intrusive. Your concern does not give you permission to question me."

## Default Output Shape

Unless the user asks otherwise, the skill returns:

- one primary reply
- two or three escalating alternatives
- one closer or redirect
- one exit/help line when the situation sounds risky or persistent

## Safety Boundaries

The skill will not use attack mode when the prompt suggests:

- forced marriage or coercive engagement
- threats, control of movement, passport, phone, or money
- pressure involving a minor
- immediate physical or domestic safety concerns

In those cases it switches to practical, safety-first guidance.

## Repository Layout

```text
.
├── README.md
├── README.zh-CN.md
├── README.en.md
├── LICENSE
└── anti-marriage-pressure/
    ├── SKILL.md
    ├── agents/openai.yaml
    └── references/
        ├── principles.md
        ├── scenarios.md
        └── style-notes.md
```

## Method

The project uses two evidence layers:

- authoritative guidance for boundaries, **assertive communication**, **de-escalation**, and forced marriage risk
- public social-platform pattern distillation for tone, pacing, escalation, and common scenarios

Social-platform material is summarized into patterns only. It is not copied into the repository.

## License And Disclaimer

This project is released under `MIT`.

The skill offers communication support, not legal advice, crisis counseling, or emergency
protection. If the situation has moved beyond ordinary social pressure, real-world safety support
comes first.
