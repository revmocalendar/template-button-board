# Template Button Board

A small static button board for copying reusable text templates. It is designed for GitHub Pages and uses Campbell University orange for the template buttons.

## Features

- Copy templates with one click.
- Search and filter templates.
- Filter by category.
- Shared source-controlled templates through GitHub Pages.

## Edit Templates

The live page is copy-only so every device sees the same templates. To change templates, update the `defaultTemplates` array in `index.html` and push the file to GitHub.

```js
{
  title: "Initial Follow Up",
  category: "Follow Up",
  text: `Hi {{name}},

Your template text goes here.`
}
```

Because the templates live in the source file, updates appear consistently for everyone after GitHub Pages redeploys.

## Publish With GitHub Pages

1. Create a new GitHub repository.
2. Upload `index.html`, `.nojekyll`, and this `README.md`.
3. Go to the repository's **Settings**.
4. Open **Pages**.
5. Set **Source** to **Deploy from a branch**.
6. Choose the `main` branch and `/root`.
7. Save.

GitHub will publish the site at a URL like:

`https://your-username.github.io/your-repo-name/`
