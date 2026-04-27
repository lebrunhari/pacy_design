# Branding

## Confirmed Visual Signals

- Pacy uses a dark-first identity with an almost-black navy background (`0xFF070D26`) and `paper` surfaces (`0xFF161C33`).
- The primary brand color is lime (`0xFFDBFF00`), used mainly for CTAs and progress/accent.
- Text and icons on dark surfaces use named white opacities (`white87`, `white60`, `white38`).
- Rounded components use radius 8 as the base.
- Mobile app bars and navigation bars use glass/blur and subtle shadow to keep navigation present without becoming a heavy block.

## Brand Typography

- Barlow appears in headings, highlights, and buttons, communicating athletic energy.
- Inter structures operational UI and reading text.
- Spline appears in mono text; GreatVibes appears as a signature style in trainer.
- On mobile, Barlow is often italic/bold; preserve that character when using existing styles.

## Iconography

- `pacy_trainer` uses `remixicon`.
- `pacy_mobile` uses `flutter_remix`.
- When creating or reviewing UI, use the package already adopted in the target app.
- Navigation bars use outline icons for inactive items and filled icons for selected items when available.
- Avatars use a custom palette of vivid colors derived from the initial, while internal text falls back to `black87` to keep contrast on those backgrounds.
- Charts preserve the brand by using the `primary` line and subtle lime gradient without expanding the main interface palette.

## Visual Tone

- Pacy should feel like a training and coaching product: dark, precise, active, and operational.
- Avoid light or overly colorful palettes that weaken the dark/lime identity.
- Avoid decorative cards without a function; surfaces exist to organize flow, reading, and action.
- Use `primary` sparingly for primary action, accent, or high-importance positive feedback.

## Evidence

- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/config/theme/color.dart:22-45`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/config/theme/color.dart:21-53`
- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/config/theme/typography.dart:4-25`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/config/theme/typography.dart:4-23`
- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/screens/home/widgets/home_navigation_bar.dart:158-178`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/screens/home/home.dart:51-70`
- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/config/widgets/avatar.dart:61-82`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/config/widgets/avatar.dart:79-102`
- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/config/widgets/line_chart.dart:27-36`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/config/widgets/line_chart.dart:33-43`
