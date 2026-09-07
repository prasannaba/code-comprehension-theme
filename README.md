# Code Comprehension Theme

An independent, high-signal theme for agentic coding and fast code reading.
The palette deliberately assigns a visual role to each part of a program:
imports are cyan, control flow is violet, definitions are orange, calls are
yellow-orange, types are magenta, data is green, and literals are amber.

It is intentionally vivid without using a fluorescent background. Calm surfaces
let important syntax stand out immediately.

## Install

Use **Extensions: Install from VSIX...** and choose the included VSIX, then select
one of the four themes:

* **Code Comprehension Light** / **Dark** — the default palette.
* **Code Comprehension Light Colorblind** / **Dark Colorblind** — same
  six roles remapped to colorblind-safe hues (Okabe-Ito based, distinct
  under protanopia, deuteranopia, and tritanopia). Definitions vs calls
  differ by bold as well as hue, so no role depends on red-green
  discrimination alone. All syntax colors still meet WCAG AA 4.5:1.

## Color roles

Six roles, kept distinct so the brain can chunk code at a glance:

| Role | Light | Dark | Used for |
| ---- | ----- | ---- | -------- |
| Behavior (orange) | `#C74313` defs bold / `#A65408` calls | `#FF956B` / `#FFB36B` | functions, calls — verify these first |
| Types (magenta) | `#A92584` bold | `#F29BDE` bold | classes, types |
| Structure (blue) | `#076A8A` / `#0B5F8A` | `#62CFF4` / `#63E6D8` | imports, namespaces, properties |
| Data (green) | `#177A4E`, params italic | `#6FD9A3`, params `#8FD8B8` italic | variables, parameters |
| Literals (amber/green) | `#8A5700` / `#237A3E` | `#F3C969` / `#9BE28C` | constants, strings |
| Control (violet) | `#5F36B8` | `#B79AFF` | keywords, muted on purpose |

Bold is reserved for definitions (functions, types). Calls use color
only, so definitions — the beacons — stand out. Block/doc comments
render brighter than inline comments because intent overviews matter
most when reviewing agent-generated code.

Semantic modifiers add a second signal layer: `*.declaration` is bold
(where things are born vs used), `*.readonly` and `*.async` are italic
(trustworthy constants, execution-order warnings), `*.deprecated` is
struck through. Agent ghost suggestions render in muted gray so
proposed code never masquerades as committed code. Outline icons,
breadcrumbs, terminal ANSI, and merge-conflict colors all follow the
same six roles, so the whole workbench speaks one language.

## Recommended settings for comprehension

The theme only sets colors. Pair it with these editor settings for the
full effect (research-backed: distinct glyphs, ~1.5 line height,
bracket guides, verification aids for AI-generated code):

```json
{
  "editor.fontFamily": "IBM Plex Mono, Lucida Console, Consolas, monospace",
  "editor.fontSize": 14,
  "editor.lineHeight": 22,
  "editor.letterSpacing": 0.2,
  "editor.fontLigatures": false,
  "editor.guides.bracketPairs": true,
  "editor.guides.bracketPairsHorizontal": true,
  "editor.bracketPairColorization.enabled": true,
  "editor.stickyScroll.enabled": true,
  "editor.inlayHints.enabled": "on",
  "editor.codeLens": true,
  "editor.renderWhitespace": "trailing",
  "editor.cursorBlinking": "smooth",
  "editor.find.seedSearchStringFromSelection": "always"
}
```

Why: IBM Plex Mono (primary) has unambiguous `l/I/1 O/0` and clean
Windows hinting; Lucida Console is the zero-install Windows fallback
(no true italic, so the 22px line height plus 0.2 letter spacing keeps
synthesized obliques and dense agent-generated lines readable).
Ligatures stay off so `!=`, `>=` never mislead during verification;
22px line height on 14px type keeps horizontal eye tracking
comfortable; bracket colorization + sticky scroll expose
nesting without background washes; inlay hints and CodeLens surface
types and references so you verify agent code instead of passively
reading it.

## Build

```sh
npx @vscode/vsce package --no-dependencies
```
