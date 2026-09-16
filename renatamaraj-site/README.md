# renatamaraj.com — setup instructions

## 1. Create the GitHub repo
1. Go to github.com (log in as renatavmaraj), click **New repository**.
2. Name it exactly `renatavmaraj.github.io` (this exact name is what makes GitHub Pages work for a user site).
3. Set it to **Public**, don't initialize with a README (we already have one).
4. Create it.

## 2. Upload these files
Easiest way with no command line:
1. On the new repo's page, click **Add file → Upload files**.
2. Drag in *everything inside this folder* (index.html, about/, work/, writing/, contact/, assets/, CNAME, README.md) — keep the folder structure intact.
3. Commit directly to the `main` branch.

(If you're comfortable with git/terminal, `git init`, add this folder's contents, commit, and `git push` to the repo instead.)

## 3. Turn on GitHub Pages
1. In the repo, go to **Settings → Pages**.
2. Under "Build and deployment," source should be **Deploy from a branch**, branch `main`, folder `/ (root)`. Save.
3. Under "Custom domain," enter `renatamaraj.com` and save (this should auto-detect from the CNAME file, but confirm it's there).
4. Check **Enforce HTTPS** once it becomes available (can take a few minutes to an hour after DNS is set up).

## 4. Point your GoDaddy domain at GitHub
In GoDaddy: your domain → **DNS** → **Manage DNS records**.

Add these **A records** for the root domain (`@`), pointing to GitHub Pages' servers:
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

Add one **CNAME record**:
```
Type: CNAME
Name: www
Value: renatavmaraj.github.io
```

Remove any existing A or CNAME records on `@` or `www` left over from the old Squarespace setup so they don't conflict.

DNS changes can take anywhere from a few minutes to 24 hours to fully propagate.

## Adding a new blog post later
1. Duplicate any existing page's folder (e.g. `about/`) as `writing/your-post-slug/`.
2. In the new `index.html`, replace the `<main class="prose">` content with your post title and text — leave the `<head>`, header, and footer as they are.
3. Add a teaser block for it near the top of `writing/index.html`'s `<main>` (there's a comment there showing the format).
4. Upload/commit both changed files to GitHub — the live site updates automatically within a minute or two.

Or just come back here and ask Claude to write and add the post for you.
