# Academic Personal Website (Jekyll)

A simple, from-scratch Jekyll site for an academic personal site: About page + CV/Publications page. Built to run on GitHub Pages with no plugins beyond what GitHub Pages supports natively.

## 1. Put it in your repo

Copy everything in this folder into the root of your `username.github.io` repository (or a project repo if you're using a custom domain / project pages — see step 4).

```
git add .
git commit -m "Add Jekyll academic site"
git push
```

GitHub Pages will build and deploy it automatically. Give it a minute or two, then check **Settings → Pages** in your repo for the live URL.

## 2. Edit your content

You won't touch most of the template files. Day-to-day, you'll edit:

| File | What it controls |
|---|---|
| `_config.yml` | Your name, tagline, email, nav links, site URL |
| `index.md` | About page bio text and news items |
| `_data/cv.yml` | Education, experience, awards (rendered automatically on the CV page) |
| `_data/publications.yml` | Your papers — add a new entry to add a new publication |

To add a publication, copy a block in `_data/publications.yml`:

```yaml
- title: "Your Paper Title"
  authors: "**Jane Doe**, Coauthor Name"
  venue: "Where it was published"
  year: 2026
  type: journal   # journal | conference | preprint — controls the colored tab
  links:
    - label: "PDF"
      url: "https://..."
```

Wrap your own name in `**double asterisks**` and it'll render in bold automatically.

## 3. Add a real photo (optional)

Drop a photo at `assets/img/profile.jpg`. If the file doesn't exist, the layout just hides the image box — nothing breaks.

## 4. Add a CV PDF (optional)

The CV page links to `/assets/cv.pdf`. Drop your actual CV PDF at `assets/cv.pdf` to make that link work, or remove the line from `cv.md` if you don't want it.

## 5. Custom domain or project page?

- **User site** (`username.github.io`): leave `baseurl: ""` in `_config.yml`.
- **Project page** (`username.github.io/repo-name`): set `baseurl: "/repo-name"` in `_config.yml`.
- **Custom domain**: add a `CNAME` file with your domain, and update `url` in `_config.yml`.

## 6. Run it locally (optional but recommended)

Requires Ruby installed.

```
bundle install
bundle exec jekyll serve
```

Then visit `http://localhost:4000`. This lets you preview changes before pushing — useful since GitHub's build can take a minute and won't show you Liquid/template errors as clearly as your terminal will.

## Design notes

- Fonts: Newsreader (headings), Inter (body), IBM Plex Mono (dates/labels) — loaded from Google Fonts.
- Colors and spacing are defined as CSS custom properties at the top of `assets/css/main.scss` — change the palette there.
- Publications use a colored left-tab to distinguish journal articles (green), conference papers (brass), and preprints (gray) — adjust the `type` field in `_data/publications.yml` to control this.
