# Pacy UI Specialist

## Product Design Role

This skill acts as Pacy's specialized Product Design layer with solid Flutter fluency. It helps Codex create, review, and adjust screens, widgets, and components according to the real visual and experience patterns already present in `pacy_trainer` and `pacy_mobile`.

Operating priorities:

- typography, visual hierarchy, and readability;
- colors, contrast, and consistent use of dark surfaces;
- spacing, grids, alignment, and touch targets;
- visual states such as loading, disabled, selected, hover, pressed, empty, and error;
- visual componentization and reuse of local widgets;
- Pacy branding, especially the contrast between dark backgrounds and lime primary color;
- mobile/tablet/desktop consistency when the app actually supports those contexts.

The original concept for this initiative was "Pacy Design Specs". The name was changed to `pacy-ui-specialist` to better match Codex skill conventions: a short slug that is usage-oriented and actionable through `$pacy-ui-specialist`.

## Revalidated General Principles

- The visual system is dark-first: `PacyColors.background` uses `0xFF070D26` in both apps, and `PacyColors.paper` uses `0xFF161C33`.
- The primary brand color is `PacyColors.primary`, based on `0xFFDBFF00`, used as an accent and call-to-action color.
- The confirmed base radius is `PacySetup.borderRadius = 8` in both apps.
- The declared spacing scale is `PacySetup.spacingFactor = 8` in both apps, but many widgets use explicit values such as 8, 12, 16, 24, 32, 40, 48, 64, and 80.
- The typography hierarchy combines Barlow for headings/buttons and Inter for interface text; `pacy_mobile` adds weights/italics to several Barlow styles.
- Important interactive components use heights of 48, 40, or 32 px, depending on size and context.
- App bars and bottom navigation use blur, transparency, and scroll-driven animated shadow in mobile flows.

## How To Use For New UI

1. Start with the closest local component: button, card, app bar, input, modal, bottom sheet, chip, tag, skeleton, or error.
2. Use existing tokens from the target app; do not copy tokens from another app without confirming they exist in the destination.
3. Build hierarchy with `PacyTypography` and small `copyWith` adjustments.
4. Preserve the dark background, `paper` surfaces, and `onDarkDivider` separators.
5. On mobile, account for `viewPadding`, 64 px app bars, and 64 px bottom navigation when present.
6. In `pacy_trainer`, verify whether the screen participates in desktop/tablet/native-phone contexts before changing breakpoints or shells.

## When To Review More Rigorously

- A component mixes values from `pacy_trainer` and `pacy_mobile`.
- A new screen creates a button, chip, card, input, or loading state without reusing an existing widget.
- The layout changes behavior across mobile, tablet, and desktop.
- The error/loading/empty state has different geometry from the success state without a clear visual reason.
- Text uses `white38` or `white60` on a dark surface but appears too important for low emphasis.

## Initial Observations - Require Future Validation

- There is no single spacing-token layer beyond `PacySetup.spacingFactor`; the current spacing guidelines are derived from observed usage.
- `pacy_mobile` does not have a revalidated `config/responsive.dart` file; mobile responsiveness was inferred from `MediaQuery`, `LayoutBuilder`, and safe areas.
- `pacy_mobile` defines `heading1` with `fontSize: PacySetup.scaleFactor`, unlike the numeric pattern used by the other headings. Do not treat mobile `heading1` as equivalent to trainer `heading1` without validating the usage screen.
