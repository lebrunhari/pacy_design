# Spacing

## Confirmed Tokens

Both apps confirm these values in `PacySetup`:

- `scaleFactor = 1`
- `spacingFactor = 8`
- `borderRadius = 8`

`spacingFactor` exists, but many components use explicit values. Treat the values below as observed patterns, not as a complete centralized API.

## Observed Scale

- 4: handle radius and small internal gaps.
- 8: short gaps, bottom-sheet handle, base radius.
- 12: lateral input/selectable padding and bottom-sheet margin.
- 16: medium gaps, medium/small button padding, space between icon and text.
- 24: mobile lateral padding, card/modal/form padding.
- 32: block separation and small chips/tags/icon buttons.
- 40: medium buttons and medium icon buttons.
- 48: large buttons, large icon buttons, handle width, compact headers.
- 64: mobile app bar and bottom navigation.
- 80: desktop/tablet base app bar and content offsets.
- 96: default scroll gradient in trainer and dashboard info cards.
- 144: default scroll gradient in mobile.

## Radius

- Use `PacySetup.borderRadius` when the target app imports `setup.dart`.
- Radius 8 appears in buttons, cards, inputs, modals, bottom sheets, chips, tags, and skeletons.
- The bottom-sheet handle uses radius 4.

## Touch Targets

- Primary buttons: 48 px on mobile; in trainer they vary by `PacyButtonSize` between 32, 40, and 48.
- Icon buttons: 32, 40, or 48 px with 16, 20, or 24 icons in trainer; mobile also uses 32/40/48 containers.
- Mobile app bars and navigation bars: 64 px, plus safe area when needed.

## Layout And Safe Area

- `pacy_mobile` often uses `MediaQuery.of(context).viewPadding` and `padding` for top/bottom safe areas.
- `pacy_mobile` fixed CTAs use 24 px lateral padding and account for `viewPadding.bottom`.
- `pacy_trainer` native-phone Home uses 24 px lateral padding, top `padding.top + 64 + 24`, and bottom `padding.bottom + 64 + 24`.
- `pacy_trainer` desktop Home uses padding `80,80,80,0` and content with `maxWidth: 1400`.

## Evidence

- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/config/theme/setup.dart:1-5`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/config/theme/setup.dart:1-5`
- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/config/widgets/button.dart:56-73`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/config/widgets/button.dart:21-28`
- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/screens/home/home.dart:102-162`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/config/widgets/button_fixed.dart:16-31`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/config/widgets/button_double_fixed.dart:31-55`
- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/config/widgets/bottom_sheet.dart:32-52`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/config/widgets/bottom_sheet.dart:32-46`
- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/config/widgets/data_table.dart:38-44`
- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/config/widgets/scroll_gradient.dart:4-55`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/config/widgets/scroll_gradient.dart:4-57`
