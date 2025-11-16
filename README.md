# Gervi Labs website

Static site for [gervi.ai](https://gervi.ai), built with Jekyll and hosted on GitHub Pages.

## Structure

- Main pages: `index.md`, `about.md`, `team.md`, `projects.md`, `contact.md`
- Project diary entries in `_projects/`
- Layouts in `_layouts/`
- Shared partials in `_includes/`
- Styles in `assets/css/main.css`

## Adding a new project

1. Create a new file in `_projects/`, for example:

   `_projects/new-project-name.md`

2. Add front matter and content:

   ```markdown
   ---
   title: New project name
   tagline: Short one line summary.
   year: 2025
   status: ongoing
   type: performance
   external_url:
   ---

   Short description of the project here.
   ```

3. Commit and push. The project will appear automatically on `/projects/`.

## Local development

If you have Ruby and Bundler installed:

```bash
gem install bundler jekyll   # if needed
jekyll serve
```

Then visit `http://localhost:4000`.

## Deployment

The site is intended for GitHub Pages:

- Set the repo to build with GitHub Pages.
- Use the default Jekyll build.
- Keep the `CNAME` file so the site serves on `gervi.ai`.
