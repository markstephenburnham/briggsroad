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
   git remote add origin https://github.com/markstephenburnham/briggsroad.git
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

Email is handled via **ImprovMX** (free tier) for both receiving and sending.

### Setup

1. Sign up at [improvmx.com](https://improvmx.com), add `briggsroad.com`
2. Add the MX records ImprovMX gives you in Namecheap Advanced DNS (replace any existing MX records)
3. In ImprovMX, create an alias: `mark` → your personal Gmail
4. In ImprovMX, go to **SMTP credentials** → create a password for `mark@briggsroad.com`

### Sending from Gmail

1. Gmail → Settings → Accounts → **Send mail as** → Add another email address
2. Enter `mark@briggsroad.com`
3. On the SMTP config screen:
   - SMTP Server: `smtp.improvmx.com`
   - Port: `587`
   - Username: `mark@briggsroad.com`
   - Password: the SMTP password from ImprovMX
   - Secured connection: TLS
4. Gmail sends a verification email to `mark@briggsroad.com` → it forwards to your Gmail → click the link

To send as `mark@briggsroad.com`, use the **From** dropdown when composing in Gmail.

### Other aliases

Add more aliases in ImprovMX as needed (e.g. `hello` → your Gmail). Each alias receives mail automatically. To *send* from a new alias, repeat the Gmail "Send mail as" steps with the new address.
