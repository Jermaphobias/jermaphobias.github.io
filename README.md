# Astra's website 101

You will need two things;
- A GitHub.com account
- A domain bought on either Porkbun or Cloudflare (I suggest these two, but any domain registrar will do)

## Commands

All commands are run from the root of the project, from a terminal:

| Command                   | Action                                           |
| :------------------------ | :----------------------------------------------- |
| `npm install`             | Installs dependencies, super needed at the beggining of each development environment setup.                          |
| `npm run dev`             | Starts local dev server at `localhost:4321`, useful for previewing live changes.      |
| `npm run build`           | Build your production site to `./dist/`, in a single static html file.          |
| `npm run preview`         | Preview your build locally, before deploying     |
| `npm run astro -- --help` | Get help using the Astro CLI                     |

## How to deploy to GitHub Pages

### 1. Create a GitHub Account
1. Go to https://github.com and click **Sign up**.
2. Enter your email, username, and password.
3. Verify your email address by clicking the link in the confirmation email.
4. Complete any profile setup prompts (you can skip or fill them in).

### 2. Create a Repository for GitHub Pages
1. On GitHub, click **+** (top right) → **New repository**.
2. Set **Repository name** to `<your-username>.github.io` (this will become your site URL).
3. Choose **Public**, then click **Create repository**.

### 3. Upload Your Site to GitHub
Go to your project's url from the GitHub website, and follow these steps:
1. Click **Add file** → **Upload files**.
2. Drag and drop these files from the root, **ALL** of them.
3. Now, go to **Settings** → **Pages**.
4. Under **Builds and deployments**, select **GitHub Actions**.
5. Click **Save** to enable GitHub Actions for your repo.
6. If you can, select Astro as the GitHub Action, and leave everything AS IS.

### 5. Access Your Deployed Site
Visit:
```
https://<your-username>.github.io/
```

### 6. Adding journal entries
To add journal entries, you can create a new markdown file in the `src/pages/posts/` directory. Doesn't matter the name, but it should end with `.md`. For example, `my-first-post.md`. The file should start with a frontmatter block like this:

```markdown
---
title: 'My First Blog Post'
pubDate: 2025-07-06
description: 'Description'
author: 'Astra'
image:
    url: 'Image url'
    alt: 'Alt for the image.'
tags: ["Tag1", "Tag2"]
layout: ../../layouts/Layout.astro
---

# My First Post

This is the content of my first post in **MARKDOWN** format.
```

REMEMBER TO PUT 
```markdown
---
title: 'My First Blog Post'
pubDate: 2025-07-06
description: 'Description'
author: 'Astra'
image:
    url: 'Image url'
    alt: 'Alt for the image.'
tags: ["Tag1", "Tag2"]
layout: ../../layouts/Layout.astro
---
```
at the top of your markdown file, this is called frontmatter and is used by Astro to generate the page correctly.

After you create your markdown file, you can run the following command to build your site:

```bash
git add .
git commit -m "Add post"
git push
``` 

The GitHub Action will automatically build your site and deploy it to GitHub Pages.

### 7. Adding gallery images
To add images to your gallery, you can place them in the `public/` directory. You can then reference these images in your markdown files using a similar syntax: (remember, you will need a markdown file per each image)

```markdown
---
title: "My cat :333"
image: "/catto.jpg"
thumbnail: "/catto.jpg"
description: "mrrrreow :3"
category: "photography"
date: "2025-06-08"
tags: ["example-tag", "cats", "mrrreow"]
layout: ../../layouts/Layout.astro
---

# Catto!!!1!

![Catto](/catto.jpg)

I took this photo of my catto, isn't he cute? :3
```

---
That's it! You have successfully deployed your website to GitHub Pages. You should see your built website live on GitHub Pages!

That's all, if I explained something wrong or you need help, DM me via Fiverr!
