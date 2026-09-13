# Project Page

A static project page for a paper or research project, built on the
[Nerfies](https://github.com/nerfies/nerfies.github.io) template
(Bulma + a little jQuery, no build step).

Published with GitHub Pages: enable Pages for this repo (Settings → Pages →
deploy from branch `main`, folder `/`).

## Layout

```
index.html                     the whole page - edit this
static/css/index.css           page-specific styles (Bulma itself is vendored here too)
static/js/index.js             carousel + interpolation-slider setup and config
static/images/                 favicon, reference stills, social preview image
static/videos/                 teaser and result clips
static/interpolation/stacked/  frames for the interpolation slider
```

## Filling it in

`index.html` is placeholder content end to end; every section is marked with an
HTML comment saying what it is and when to delete it. Work through it top to
bottom:

1. **Head** - title, description, keywords, and the `og:`/`twitter:` social
   preview tags. The social URLs must be absolute, so replace
   `https://USERNAME.github.io/REPO/` with the real address.
2. **Hero** - title, authors, affiliations, and the Paper / arXiv / Video /
   Code / Data buttons. Delete the link blocks you do not need.
3. **Teaser** - drop a short looping clip at `static/videos/teaser.mp4`.
4. **Carousel** - one `.item` per result video in `static/videos/`.
5. **Abstract**, **Video** (replace `VIDEO_ID` with your YouTube id), the
   two-column results section, **Related Links**, and **BibTeX**.

### Interpolation slider

The slider swaps through pre-rendered frames rather than scrubbing a video:

1. Put the frames in `static/interpolation/stacked/`, named `000000.jpg`,
   `000001.jpg`, ... (zero-padded to 6 digits).
2. Set `INTERP_BASE` and `NUM_INTERP_FRAMES` at the top of `static/js/index.js`.
3. Put the two reference stills at `static/images/interpolate_start.jpg` and
   `static/images/interpolate_end.jpg`.

If you don't need it, delete the interpolation block from `index.html` - the JS
skips it when the block is missing.

### Notes

- No analytics are included. Paste your own snippet into the marked spot in
  `<head>` if you want them.
- Keep media small; GitHub Pages serves everything in the repo and large videos
  make the page slow and the repo heavy.

## Previewing locally

```
python3 -m http.server 8000
```

Then open <http://localhost:8000>.

## License

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />
Website borrowed from [NeRFies](https://github.com/nerfies/nerfies.github.io) under a
<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International</a>.
Keep the attribution line in the footer if you reuse this.
