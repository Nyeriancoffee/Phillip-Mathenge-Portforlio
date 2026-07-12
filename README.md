# Phillip Mathenge M. — Personal Website

A single-file website (`index.html`) built from your resume, styled around
the idea of data annotation — your own profession. Your professional
summary in the hero section is tagged the way an annotation tool tags
entities (ROLE, ORG, SKILL, TRAIT, FOCUS). Hover a tag on desktop, or tap it
on mobile, to see its category.

## Files

| File | Purpose |
|---|---|
| `index.html` | The entire site — HTML, CSS, and JS in one file. Open it directly in any browser. |
| `README.md` | This file. |

## How the page is organized

Search `index.html` for these comment banners to jump straight to a section:

1. `1. DESIGN TOKENS` — all colors and fonts, defined once as CSS variables
2. `SECTION: HERO` — your name, title, and the tagged summary paragraph
3. `SECTION: EXPERIENCE` — the work history "log"
4. `SECTION: SKILLS` — skill categories as tag chips
5. `SECTION: EDUCATION` — your degree record
6. `SECTION: CONTACT` — footer with email/phone/location
7. `SCRIPT` — small bit of JS that makes tags tap-able on phones

## Common updates

**Change your phone/email:** find `#contact` in the HTML, edit the two
`<a href="mailto:...">` / `<a href="tel:...">` lines.

**Add a new job:** copy one `.log-entry` block under `SECTION: EXPERIENCE`
and edit the date, role, organization, and description.

**Add or rename a skill:** find `SECTION: SKILLS`, locate the relevant
`.skill-group`, and add/edit a `<span class="chip">...</span>`.

**Change colors:** edit only the `:root { ... }` block near the top of the
`<style>` tag. Every other rule in the file references these variables, so
changing e.g. `--tag-skill` updates that color everywhere it's used
(legend, tags, and matching skill-chip headings).

**Change the annotated summary:** find `#annotated-summary` in the HTML.
Each tagged phrase looks like:
```html
<span class="tag skill" data-tag="SKILL" tabindex="0">your phrase</span>
```
The class (`role`, `org`, `skill`, `trait`, `focus`) controls the color;
`data-tag` controls the label text shown in the tooltip.

## Deploying it

This is a static file — no build step needed. Options:

- **Quickest:** open `index.html` directly in a browser, or double-click it.
- **Free hosting:** drag the file into
  [Netlify Drop](https://app.netlify.com/drop), or create a GitHub repo,
  upload `index.html` as `index.html`, and enable **GitHub Pages** in the
  repo's Settings → Pages.
- **Custom domain:** once hosted on Netlify or GitHub Pages, both let you
  attach a custom domain for free (you'd only pay for the domain itself).

## Notes on the content

The site currently reflects what's in your resume. A few things worth a
second look before you publish:

- The "Also familiar with" chip group (AWS, GCP, Docker, CI/CD, GitHub
  Actions) was listed on your resume but isn't backed by a specific role
  or project description. If you have concrete experience with these,
  consider adding a line about where/how you used them — specifics build
  more credibility with hiring managers than a bare tool list.
- Your Kenya Police SACCO experience is mentioned in your summary but
  didn't have its own dated entry on the resume — I gave it an entry in
  the "Experience log" marked "Prior." Add exact dates there if you have
  them.
