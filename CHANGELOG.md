# Changelog

## 1.5.3

* Publisher brand icon, marketplace install docs, research links.
* Screenshots wired into README; rebranded docs around the
  AI-comprehension story.
* OIDC trusted publishing (no PAT required).

## 1.4.0

* Semantic modifiers: `*.declaration` bold, `*.readonly` / `*.async` italic,
  `*.deprecated` strikethrough.
* Agent ghost suggestions in muted gray so proposed code never masquerades
  as committed code.
* 19 per-kind `symbolIcon.*` colors, breadcrumb states, sticky-scroll border.
* Full terminal ANSI palette per variant; colorblind variants use
  vermillion-vs-bluish-green for fail-vs-pass.
* Merge-conflict colors (current teal, incoming amber).
* Module/import references now underline + bold.
* Remote / debugging / no-folder status bar states.

## 1.3.0

* New variants: Code Comprehension Light Colorblind and Dark Colorblind
  (Okabe-Ito based, distinct under protanopia, deuteranopia, tritanopia).
* All syntax colors meet WCAG AA 4.5:1.

## 1.2.0

* Six-role palette with de-duplicated hues; bold reserved for definitions.
* Block/doc comments brighter than inline comments.
* Diff, bracket-pair, inlay-hint, CodeLens, sticky-scroll colors.
* Recommended editor settings (IBM Plex Mono first) in README.

## 1.1.x

* Fixed illegible Quick Pick / theme picker selection in Light
  (dark-teal selection + white text, explicit menu/input/button colors).
* Darkened low-contrast syntax to pass WCAG AA.
