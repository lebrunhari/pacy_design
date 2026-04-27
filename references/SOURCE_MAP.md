# Source Map

Revalidated on 2026-04-25 from the real `pacy_trainer` and `pacy_mobile` files. This list is the primary source for deciding what can be treated as an official guideline for this skill.

## pacy_trainer

Files analyzed:

- `pacy_trainer/lib/config/theme/color.dart`: `PacyColors`, black/white with opacities, `background`, `backgroundBlur`, `overlay`, `paper`, `navigationWidget`, dividers, chart tokens, `primary`, `error`, `warning`, `info`, `success`.
- `pacy_trainer/lib/config/theme/typography.dart`: `PacyTypography` with Barlow, Inter, Spline, and GreatVibes.
- `pacy_trainer/lib/config/theme/setup.dart`: `scaleFactor = 1`, `spacingFactor = 8`, `borderRadius = 8`.
- `pacy_trainer/lib/config/theme/gradient.dart`: `chart` and `scroll` gradients.
- `pacy_trainer/lib/config/theme/elevation.dart`: shadows by elevation 1 to 4.
- `pacy_trainer/lib/config/responsive.dart`: `mobile`, `tablet`, `desktop` breakpoints; `tabletMinWidth = 768`, `desktopMinWidth = 1024`, `nativeTabletMinShortestSide = 600`.
- `pacy_trainer/lib/config/platform.dart`: `isNativeMobilePlatform` and `isNativePhonePlatform`.
- `pacy_trainer/lib/config/orientation.dart`: native phone locks to `portraitUp` when `shortestSide < 600`.
- `pacy_trainer/lib/config/widgets/tablet_viewport_scale.dart`: scales native tablets below `minDesignShortestSide = 840`.
- `pacy_trainer/lib/config/widgets/button.dart`: `PacyButton`, 32/40/48 sizes, uppercase labels, loading dots, danger, and disabled.
- `pacy_trainer/lib/config/widgets/button_outlined.dart`: `PacyOutlinedButton`, 32/40/48 sizes, `white24`/`white12` borders.
- `pacy_trainer/lib/config/widgets/icon_button.dart`: `PacyIconButton`, 32/40/48 sizes and 16/20/24 icons.
- `pacy_trainer/lib/config/widgets/text_field.dart`: `PacyFormBuilderTextField`, dark input, radius 8, keyboard scroll/focus.
- `pacy_trainer/lib/config/widgets/bottom_sheet.dart`: bottom sheet with 48x4 handle, margin 12, paper, radius 8, and shadow.
- `pacy_trainer/lib/config/widgets/modal.dart`: modal overlay, 500 ms guard, adaptive 16/80 padding.
- `pacy_trainer/lib/config/widgets/modal_container.dart`: modal container, 640 px default, paper, radius 8, elevation 2.
- `pacy_trainer/lib/config/widgets/skeleton.dart`: 1000 ms shimmer, `white04`, and `white12` for line.
- `pacy_trainer/lib/config/widgets/error.dart`: centered error, `title/body` text, code chip, and CTA.
- `pacy_trainer/lib/config/widgets/chip.dart`: 32 px chip, horizontal padding 12, `white04`, `onDarkDivider` border.
- `pacy_trainer/lib/config/widgets/tag.dart`: 32 px tags with alpha 0.1 and `primary/info/success/warning/alert/legend/error` enum.
- `pacy_trainer/lib/config/widgets/tabbar.dart`: `PacyTabBar`, `primary` indicator, `onDarkDivider` divider, `white87` selected, `white60` unselected.
- `pacy_trainer/lib/config/widgets/switch.dart`: `PacySwitch`, selected track with white alpha 0.16, disabled `white04`, `white87` thumb.
- `pacy_trainer/lib/config/widgets/snackbar.dart`: top snackbar, maxWidth 336, radius 8, blur 72, 5 s duration, standard/success/info/error types.
- `pacy_trainer/lib/config/widgets/toast.dart`: top toast, maxWidth 320, pill radius 96, 1400 ms duration, blur 72.
- `pacy_trainer/lib/config/widgets/data_table.dart`: operational table with row/header 64, footer 80, skeletons, and empty state.
- `pacy_trainer/lib/config/widgets/line_chart.dart`: line chart with `primary`, chart gradient, tooltip radius 8, and click cursor.
- `pacy_trainer/lib/config/widgets/avatar.dart`: circular avatar or image, initials, palette derived from initial, and 200 ms fade.
- `pacy_trainer/lib/config/widgets/scroll_gradient.dart`: scroll fade with default height 96.
- `pacy_trainer/lib/config/widgets/app_bar.dart`: desktop/tablet app bar with blur 16, base height 80 or 160.
- `pacy_trainer/lib/config/widgets/app_bar_mobile.dart`: 64 px mobile app bar, blur 24, and scroll-animated background.
- `pacy_trainer/lib/screens/home/home.dart`: desktop shell with sidebar and maxWidth 1400; native-phone shell with 24 px lateral padding and 64 px app bar/bottom nav.
- `pacy_trainer/lib/screens/home/widgets/home_navigation_bar.dart`: 64 px mobile bottom navigation with animated blur/shadow.
- `pacy_trainer/lib/screens/dashboard/widgets/dashboard_card.dart`: `paper` card, radius 8, header 64, desktop FAQ modal, mobile FAQ screen.

Derived conceptual guidelines:

- Typography: Barlow for impact and buttons; Inter for interface; Spline for mono; GreatVibes appears as a signature.
- Colors: dark-first, lime as primary, named white/black opacities, semantic states through `MaterialColor`.
- Spacing: base scale 8, with recurring 12/16/24/32/40/48/64/80 usage.
- Components: use `Pacy*` widgets before creating loose containers.
- Responsiveness: `pacy_trainer` has real breakpoints and clear differences between web/mobile/tablet/native phone.
- Visual states: loading through `PacySkeleton` and `LoadingAnimationWidget`, errors with CTA and code, nav/appbar with scroll state.
- Basic visual accessibility: prefer `white87` for primary text, `white60` for support, `white38` for disabled/placeholder.

## pacy_mobile

Files analyzed:

- `pacy_mobile/lib/config/theme/color.dart`: `PacyColors`, dark palette, `base`, `primary`, `error`, `warning`, `info`, `success`.
- `pacy_mobile/lib/config/theme/typography.dart`: `PacyTypography` with italic/bold Barlow, Inter, and Spline.
- `pacy_mobile/lib/config/theme/setup.dart`: `scaleFactor = 1`, `spacingFactor = 8`, `borderRadius = 8`.
- `pacy_mobile/lib/config/theme/gradient.dart`: `chart` and `scroll` gradients, with `stops` on scroll.
- `pacy_mobile/lib/config/theme/elevation.dart`: same shadows by elevation 1 to 4.
- `pacy_mobile/lib/main.dart`: dark theme, edge-to-edge, status/navigation bar.
- `pacy_mobile/lib/config/widgets/button.dart`: 48 px `PacyButton`, uppercase, danger, loading, and disabled.
- `pacy_mobile/lib/config/widgets/button_outline.dart`: `PacyOutlinedButton`, 48 px or 24x12 padding.
- `pacy_mobile/lib/config/widgets/button_fixed.dart`: fixed CTA with gradient, 24 px lateral padding, and bottom safe area.
- `pacy_mobile/lib/config/widgets/button_double_fixed.dart`: two fixed CTAs with spacing 16 and gradient 280.
- `pacy_mobile/lib/config/widgets/icon_button.dart`: 32/40/48 icon buttons with optional background.
- `pacy_mobile/lib/config/widgets/form_builder_textfield.dart`: dark input, radius 8, required label, error, helper/counter.
- `pacy_mobile/lib/config/widgets/selectable_text_field.dart`: Android/iOS selectable input, bottom sheet, and wheel chooser.
- `pacy_mobile/lib/config/widgets/bottom_sheet.dart`: bottom sheet with 48x4 handle, margin 12, paper, radius 8, and shadow.
- `pacy_mobile/lib/config/widgets/dialog_fullscreen.dart`: fullscreen dialog with 400 ms vertical slide.
- `pacy_mobile/lib/config/widgets/skeleton.dart`: 1000 ms shimmer, `white04`, and `white12`.
- `pacy_mobile/lib/config/widgets/error.dart`: error screen with app bar, padding 48, code chip, and fixed CTA.
- `pacy_mobile/lib/config/widgets/chip.dart`: 32 px chip, padding 12, `white04`, `onDarkDivider` border.
- `pacy_mobile/lib/config/widgets/tag.dart`: 32 px tags with `primary/info/success/warning/error` enum.
- `pacy_mobile/lib/config/widgets/tabbar.dart`: `PacyTabBar`, `paper` container, `white87` indicator, radius 8, 150 ms animation.
- `pacy_mobile/lib/config/widgets/snackbar.dart`: top snackbar, margin 8, radius 8, blur 48, dismissible, normal/alert/error/success types.
- `pacy_mobile/lib/config/widgets/line_chart.dart`: line chart with `primary`, chart gradient, custom handle/bubble, and external touch.
- `pacy_mobile/lib/config/widgets/avatar.dart`: avatar with custom radius, one- or two-letter initials, palette derived from initial, and 200 ms fade.
- `pacy_mobile/lib/config/widgets/scroll_gradient.dart`: scroll fade with default height 144 plus bottom safe area.
- `pacy_mobile/lib/config/widgets/appbar.dart`: 64 px app bar with blur 24 and scroll-animated background.
- `pacy_mobile/lib/config/widgets/navigation_bar.dart`: 64 px bottom navigation with animated blur/shadow.
- `pacy_mobile/lib/config/widgets/workout_card.dart`: clickable `paper` card, alpha, radius 8, padding 24, and touch states.
- `pacy_mobile/lib/screens/home/home.dart`: mobile home with `PacyAppBar`, `PacyNavigationBar`, `extendBody`, and three tab pages.

Derived conceptual guidelines:

- Typography: italic/bold Barlow and Inter form the main hierarchy; do not assume full equivalence with trainer.
- Colors: shares the dark base and lime, but has additional tokens such as `base` and divergences in `overlay`/`warning`.
- Spacing: mobile UI heavily uses 24 px lateral padding, safe areas, and fixed buttons.
- Components: prefer mobile widgets (`PacyButtonFixed`, `PacyButtonDoubleFixed`, `PacyNavigationBar`, `PacyAppBar`).
- Responsiveness: the mobile app has no global breakpoints; it uses safe areas, `MediaQuery`, `LayoutBuilder`, and viewport sizes.
- Visual states: focus on loading skeletons, scroll-driven appbar/nav, fixed button, and fullscreen error screens.

## Confirmed Divergences

- `pacy_trainer` has `PacyResponsive` and `PacyPlatform`; `pacy_mobile` has no revalidated global equivalent.
- `pacy_mobile` defines `PacyColors.base`; `pacy_trainer` does not define that token.
- `pacy_trainer` defines `backgroundBlur`, `chartBgColor`, and `chartTooltipColor`; `pacy_mobile` did not confirm these tokens.
- `pacy_trainer` has `PacyButtonSize` and `PacyOutlinedButtonSize`; `pacy_mobile` has a simpler button API.
- Tags diverge: trainer has `alert` and `legend`; mobile does not.
- `PacySkeleton` API diverges: trainer uses `borderRadius/customRadiusSize`; mobile uses `enabledBorderRadius/borderRadius`.
- `PacyTabBar` diverges: trainer uses `TabController` and `primary` indicator; mobile uses a `white87` pill indicator calculated from screen width.
- `PacySnackBar` diverges in types, blur, and dismissibility; do not port enum or margin without adapting.
- `PacyAvatar` diverges: trainer is circular by default; mobile accepts custom `radius` and can become a rounded rectangle.
