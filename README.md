# MustBrew — Instagram bio landing page

A Linktree-style page for the cafe. No database, no build step, no dependencies.
Everything is edited in two plain text files.

```
index.html   the page (don't need to touch this)
config.txt   brand, buttons, opening hours, social links
menu.txt     the menu
```

## Editing

Open `config.txt` or `menu.txt` in any text editor, change the text, save,
refresh the page. That's it.

**Add a button** — paste a block like this into `config.txt` (order in the file
= order on the page):

```
[link]
icon     = 🎁
title    = Loyalty Card
subtitle = Buy 9, get 1 free
url      = https://example.com/loyalty
featured = no
```

`featured = yes` makes it the big highlighted button. Use it for the main
order link only.

**Add a menu item** — in `menu.txt`, one item per line:

```
Category Name:
Item name | price | short description
* Item name | price | a "*" marks it as a signature item (shows a ★)
```

Lines starting with `#` are comments. Descriptions are optional.

## Previewing locally

Browsers won't read local text files from a `file://` page, so run a tiny
server from this folder:

```
python3 -m http.server 8000
```

Then open http://localhost:8000

## Putting it online

Upload all four files (keep them in the same folder) to any static host —
Netlify, Vercel, GitHub Pages, Cloudflare Pages, or normal shared hosting.
Drag-and-drop works on Netlify. Then put that URL in the Instagram bio.

## Notes

- Light and dark mode both handled automatically.
- Today's row in Opening Hours is highlighted automatically.
- The "View Full Menu" button uses `url = #menu`, which scrolls down to the
  menu on this same page instead of leaving the site.
- To use an image logo instead of the ☕ emoji, put the file next to
  `index.html` and set `logo = logo.png` in `config.txt`.
