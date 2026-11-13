# Evelyn Simin — Portfolio

Personal portfolio of **Evelyn Simin (沈寶婷)**, Computer Science student at BINUS University.
Pond-and-lotus theme with a light mode ("Morning pond") and a dark mode ("Night pond").

**Live site:** https://my-portfolio-opal-five-81.vercel.app

---

## What is in this repository

| File | What it does |
|---|---|
| `index.html` | The whole website (design, text, projects, experience, CV). |
| `school-photos-binus.js` | Photos for the Bina Nusantara University folder (Education section). |
| `school-photos-dbb.js` | Photos for the Ekayana Dharma Budhi Bhakti High School folder. |
| `og-image.jpg` | The picture shown when the link is shared on LinkedIn, WhatsApp, etc. |
| `vercel.json` | Tells Vercel how long browsers may keep the photos (faster repeat visits). |
| `README.md` | This file. |

Keep all of these files in the **same folder** (the top level of the repo). If a photo
file is missing, that school's folder opens with a "couldn't load the photos" message.

---

## How updates go live

The site is hosted on **Vercel** and connected to this GitHub repository.
Whenever a file here changes, Vercel redeploys automatically (about a minute).

To change a file on github.com:
1. Open the file, click the **pencil** icon, edit, then **Commit changes**.
2. To replace a file with a new version: **Add file → Upload files**, drop the new file
   with the *same name*, then **Commit changes**.
3. To delete a file: open it, click the **⋯** menu, then **Delete file**.

After a deploy, hard refresh the site (Cmd+Shift+R on Mac, Ctrl+Shift+R on Windows).

---

## Easy edits inside `index.html`

Near the top of `index.html` there are two blocks marked **EDIT HERE**.
You can edit them without touching any other code.

### 1. Typing greeting in the hero ("Hello, my name is …")

```js
window.GREETINGS = [
  { t: "Halo, nama saya", l: "id" },
  { t: "你好，我的名字是", l: "zh", c: 1 },
  ...
];
window.TYPE_SPEED = 90;   // typing speed (ms per letter, smaller = faster)
window.ERASE_SPEED = 38;  // erasing speed
window.HOLD_TIME = 1700;  // how long a finished greeting stays
```

- `t` is the text, `l` is the language code.
- Add `c: 1` for Chinese, Japanese or Korean so the right font is used.
- Keep a comma after every line except the last.

### 2. Photo captions in the Education folders

```js
window.SCHOOL_GALLERIES = {
  binus: [
    ["b01", "Inauguration 2024"],
    ...
  ],
  dbb: [ ... ]
};
```

- Each line is `["photo id", "caption"]`. Change the caption text, reorder lines,
  or delete a line to hide a photo.
- The ids (`b01`, `d12`, …) match the photos inside the two `school-photos-*.js` files,
  so don't change the ids.

---

## Things that are *not* a quick edit

- **Adding new photos** — photos are packed into the `school-photos-*.js` files, so new
  ones need those files regenerated (ask Claude, or send the new photos and the school
  they belong to).
- **Updating the CV** — the CV PDF is embedded in `index.html`, so a new CV also needs
  the file regenerated.
- **Changing the Vercel link** — if you rename the Vercel address, update it in the
  `LINK PREVIEW` comment block near the top of `index.html`. It appears in 4 places
  (`canonical`, `og:url`, `og:image`, `twitter:image`).

---

## Things the site depends on

If any of these disappear, part of the site breaks:

- **Old GitHub Pages site** (`velvelvet0306.github.io/Evelyn-Portfolio`) — hosts the
  organization logos and the Creative Portfolio PDF. Keep that repository online.
- **Tailwind CSS** (`cdn.tailwindcss.com`) — the page's styling is generated in the
  browser on every visit.
- **Google Fonts** — the script, serif and Chinese fonts.

---

## Sharing preview

The link preview (title, description and picture) is set by the `meta` tags near the top
of `index.html` and by `og-image.jpg`. LinkedIn and WhatsApp remember old previews for a
while; to refresh LinkedIn, paste the link into
[LinkedIn Post Inspector](https://www.linkedin.com/post-inspector/).

---

## Troubleshooting

| Problem | Fix |
|---|---|
| A school folder says "couldn't load the photos" | Check that `school-photos-binus.js` and `school-photos-dbb.js` are in the repo next to `index.html`. |
| Link preview shows no picture | Check that `og-image.jpg` is in the repo, then refresh the preview (see above). |
| Page looks unstyled for a moment | Normal on slow connections; it is the styling loading. |
| Changes don't show up | Wait a minute for Vercel, then hard refresh the page. |

---

## Built with

HTML, CSS and JavaScript (React and Tailwind CSS in the source project), hosted on Vercel.
Designed and built by Evelyn Simin.
