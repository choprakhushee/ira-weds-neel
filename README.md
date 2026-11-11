# Ira & Neel · Wedding Invitation

A floral "Secret Garden" wedding invitation website by **Aamantran Atelier**.

Live: https://choprakhushee.github.io/ira-weds-neel/

The page is one `index.html` plus painted artwork in `assets/art/`. The painted couple, floral arch,
corner bouquets and the five event flowers are AI watercolour art made in Canva. The garlands, flower
confetti, flower swing, flower elephant and peacock, petal butterflies, hills and music are drawn or
generated in the browser. If any painted image is missing, a hand-drawn SVG version is shown instead.

## Edit the details

Open `index.html` and edit the `CONFIG` object at the top of the `<script>`: names, parents, dates,
events, story, RSVP number and message, contacts, colours and map links.

The share preview (what WhatsApp shows) comes from the `og:` and `twitter:` tags in `<head>`.
WhatsApp can't run JavaScript, so update those by hand for a new couple.

## Personalised guest links

Add `?guest=` to the link. The name appears on the opening doors and in the WhatsApp RSVP message.

- https://choprakhushee.github.io/ira-weds-neel/?guest=Sharma%20Family
- https://choprakhushee.github.io/ira-weds-neel/?guest=Ananya%20%26%20Rohan

Use `%20` for spaces and `%26` for `&`.

## Swap in your own photos or artwork

All painted images are listed in `CONFIG.images` (and each event's `image`) near the top of `index.html`.
Replace a file in `assets/art/` with your own using the same name, or point the path at a new file.

| File | Shown in | Suggested size |
|---|---|---|
| `assets/art/couple.webp` | Under the hero arch, the sign-off and the share image | about 800 × 1300, transparent, full length |
| `assets/art/couple-bust.webp` | The Bride & The Groom portrait (arched frame) | about 700 × 670, head and shoulders |
| `assets/art/arch.webp` | The floral arch around the couple | about 1000 × 1333, transparent, open centre |
| `assets/art/bouquet-tl.webp`, `bouquet-br.webp` | Corner bouquets on the doors, hero, portrait, RSVP card and desktop backdrop | about 760 × 780, transparent |
| `assets/art/jasmine.webp`, `marigold.webp`, `orchid.webp`, `rose.webp`, `lily.webp` | Each event card | about 640 wide, transparent |
| `assets/art/bfly-pink-l.webp` / `-r.webp` (also `peach`, `lilac`) | The flying butterflies, as left and right wing halves split down the body | about 120 × 160 each, transparent |

Transparent PNG or WebP both work. For a normal photo of the couple (not a cut-out), set
`images.couple.fit` to `"cover"`. Keep each file under about 400 KB.

The flower garlands, confetti and animals take their colours from `CONFIG.garland`, `CONFIG.confetti`
and each event's `garland` list.

## Open it locally

```
python3 -m http.server 8000
```

Then open http://localhost:8000/

## Redraw the share image

`index.html?og` draws the 1200 × 630 share card from `CONFIG` and the painted art. To save it as
`og-image.png` and `og-image.svg` (needs Node and Playwright):

```
python3 -m http.server 8765
node tools/export-og-image.js
```

## Publish on GitHub Pages

Settings → Pages → Deploy from a branch → `main` → `/ (root)` → Save. The site is live about a minute later.
