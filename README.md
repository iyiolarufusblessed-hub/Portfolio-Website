# Juan Dela Cruz — Personal Portfolio Website

A static, no-JavaScript, no-CMS personal portfolio built with semantic
HTML5, pure CSS3, and a JSON data schema.

## Directory structure
```
/                     Root — one HTML file per page
  index.html          Home
  about.html          About Me
  education.html      Educational Background
  skills.html         Technical Skills
  projects.html       Projects
  hobbies.html         Hobbies and Interests
  cv.html             Curriculum Vitae
  contact.html        Contact Me
/assets/css/style.css Single stylesheet (design tokens, layout, components)
/assets/images/       SVG placeholder images referenced by data.json
/data/data.json       Structured content schema (education, skills, projects, hobbies)
```

## Deployment
This is a fully static site — any static host works:
- **GitHub Pages:** push this folder to a repo, enable Pages on the `main`
  branch (root), and it is served at `https://<user>.github.io/<repo>/`.
- **Netlify:** drag-and-drop this folder onto Netlify's deploy UI, or connect
  the repo for continuous deployment.
- **Any HTTP server:** because there is no build step, the folder can be
  served as-is by Apache, Nginx, or a university web host — just point the
  document root at this directory.

## Notes
- No JavaScript is used anywhere (no `<script>` tags for logic — only
  `application/ld+json` metadata blocks, which are inert data, not executable
  script).
- Mobile navigation uses the CSS-only "checkbox hack" (`:checked` selector).
- Project detail overlays use the CSS `:target` pseudo-class.
- The About FAQ uses native `<details>`/`<summary>` (HTML5, not JavaScript).
- `data/data.json` is the canonical structured-data model of the site's
  content; because the brief forbids client-side scripting, content is
  mirrored by hand into each HTML page (a fetch-and-render pattern would
  require JavaScript). See the accompanying Technical Report for a full
  discussion of this design decision.
