# MySelectMenu

The landing page for the G.E. Shannon family archive. A black-screen menu
with two icons - the old B&W photo book and the old family movies - each a
link to its own separately hosted app. Live at
https://gmshannon99.github.io/MySelectMenu/.

## Structure

- `index.html` - the entire app; a static two-icon menu, no JS.
- `style.css` - layout and hover/focus styling for the menu cards.
- `assets/main-cover.jpg` - the book's cover photo, used as its menu icon.
- `assets/old-movie-camera-icon.jpg` - the old movie camera icon, used as
  the family movies menu icon.
- `assets/favicon.svg` / `assets/favicon.ico` - a black/white outline
  favicon matching the site's theme.

## How the menu works

Each icon is a plain `<a href>` to a different GitHub Pages site - there's
no shared framework or client-side router between this menu and the two
destinations, just full-page browser navigation:

- Book cover -> [GES-OldBW-Book](https://gmshannon99.github.io/GES-OldBW-Book/)
- Movie camera icon -> [FamilyOldMovies](https://gmshannon99.github.io/FamilyOldMovies/)

Both destination apps link back here (`https://gmshannon99.github.io/MySelectMenu/`)
via their own exit actions, the same way - `window.location.href`, not
`window.close()`, since a page reached by real navigation can't reliably
close its own tab.

## Adding another destination

Add another `.menu-card` link inside `.menu-grid` in `index.html`, following
the existing pattern: a `.menu-icon` (either an `<img class="menu-photo">`
for a real thumbnail, or a `<div class="menu-frame">` placeholder box) plus
a `.menu-caption` describing it. No JS changes are needed - the grid layout
and hover effects in `style.css` already apply to any `.menu-card`.

## Local preview

Static files, no build step - open `index.html` directly, or serve the
folder over HTTP:

```
npx serve .
```
