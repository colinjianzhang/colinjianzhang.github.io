# Website Editing Guide

This file explains which files to edit when you want to update the website.

The live site structure is currently:

- `Home`
- `Publications`
- `Working Papers`
- `Teaching`

Important: the current live content is mainly driven by files in `_pages/`, not by the older template collections such as `_publications/`, `_talks/`, or `_teaching/`.

## Most Common Edits

| What you want to change | File to edit |
| --- | --- |
| Home page text | `_pages/about.md` |
| Publications page content | `_pages/publications.md` |
| Working Papers page content | `_pages/workingpapers.md` |
| Teaching page content | `_pages/teaching.md` |
| CV page text/link | `_pages/cv.md` |
| Navigation menu items | `_data/navigation.yml` |
| Name, email, Google Scholar, ORCID, profile image setting | `_config.yml` |
| Profile image file | `images/profile1.jpg` |
| Other uploaded files, such as CV PDF | `files/` |
| Overall site look and colors | `_sass/_colin-redesign.scss` |
| Import list for styles | `assets/css/main.scss` |
| Top navigation HTML | `_includes/masthead.html` |
| Left profile/sidebar card HTML | `_includes/author-profile.html` |
| Shared page wrapper | `_layouts/default.html` |

## Page Content

### Home page

Edit:

- `_pages/about.md`

Notes:

- This file controls the page at `/`.
- Even though the menu says `Home`, the content source is still `_pages/about.md`.
- Update biography text, contact text, Scholar link text, SSRN text, address, and phone here.

### Publications page

Edit:

- `_pages/publications.md`

Notes:

- Add, remove, or reorder publications directly in this file.
- Abstract dropdowns are written directly in HTML/Markdown in this file.
- If you only want to update publication text, this is the file to use.

### Working Papers page

Edit:

- `_pages/workingpapers.md`

Notes:

- Add, remove, or reorder working papers here.
- Abstract dropdowns are also written directly in this file.

### Teaching page

Edit:

- `_pages/teaching.md`

Notes:

- Current teaching entries are written manually in this file.

### CV page

Edit:

- `_pages/cv.md`
- `files/cv.pdf`

Notes:

- The page text and download link are in `_pages/cv.md`.
- The actual PDF file should be replaced in `files/cv.pdf`.

## Navigation

Edit:

- `_data/navigation.yml`

Notes:

- This controls the top menu items to the right of `Home`.
- If you want to add `CV` back to the menu, uncomment or add it here.
- The `Home` label itself is hard-coded in `_includes/masthead.html`.

## Profile Card / Sidebar

Edit:

- `_config.yml`
- `_includes/author-profile.html`
- `images/profile1.jpg`

Use `_config.yml` for:

- `author.name`
- `author.avatar`
- `author.bio`
- `author.location`
- `author.email`
- `author.googlescholar`
- `author.orcid`
- other profile links

Use `_includes/author-profile.html` only if you want to change the structure of the sidebar itself, for example:

- rename `Contact`
- reorder which links appear
- add or remove profile fields from the card

Replace `images/profile1.jpg` if you want to change the portrait photo.

## Design / Styling

### Main redesign file

Edit:

- `_sass/_colin-redesign.scss`

This is the main file for the current visual design. Use it for:

- colors
- spacing
- card appearance
- typography styling
- navigation appearance
- sidebar appearance
- home page emphasis
- publications/details styling

### Style import file

Edit:

- `assets/css/main.scss`

Notes:

- Normally you do not need to change this file unless you add or remove a Sass partial.
- It currently imports `_colin-redesign.scss`.

### Structural template files

Edit these only if you want to change layout structure, not just styling:

- `_includes/masthead.html`
- `_includes/author-profile.html`
- `_layouts/default.html`

Use cases:

- change the `Home` label
- change the menu HTML
- change the sidebar HTML
- change the page wrapper classes

## Files You Normally Do Not Need To Edit

Usually ignore these unless you intentionally want to work on old template content:

- `_posts/`
- `_portfolio/`
- `_publications/`
- `_talks/`
- `_teaching/`
- `_site/`

Notes:

- `_site/` is generated output. Do not edit it by hand.
- The current live pages are driven by `_pages/`.

## Local Preview

On this machine, Ruby is installed at:

- `C:\Ruby32-x64`

From the repo root, local build commands are:

```powershell
& 'C:\Ruby32-x64\bin\bundle.bat' install
& 'C:\Ruby32-x64\bin\jekyll.bat' build
```

If you want to run a local server instead of only building:

```powershell
& 'C:\Ruby32-x64\bin\jekyll.bat' serve
```

Then open:

- `http://127.0.0.1:4000`

## Deployment Workflow

Recommended workflow:

1. Create a branch.
2. Edit the relevant file.
3. Run a local Jekyll build.
4. Check the result.
5. Commit the change.
6. Push the branch.
7. Merge into `master` when ready.

For this repo, pushing to `master` updates the live GitHub Pages site.

## Quick Examples

### Example 1: update homepage biography

Edit:

- `_pages/about.md`

### Example 2: add a new working paper

Edit:

- `_pages/workingpapers.md`

### Example 3: replace the CV PDF

Edit:

- `files/cv.pdf`

### Example 4: add CV back to the top navigation

Edit:

- `_data/navigation.yml`

### Example 5: change colors or spacing

Edit:

- `_sass/_colin-redesign.scss`

## If You Are Unsure

Use this rule:

- If you are changing text on a page, edit `_pages/...`.
- If you are changing profile/contact/sidebar info, edit `_config.yml`.
- If you are changing the look, edit `_sass/_colin-redesign.scss`.
- If you are changing menu structure or sidebar HTML structure, edit `_includes/...`.
