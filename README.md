# Consulting site

A minimal Jekyll site built for GitHub Pages' **native** build — no GitHub
Actions workflow, no theme gem, no JavaScript. Push to `main` and Pages
rebuilds.

> All names, figures, and engagements in the content are **placeholder**
> material written to read realistically. Replace them before the site goes
> anywhere public under a real identity.

## Editing content in the browser

Every page's content lives in Markdown — front matter for structured data,
body text for prose — so it can be edited entirely from the GitHub web editor
(press `.` in the repo, or click the pencil on any file).

| File | What lives there |
|---|---|
| `_config.yml` | Site title, name, email, LinkedIn URL, location |
| `index.md` | Home. `areas:` in front matter = the three practice areas |
| `about.md` | Bio and approach — all body prose |
| `projects.md` | `cases:` in front matter = the four case study cards |
| `speaking.md` | `talks:` in front matter = the talk list |
| `contact.md` | `channels:` in front matter = email / LinkedIn / location |

Adding a talk means adding a `- date: / title: / event: / venue:` block to the
`talks:` list. Nothing else has to change. Same pattern for cases and areas.

Navigation is generated from each page's `nav_order` and `nav_title`, so a new
page joins the nav by declaring those two keys in its front matter.

## Structure

```
_config.yml
_layouts/
  default.html      html shell, meta tags, header + footer
  page.html         title, lede, body, and the optional front-matter blocks
_includes/
  header.html       brand + horizontal nav
  footer.html       contact line + copyright
assets/css/style.css   single stylesheet, custom properties at :root
```

## Design constraints

White ground, `#1a1a1a` text, one accent (deep navy `#12284b`). No shadows, no
gradients, no border-radius, no animation. Georgia headings, system sans body,
1.7 line height, 1100px maximum width. Mobile is a single column and the nav
wraps — there is no hamburger and no menu script.

To adjust the visual system, edit the custom properties in the `:root` block at
the top of `assets/css/style.css`. Colour, type scale, and spacing are all
declared there.

## Local preview (optional)

```
gem install jekyll
jekyll serve
```

Not required — GitHub builds the site on push.

## Deployment

Settings → Pages → Deploy from a branch → `main` / `/ (root)`.

If the repository is renamed, update `baseurl` in `_config.yml` to match the
new name (`/new-repo-name`), or set it to `""` for a user page.
