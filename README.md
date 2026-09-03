# ENAI Summer School Dubai 2026 — Tag Maker

A small web app for participants of the ENAI Summer School in Dubai. Everyone
builds their own name tag and takes away a keepsake image:

1. **Your name** — type it and it appears on the tag.
2. **Pick your cover** — teal, mint or lavender.
3. **Make a tag yours** — add a portrait photo, then place stickers on the tag
   (drag to move, drag the corner handle to resize, the round handle to rotate).
4. **Share your thoughts** — a page of notes, with prompts if you get stuck.
5. **Add your pictures** — choose a Dubai photo from the gallery or upload your
   own, then add a photo from the sessions (one picture or a four-photo collage).
   Photos are cropped inside a fixed frame, Canva style: the frame stays put and
   you drag the picture inside it.
6. **Preview** — the finished keepsake, with the tag resizable by its corner handle.
7. **Share** — download the image, or open LinkedIn / WhatsApp with the caption ready.

## Running it

`index.html` is the whole application. Open the file in a browser, or serve the
folder with any static server:

```bash
python3 -m http.server 8000
```

## Publishing on GitHub Pages

1. Push this repository to GitHub.
2. **Settings → Pages**.
3. **Source:** Deploy from a branch · **Branch:** `main` / `/ (root)` · **Save**.
4. The app is live at `https://<user>.github.io/<repo>/` after a minute or two.

## How it is built

* One self-contained `index.html`: markup, CSS and JavaScript, with every logo,
  sticker and gallery photo embedded as a data URI. There is nothing else to
  deploy — about 93 KB of code and the rest images.
* Two external dependencies, both loaded from a CDN: **Google Fonts**
  (Fraunces + Figtree) and **html2canvas** for the image export. The app needs
  an internet connection for those.
* Work in progress is kept in the visitor's own browser (`localStorage`), so a
  reload does not lose a half-finished tag.
* No backend, no analytics, no accounts. Photos people add never leave their
  device — the keepsake image is rendered locally and saved by the browser.

## Assets and credits

The tag design, layout and copy come from the ENAI Summer School design deck.
Embedded artwork belongs to its respective owners and is included for this
event only:

* ECAI — Centre for Academic Integrity in the UAE (fixed branding on every tag)
* ENAI — European Network for Academic Integrity
* University of Wollongong in Dubai, Canadian University Dubai,
  University of Europe for Applied Sciences, Turnitin, Curve Up, Marwan, Dubai
* Dubai photography supplied by the organisers (Dubai Department of Economy and
  Tourism press images)

These are **not** covered by any open-source licence you may add for the code.
If you make the repository public, check that redistributing the photographs and
partner logos is within the permissions you were given.

The original full-resolution photography and the design PDF stay out of the
repository (see `.gitignore`) — the finished, downsized artwork is already inside
`index.html`.

## Notes for future edits

* Because the images are inlined, every change to `index.html` stores another
  ~6.5 MB in git history. If that becomes awkward, move the images into an
  `img/` folder and reference them by path instead.
* Gallery photos are embedded at 1600 px wide; the keepsake exports each photo
  at roughly 760 × 428 px, so they stay sharp.
* The photo frames use the design's proportions, 35.4 × 18.1.
