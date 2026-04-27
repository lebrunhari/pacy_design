# Typography

## Confirmed Fonts

`pacy_trainer`:

- Headings and buttons use `BarlowBold`.
- Interface text uses `InterBold` and `InterRegular`.
- Mono uses `SplineRegular` and `SplineSemiBold`.
- `signature` uses `GreatVibes`.

`pacy_mobile`:

- Headings, feature, highlight, and buttons use `BarlowBold` with `FontWeight.w700` and `FontStyle.italic`.
- Interface text uses `InterBold` and `InterRegular`.
- Mono uses `SplineRegular`.

## Revalidated Scale

`pacy_trainer`:

- `heading1`: 96, `BarlowBold`, height 1.20, letterSpacing -1.5.
- `heading2`: 60, `BarlowBold`, height 1.20, letterSpacing -0.5.
- `heading3`: 48, `BarlowBold`.
- `heading4`: 34, `BarlowBold`.
- `heading5`: 24, `BarlowBold`.
- `heading6`: 20, `BarlowBold`.
- `feature`/`highlight`: 16, `BarlowBold`, height 1.50.
- `title`: 16, `InterBold`.
- `subtitle`: 14, `InterBold`.
- `body`: 14, `InterRegular`.
- `largeButton`: 20, `mediumButton`: 16, `smallButton`: 14.
- `caption`: 12.
- `overline`/`overlineFocus`: 10, letterSpacing 1.0.

`pacy_mobile`:

- `heading2`: 60, `heading3`: 48, `heading4`: 34, `heading5`: 24, `heading6`: 20.
- `feature`/`highlight`: 16.
- `title`: 16, `InterBold`.
- `subtitle`: 14, `InterBold`.
- `largeBody`: 16, `body`: 14.
- `button`: 20, `smallButton`: 14.
- `caption`: 12.
- `overline`/`overlineFocus`: 10.

## Recommended Usage

- Use Barlow headings for titles, highlighted values, metrics, and higher-hierarchy calls.
- Use `title`, `subtitle`, `body`, and `caption` for dense UI, cards, descriptions, and metadata.
- Use `copyWith(color: ...)` to apply visual emphasis without creating isolated styles.
- In buttons, preserve uppercase when using `PacyButton`/`PacyOutlinedButton`; both convert labels to uppercase.
- Do not use `Theme.of(context).textTheme` as the default in Pacy screens when `PacyTypography` is available, except in existing exceptions.

## Divergences And Cautions

- `pacy_mobile` adds `FontWeight` and italics to Barlow; `pacy_trainer` defines the family without those additional attributes.
- `pacy_mobile` has `largeBody`; `pacy_trainer` does not.
- `pacy_trainer` has `mediumButton` and `largeButton`; `pacy_mobile` uses `button`.
- `pacy_mobile.heading1` was revalidated with `fontSize: PacySetup.scaleFactor`, unlike the rest of the scale. Treat it as pending validation before using it.

## Evidence

- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/config/theme/typography.dart:4-25`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/config/theme/typography.dart:4-23`
- `/Users/lebrunhari/StudioProjects/pacy_trainer/lib/config/widgets/button.dart:94-110`
- `/Users/lebrunhari/StudioProjects/pacy_mobile/lib/config/widgets/button.dart:28-40`
