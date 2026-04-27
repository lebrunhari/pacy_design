# Visual Review Checklist

Use this checklist before finishing any task triggered by `$pacy-ui-specialist`.

## Scope

- The change is visual/UX.
- No Provider, API, auth, model, data contract, or business rule was changed without an explicit request.
- The target app was identified: `pacy_trainer`, `pacy_mobile`, or both.

## Evidence

- Real files were reopened during the task.
- Tokens, widgets, and values used by the change exist in the target app.
- Divergences between apps were preserved or justified.

## Layout

- Safe areas, keyboard, scroll, app bar, and bottom navigation were considered.
- Mobile, tablet, and desktop were handled only when the target app has those contexts.
- Text does not overflow its container or become hidden by fixed overlays.
- Lateral and vertical padding follow observed patterns: 24 px on mobile, 80 px in trainer desktop Home when applicable.

## Visual Hierarchy

- Titles use the appropriate Pacy style (`heading*`, `title`, or `subtitle`).
- Primary text uses `white87`; supporting text uses `white60`; placeholder/disabled text uses `white38`.
- The primary CTA uses the existing `PacyButton` whenever possible.
- Icons use the package adopted by the target app.

## States

- Loading geometry is compatible with the final state.
- Empty and error states do not change the shell without a reason.
- Disabled states reduce visual emphasis.
- Selected/unselected states are clear in tabs, navigation, and lists.
- Hover/pressed/focus were preserved on web/desktop when applicable.
- Snackbars/toasts use duration, blur, icon, and visual semantics from the target app.
- Charts preserve the target app's legend/tooltip/handle and do not change interaction by inference.

## Componentization

- An existing `Pacy*` widget was considered before creating a new component.
- A new component, when necessary, uses local tokens and a simple API.
- There are no isolated styles that duplicate `PacyButton`, `PacyChip`, `PacyTag`, `PacySkeleton`, `PacyAppBar`, `PacyNavigationBar`, bottom sheet, or modal without need.
- Tables, tabs, switch, charts, snackbars, toasts, avatars, and gradients were searched in the target app before creating a local alternative.

## Basic Visual Accessibility

- Visual contrast and readability were checked on dark backgrounds.
- Touch target size follows existing components: 48/40/32 px according to context.
- Important content does not rely only on color when text/icon support is available.
- Small text (`caption`, `overline`) does not carry primary information.
