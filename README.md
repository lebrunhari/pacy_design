# Pacy UI Specialist

`pacy-ui-specialist` is a Codex skill for Pacy Flutter UI/UX work. It helps agents review and implement interface changes in `pacy_trainer` and `pacy_mobile` while preserving the real design language already present in those apps.

## Why This Exists

This skill was created to follow the intent of Google's DESIGN.md convention from Stitch: keep design-system guidance in Markdown so both humans and AI agents can read, version, update, and apply it consistently.

The Pacy version adapts that convention for production Flutter development. Instead of a single generic `DESIGN.md` file for AI screen generation, this project uses a Codex skill with focused references, evidence rules, and Flutter-specific guardrails.

## Relationship To Google's DESIGN.md

Google's DESIGN.md convention documents visual rules such as overview, colors, typography, spacing, elevation, components, and practical do's/don'ts. The goal is to give AI design agents a durable source of truth for consistent interface generation.

This skill keeps the same core idea, but changes the shape for Pacy:

- it is organized as a Codex skill, not as a single app-root `DESIGN.md`;
- it is split into focused reference files for progressive disclosure;
- it maps guidance back to real Flutter files through `references/SOURCE_MAP.md`;
- it treats `pacy_trainer` and `pacy_mobile` as related but distinct apps;
- it requires code evidence before turning a pattern into guidance;
- it prioritizes reusable Flutter widgets, local tokens, and existing `Pacy*` components over generic visual descriptions.

Reference: [Google Stitch DESIGN.md overview](https://stitch.withgoogle.com/docs/design-md/overview).

## Pacy Flutter Adaptations

The skill is built around Pacy's actual Flutter implementation:

- dark-first visual system with `PacyColors.background`, `PacyColors.paper`, and `PacyColors.primary`;
- typography based on Pacy's Barlow, Inter, Spline, and related app-specific styles;
- spacing and radius patterns derived from `PacySetup` and observed widget usage;
- component guidance for buttons, cards, app bars, bottom navigation, modals, bottom sheets, inputs, chips, tags, skeletons, charts, and error states;
- responsive rules that preserve the difference between `pacy_trainer` desktop/tablet/native-phone behavior and `pacy_mobile` mobile-first behavior;
- review rules that avoid touching Providers, APIs, auth, models, data contracts, or business logic.

## Project Structure

```text
pacy-ui-specialist/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── PACY_UI_SPECIALIST.md
    ├── SOURCE_MAP.md
    ├── TYPOGRAPHY.md
    ├── COLORS.md
    ├── SPACING.md
    ├── COMPONENTS.md
    ├── BRANDING.md
    ├── RESPONSIVE_PATTERNS.md
    └── VISUAL_REVIEW_CHECKLIST.md
```

## How To Use

Use this skill in Codex when a task is specifically about Flutter UI/UX in `pacy_trainer` or `pacy_mobile`:

```text
Use $pacy-ui-specialist to review this native-phone dashboard layout.
```

The skill should not be used for backend, Providers, APIs, authentication, data models, or business rules.

## Maintenance Rules

- Keep all documentation in English.
- Keep activation metadata concise in `SKILL.md`.
- Put detailed guidance in `references/`.
- Update `SOURCE_MAP.md` whenever the evidence base changes.
- Prefer project-relative paths such as `pacy_trainer/lib/...` and `pacy_mobile/lib/...`.
- Do not promote inferred behavior into official guidance without revalidating the real Flutter code.
- Preserve app divergences instead of forcing one design system across both apps.

## License

This project uses the [Pacy Reference-Only License](LICENSE), identified as `LicenseRef-Pacy-Reference-Only-1.0`.

The license is intentionally custom and proprietary. This project is source-available for reference, but it is not open source.

Allowed:

- read and study the project;
- use it as reference or inspiration to understand how a Pacy-specific Codex skill is structured;
- use, modify, and maintain it inside Pacy-owned or Pacy-authorized projects.

Not allowed without prior written authorization from Pacy:

- copy, adapt, distribute, publish, install, or execute this skill in non-Pacy projects;
- use the skill, documentation, reference files, or substantial portions of them in non-Pacy repositories, products, workflows, tools, or services;
- present a non-Pacy project as endorsed by or affiliated with Pacy.

GitHub may not detect this as a standard open source license. That is expected.
