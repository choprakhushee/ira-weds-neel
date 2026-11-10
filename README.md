# Ira & Neel · Wedding Invitation

A floral "Secret Garden" wedding invitation website by **Aamantran Atelier**.

Live: https://choprakhushee.github.io/ira-weds-neel/

Everything is in one `index.html`: the flowers, the illustrated bride and groom, the Nilgiri hills and
the music are all drawn or generated in the browser. The only outside resource is Google Fonts.

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

## Real photos or illustrations (optional)

Put files with these names in `assets/`. They replace the drawings automatically, and any missing
file keeps its drawing. The browser console shows a "404" line for each empty slot; that is expected.

| File | Shown in | Suggested size |
|---|---|---|
| `couple.png` | Under the hero arch and in the sign-off wreath | 1000 × 1500, transparent PNG, full length |
| `bride.png`, `groom.png` | The oval portraits | 800 × 1100, head and shoulders in the upper half |
| `mehendi.png`, `haldi.png`, `sangeet.png`, `wedding.png`, `reception.png` | Inside each event's arch | 900 × 1000 |

For a normal photo of the couple (not a cut-out), set `images.couple.fit` to `"cover"` in `CONFIG`.
Keep each file under about 400 KB.

## Open it locally

```
python3 -m http.server 8000
```

Then open http://localhost:8000/

## Redraw the share image

`index.html?og` draws the 1200 × 630 share card from `CONFIG`. To save it as `og-image.png` and `og-image.svg`
(needs Node and Playwright):

```
python3 -m http.server 8765
node tools/export-og-image.js
```

## Publish on GitHub Pages

Settings → Pages → Deploy from a branch → `main` → `/ (root)` → Save. The site is live about a minute later.
