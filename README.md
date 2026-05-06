# Template Button Board

A small static button board for copying reusable text templates. It is designed for GitHub Pages and uses Campbell University orange for the template buttons.

## Features

- Copy templates with one click.
- Add, edit, and delete templates from the browser.
- Search and filter templates.
- Filter by category.
- Choose from existing categories or add a new category.
- Assign button and text colors by category.
- Edit category colors so all matching buttons update together.
- Sync shared templates through Firebase Firestore.

## Edit Templates

The live page lets users add, edit, and delete templates. Changes are saved in Firebase Firestore, so the same templates appear on phone, work laptop, and desktop.

The `defaultTemplates` array in `index.html` is only used to seed Firestore the first time the database is empty.

```js
{
  title: "Initial Follow Up",
  category: "Follow Up",
  text: `Hi {{name}},

Your template text goes here.`
}
```

After Firestore has templates, the live data in Firebase is the source of truth.

## Firebase Setup

1. Create a Firebase project.
2. Add a web app and copy the Firebase config into `index.html`.
3. Go to **Build > Firestore Database**.
4. Create the database.
5. Start in test mode while building.

Test mode is not permanent. Later, lock editing behind Firebase Authentication so only approved users can add, edit, or delete buttons.

For the current shared-editing version, Firestore rules must allow both `templates` and `categoryStyles`:

```js
rules_version = '2';

service cloud.firestore {
  match /databases/{database}/documents {
    match /templates/{templateId} {
      allow read, write: if true;
    }

    match /categoryStyles/{categoryId} {
      allow read, write: if true;
    }
  }
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
