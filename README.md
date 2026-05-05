# Template Button Board

A small static button board for copying reusable text templates. It is designed for GitHub Pages and uses Campbell University orange for the template buttons.

## Edit Templates

Open `index.html` and edit the `templates` array near the bottom of the file:

```js
{
  title: "Initial Follow Up",
  category: "Follow Up",
  text: `Hi {{name}},

Your template text goes here.`
}
```

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
