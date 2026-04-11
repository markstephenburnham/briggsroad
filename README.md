# briggsroad.com

Static site for Briggs Road LLC, hosted on GitHub Pages.

## Deployment

### First time

1. Create a new repo at github.com named `briggsroad`
2. From this directory:
   ```bash
   git init
   git add index.html README.md
   git commit -m "initial"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/briggsroad.git
   git push -u origin main
   ```
3. In the GitHub repo: **Settings → Pages → Source** → Deploy from branch → `main` / `root` → Save
4. GitHub will publish the site at `YOUR_USERNAME.github.io/briggsroad` within a minute or two

### Custom domain (briggsroad.com)

In Namecheap Advanced DNS, add these records:

| Type | Host | Value |
|------|------|-------|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | YOUR_USERNAME.github.io. |

Then in GitHub: **Settings → Pages → Custom domain** → enter `briggsroad.com` → Save.
GitHub will provision an SSL certificate automatically (can take up to 24 hours).

### Making changes

Edit `index.html`, then:
```bash
git add index.html
git commit -m "update site"
git push
```
GitHub Pages redeploys automatically within ~30 seconds.

## Email

Set up forwarding for `mark@briggsroad.com` (or `hello@briggsroad.com`) via your domain registrar or Cloudflare Email Routing so mail lands in your inbox.
