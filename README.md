# Google OLED userstyles

Pure black (`#000`) backgrounds for Google Search and Google Calendar, for OLED screens.
Both styles build on Google's own dark theme and turn its greys black, so turn on the dark theme first.

| Style | File | Requires |
|---|---|---|
| Google Search | `google-oled-black.user.css` | Google Settings → Dark theme |
| Google Calendar | `google-calendar-oled-black.user.css` | Calendar Settings → Appearance → Dark |

## Install

1. Install [Stylus](https://github.com/openstyles/stylus).
2. Open the raw file and Stylus offers to install it:
   - [Google Search](https://raw.githubusercontent.com/Dylon99/userstyles/main/google-oled-black.user.css)
   - [Google Calendar](https://raw.githubusercontent.com/Dylon99/userstyles/main/google-calendar-oled-black.user.css)
3. Colours can be changed in the style's options (gear icon in Stylus).

Installed this way, Stylus checks this repo for new versions via `@updateURL`.

## How it works

- **Search:** targets stable IDs (`#rcnt`, `#center_col`, ...) and ARIA landmarks, because Google rotates its class names.
  Wrappers inside the results are made transparent so the black page shows through.
  The search box and buttons stay grey on purpose.
- **Calendar:** overrides the Material 3 colour tokens (`--gm3-sys-color-surface-*`).
  The grid lines are the back layer showing through 1px gaps between day boxes, so that layer uses the
  "Grid lines" colour and the day boxes are never filled. Side effect: the week-number column shows in the line colour.

Every `var()` has a hard-coded fallback, so the styles also work when pasted into Stylus's classic editor.

## When something turns grey again

Google changes its markup now and then. Inspect the grey element, check `background-color` in the
Computed tab, and add the variable or element to the style.
