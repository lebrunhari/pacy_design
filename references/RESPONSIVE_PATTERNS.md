# Responsive Patterns

## pacy_trainer

`pacy_trainer` has a formal responsiveness layer:

- `PacyBreakpoint`: `mobile`, `tablet`, `desktop`.
- `tabletMinWidth = 768`.
- `desktopMinWidth = 1024`.
- `nativeTabletMinShortestSide = 600`.
- `isNativePhonePlatform` combines native Android/iOS platform with the mobile breakpoint.

Confirmed patterns:

- Desktop/tablet Home uses a sidebar, its own app bar, centered scroll, and `maxWidth: 1400`.
- Native phone uses `PacyAppBarMobile`, `PacyHomeNavigationBar`, 24 px lateral padding, and 64 px app-bar/bottom-nav offsets.
- Only the Dashboard page is supported in the native-phone Home shell; other pages show unavailable-on-native-phone content.
- Native phone with `shortestSide < 600` is locked to portrait.
- Native tablet below 840 shortest side can be scaled through `PacyTabletViewportScale`.

## pacy_mobile

`pacy_mobile` does not have a revalidated global breakpoint layer. The pattern is mobile-first:

- `Scaffold` with `PacyAppBar`, `PacyNavigationBar`, `extendBody`, and `extendBodyBehindAppBar`.
- Safe areas through `MediaQuery.padding` and `MediaQuery.viewPadding`.
- `LayoutBuilder` appears in screens/forms where available height matters.
- Fixed CTAs account for `viewPadding.bottom` and use a gradient to preserve readability of underlying content.
- App bar and bottom navigation change shadow/blur according to scroll.

## Practical Rules

- Do not apply trainer breakpoints to mobile without making an explicit decision for `pacy_mobile`.
- In `pacy_trainer`, prefer `context.isMobile`, `context.isTablet`, `context.isDesktop`, `context.isTabletUp`, `context.isDesktopUp`, and `context.isNativePhonePlatform` when the file already uses that layer.
- In `pacy_mobile`, preserve safe areas and bottom/top padding before adjusting heights.
- When changing an app bar or bottom navigation, validate behavior at the top, during scroll, and at the end of scroll.
- If the error state should not scroll, preserve the shell geometry and adjust the parent rather than the error component unless the user explicitly asks otherwise.

## Evidence

- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/config/responsive.dart:4-72`
- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/config/platform.dart:5-22`
- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/config/orientation.dart:6-41`
- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/config/widgets/tablet_viewport_scale.dart:20-89`
- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/screens/home/home.dart:53-95`
- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/screens/home/home.dart:98-162`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/screens/home/home.dart:31-77`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/config/widgets/appbar.dart:8-171`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/config/widgets/navigation_bar.dart:5-127`
