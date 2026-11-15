# THE UNKNOWN

A bilingual (English / Armenian) discovery app: an animated portal, a swipeable
deck of discoveries, favorites, personal statistics and settings.

The app is split into three files: **`index.html`** (structure), **`style.css`**
(all CSS, animations and responsive layouts) and **`script.js`** (all JavaScript:
data, translations, swipe logic, favorites, statistics, settings). There are no
images, fonts, build steps or runtime dependencies to install. `index.html` is
the entry file (it was named `THE UNKNOWN.html`; it was renamed only so browsers
and servers open it automatically). It contains 32 discoveries: the original 17
plus 15 added ones.

## Project structure

```
THE-UNKNOWN/
├── index.html              # HTML structure (links style.css and script.js)
├── style.css               # all CSS, animations, responsive layouts
├── script.js               # all JavaScript and application logic
├── package.json            # optional: npm scripts for a local server
├── README.md               # this file
├── .gitignore
└── .vscode/
    └── extensions.json     # recommends the Live Server extension
```

## Open it in VS Code

1. Extract `THE-UNKNOWN.zip`.
2. In VS Code: **File → Open Folder…** and choose the `THE-UNKNOWN` folder.
3. When prompted, install the recommended **Live Server** extension
   (or open the Extensions panel and search for "Live Server" by Ritwick Dey).
4. Right-click `index.html` and choose **Open with Live Server**.
   The app opens in your browser and reloads when you save.

## Other ways to run it

- **Directly:** double-click `index.html`. It works from `file://`
  (keep the three files together in the same folder).
- **npm** (Node.js 18+ installed): in the VS Code terminal run
  `npm start`, then open http://localhost:3000
  (this downloads the small `serve` helper on first run via `npx`).
- **Python:** `npm run serve:python` or `python3 -m http.server 3000`,
  then open http://localhost:3000

## Dependencies

None. No `npm install` is needed. Everything runs in the browser. The only
external links are the author's LinkedIn/GitHub in the footer and the source
links in each discovery, which open in new tabs.

## Where to edit

- `style.css`: all CSS (themes, portal, animations, cards, statistics)
- `index.html`: the HTML structure only
- `script.js` holds all the code:

- `const D=[...]`: the discoveries (English + Armenian text, facts, sources)
- `const T={en:{...},hy:{...}}`: interface translations
- `const SC={...}`: the animated SVG scene for each discovery
- `D.push(...)` and `Object.assign(SC,{...})` just after it: the 15 added discoveries and their scenes
- the remaining script: views, swipe logic, statistics, settings

## Data

User progress (likes, skips, language, theme) is stored in the browser's
`localStorage` under the key `unk`. Use **Settings → Copy my data (JSON)** to
back it up.
