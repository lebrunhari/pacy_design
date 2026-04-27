# Components

## Before Creating A New Widget

Look first for a `Pacy*` component in the target app. Components with the same name can have different APIs between `pacy_trainer` and `pacy_mobile`, so confirm the signature and behavior before reusing them.

## Buttons

`pacy_trainer`:

- `PacyButton` has `small`, `medium`, and `large` sizes with 32, 40, and 48 heights.
- It uses `PacySetup.borderRadius`, `PacyColors.primary` for active state, `PacyColors.error` for danger, and `PacyColors.white04` for disabled.
- The label becomes uppercase and loading uses `LoadingAnimationWidget.staggeredDotsWave`.
- `PacyOutlinedButton` mirrors 32/40/48 sizes, with `white24` active border and `white12` disabled border.

`pacy_mobile`:

- `PacyButton` is 48 px, uppercase, with `primary`, danger, and disabled on `paper`.
- `PacyOutlinedButton` can be expanded with height 48 or non-expanded with 24x12 padding.
- `PacyButtonFixed` and `PacyButtonDoubleFixed` position CTAs at the bottom with gradient and safe area.

## Icon Buttons

- Both apps use 32/40/48 sizes.
- `pacy_trainer` calculates 16/20/24 icons and uses `white87` active, `white38` disabled.
- `pacy_mobile` allows `backgroundColor`, `color`, and `disabledColor`; its default is darker because it also appears on light surfaces such as the webview header.

## Inputs

`pacy_trainer`:

- `PacyFormBuilderTextField` has `white04` fill, radius 8, `onDarkDivider` border, `white87` focus, `error.shade400` error, helper/caption, and keyboard scroll/focus handling.

`pacy_mobile`:

- `PacyFormBuilderTextField` has a similar visual pattern, optional required label, and `keyboardAppearance: Brightness.dark`.
- `PacySelectableInput` uses Material on Android, Cupertino on iOS, height 48, bottom sheet, and wheel chooser.

## Cards

`pacy_trainer`:

- `PacyDashboardCard` uses `paper`, radius 8, header 64, divider, `white87` title, period button/icon, and FAQ behavior that differs between mobile and modal.
- The card has an internal centered error fallback.

`pacy_mobile`:

- `PacyWorkoutCard` uses `Material` with `Color.alphaBlend(PacyColors.white04, PacyColors.paper)`, radius 8, padding 24, InkWell, and touch states.
- The day card can receive a `white87` border when `canHighlight`.

## Modals And Bottom Sheets

- Bottom sheets in both apps use overlay, transparent background, 48x4 handle, margin 12, `paper` surface, radius 8, and shadow.
- `pacy_trainer` also has `PacyModalSheet`, `PacyModalSheetContainer`, and keyboard-aware layout for larger modals.
- `pacy_mobile` has `showPacyFullscreenDialog` with a 400 ms vertical slide.

## App Bars And Navigation Bars

- Mobile app bars in both apps have toolbar 64, uppercase `heading6` title, blur 24, and `navigationWidget` background with alpha 0.8 while scrolling.
- Mobile bottom navigation in both apps has height 64, hidden labels, `white38` icons, and `white87` selected icons.
- `pacy_trainer` also has a desktop/tablet app bar with base height 80 or 160, blur 16, and divider.

## Visual States

- `PacySkeleton` uses shimmer 1000 ms, `white04` for blocks, and `white12` when height is 1.
- Error states use title, description, code, and CTA when applicable.
- Disabled should reduce emphasis, generally to `white38` or `white04`/`paper` background.
- Selected uses `white87`; unselected usually uses `white38`.
- Tabs diverge by app: trainer uses a `primary` indicator in `TabBar`; mobile uses a `white87` pill indicator over a `paper` surface.
- Snackbars use top flushbar, circular 24 icon, radius 8, blur, and semantic colors.
- Toast exists in trainer as a short-lived top success pill with radius 96.

## Tables And Charts

- `pacy_trainer` has `PacyDataTable` for operational surfaces: header/data row 64, footer 80, `paper`, skeletons, and empty state with icon.
- Line charts in both apps use `PacyColors.primary`, `PacyGradient.chart`, 300 ms curve, and 2 px line.
- `pacy_trainer` line chart has an internal tooltip with radius 8 and click cursor.
- `pacy_mobile` line chart uses custom handle and bubble, with external touch callback.

## Avatars

- Both apps have `PacyAvatar` with remote image, placeholder/error assets, fade 200 ms, initials, and a palette derived from the first letter.
- `pacy_trainer` is circular by default.
- `pacy_mobile` accepts a custom `radius` and can create a rounded-rectangle, non-circular avatar.

## Evidence

- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/config/widgets/button.dart:7-120`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/config/widgets/button.dart:6-44`
- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/config/widgets/button_outlined.dart:7-136`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/config/widgets/button_outline.dart:6-44`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/config/widgets/button_fixed.dart:5-37`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/config/widgets/button_double_fixed.dart:5-63`
- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/config/widgets/icon_button.dart:4-54`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/config/widgets/icon_button.dart:5-67`
- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/config/widgets/text_field.dart:8-288`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/config/widgets/form_builder_textfield.dart:8-156`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/config/widgets/selectable_text_field.dart:40-190`
- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/screens/dashboard/widgets/dashboard_card.dart:15-384`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/config/widgets/workout_card.dart:14-105`
- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/config/widgets/bottom_sheet.dart:5-73`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/config/widgets/bottom_sheet.dart:7-67`
- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/config/widgets/skeleton.dart:6-49`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/config/widgets/skeleton.dart:5-62`
- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/config/widgets/error.dart:7-67`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/config/widgets/error.dart:9-64`
- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/config/widgets/tabbar.dart:6-35`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/config/widgets/tabbar.dart:5-69`
- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/config/widgets/switch.dart:4-22`
- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/config/widgets/snackbar.dart:7-87`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/config/widgets/snackbar.dart:7-99`
- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/config/widgets/toast.dart:7-47`
- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/config/widgets/data_table.dart:13-233`
- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/config/widgets/line_chart.dart:6-73`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/config/widgets/line_chart.dart:7-85`
- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/config/widgets/avatar.dart:5-83`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/config/widgets/avatar.dart:5-103`
