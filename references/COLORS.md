# Colors

## Confirmed Base Palette

Common to both apps:

- `black`: `0xFF070D26`
- `white`: `0xFFFAFBFF`
- `background`: `0xFF070D26`
- `paper`: `0xFF161C33`
- `navigationWidget`: `0xFF0B102B`
- `onDarkDivider`: `0x1FFAFBFF`
- `onLightDivider`: `0x1F070D26`
- `primary`: `0xFFDBFF00`
- `error`: semantic red
- `warning`: semantic yellow/orange
- `info`: semantic blue
- `success`: semantic green

## Text Emphasis

- `white87`: primary text on dark backgrounds.
- `white60`: relevant secondary text.
- `white38`: placeholder, disabled, or low emphasis.
- `white24`/`white12`/`white04`: dividers, borders, subtle fills, and overlays.
- `black87`: text over `primary`.

## Surfaces

- Use `PacyColors.background` for screen backgrounds.
- Use `PacyColors.paper` for cards, bottom sheets, modals, and elevated surfaces.
- Use `PacyColors.white04` for subtle fills in chips, inputs, skeletons, and internal overlays.
- Use `PacyColors.onDarkDivider` for discreet lines/borders on dark surfaces.

## Semantic States

- Primary: `PacyColors.primary` for the main CTA and brand accents.
- Error: `PacyColors.error` or shades, especially in danger buttons and input errors.
- Warning, info, and success appear as `MaterialColor` values in both apps.
- Tags use semantic color with alpha 0.1 as fill and the full color for text.

## Confirmed Divergences

- `pacy_trainer` defines `black08`, `backgroundBlur`, `chartBgColor`, and `chartTooltipColor`; `pacy_mobile` did not confirm these tokens.
- `pacy_mobile` defines `base`; `pacy_trainer` did not confirm this token.
- `overlay` differs: trainer uses `0xCC070D26`; mobile uses `0xDE070D26`.
- `warning` has a different base value: trainer `0xFFFEE83D`; mobile `0xFFFDB900`.
- Tags diverge: trainer has `alert` and `legend`; mobile does not.

## Practical Rules

- Do not create a new color for a state without checking whether `primary/error/warning/info/success` covers the case.
- Avoid pure white or pure black outside Pacy tokens.
- On dark backgrounds, do not use `white38` for primary information.
- When porting a component between apps, verify that the token exists in the destination app.

## Evidence

- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/config/theme/color.dart:3-98`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/config/theme/color.dart:3-106`
- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/config/widgets/tag.dart:57-73`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/config/widgets/tag.dart:37-49`
