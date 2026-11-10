# Ruined Library

An unofficial, fan-made theme for Obsidian and [Digital Garden](https://github.com/oleeskild/obsidian-digital-garden),
in the spirit of *Library of Ruina*: near-black warm paper, parchment text, thin gold rules, framed
panels, and main-menu-style buttons for a home page. It uses no game art, logo or fonts, and is not
affiliated with Project Moon.

It comes in a dark theme (the intended look) and a light "archive paper" theme.

## Obsidian

Copy `theme.css` and `manifest.json` into `<your vault>/.obsidian/themes/Ruined Library/`, then choose
it under **Settings → Appearance → Themes**.

## Digital Garden

1. Put this repository on GitHub (public), with `theme.css` at the root.
2. In your **garden's** repository, edit `.env` and set:

   ```
   THEME=https://raw.githubusercontent.com/<you>/<repo>/main/theme.css
   BASE_THEME=dark
   ```

   Digital Garden's theme picker lists only community themes, so this line is how a theme of your own
   is set. The plugin reads your garden's `.env` and writes back only the settings you change, so the
   line stays until you pick a different theme in the picker.
3. Let the site rebuild. (The theme is fetched at build time, so rebuild after changing the file.)

## The menu buttons

Make your home note a list of links and add one line of frontmatter:

```markdown
---
cssclasses: ruina-menu
---
# The Archive

*Welcome, guest. Choose a floor.*

- [[Campaign Log]]
- [[The Party]]
- [[Bestiary]]
```

Each list item becomes a button: corner brackets, a diamond marker, and a gold glow that sweeps across
and slides the button in on hover. It works from the keyboard (Tab shows a focus outline), shrinks to
phone width, and turns its motion off for visitors who ask their device for reduced motion.
`example/Home.md` is a starting point.

**On Digital Garden**, the class reaches the page through a setting: in the plugin's settings,
under the frontmatter keys, **CSS classes** defaults to `dg-content-classes`. Either write
`dg-content-classes: ruina-menu` in the note, or change that setting to `cssclasses` so the same line
works in Obsidian and on the site. Then run **Set as Garden Home Page** on the note and publish.

Variants, added beside `ruina-menu` (for example `cssclasses: [ruina-menu, ruina-menu-row]`):

- `ruina-menu-row`: buttons side by side, wrapping to fit.
- `ruina-menu-left`: the stack aligned to the left instead of centred.

## Retuning the colours

The palette is a short list of `--ruina-*` variables at the top of `theme.css`, one set for dark and one
for light. Change a value there and the whole theme follows. If you can compare against the game, the
ones to adjust first are `--ruina-gold`, `--ruina-ink-1` (page) and `--ruina-text`.

## Fonts

Headings use Cinzel if it is installed on the reader's device, otherwise Optima, Palatino or Georgia;
body text uses Palatino or Georgia. The theme makes no font requests, so nothing is sent to a font
service. Install [Cinzel](https://fonts.google.com/specimen/Cinzel) (SIL OFL) on your own devices for
the intended headings; visitors to your garden see the fallback unless you add the font to the site.

## Atlas statblocks

If you also use the Atlas Statblocks garden plugin, its cards are drawn from the same theme
variables and are framed to match.

## Tested

On a Digital Garden site built from the current template, in Chromium: dark and light themes, desktop
and phone width, headings, lists, tasks, tables, code, callouts, tags, blockquotes, link previews,
Atlas statblocks, the menu in column and row form, hover, and keyboard focus. **Not tested inside the
Obsidian app itself.** The colours and typography go through Obsidian's standard variables, so they
should carry over, but the menu buttons draw in Reading view only (Live Preview shows the plain list),
and Obsidian's own interface chrome (settings windows, file explorer) has had no extra styling.

## License

MIT. See `LICENSE`.
