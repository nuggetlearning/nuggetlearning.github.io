# Nuggets — landing site

Static site for [nuggets]. Plain HTML/CSS, no build step. Open `index.html` locally or serve the folder.

## Local preview

```sh
cd marketing/site
python3 -m http.server 8080
# → http://localhost:8080
```

## Pages

- `index.html` — landing
- `support.html` — FAQ + contact
- `contact.html` — contact info
- `privacy.html` — privacy policy
- `terms.html` — terms of service
- `404.html` — not-found page
- `assets/` — styles, icons, screenshots

## Publishing to GitHub Pages (new repo)

1. **Create a new GitHub repo** named `nuggets-site` (or similar, public).
2. **Copy this folder's contents** to the new repo's root:

   ```sh
   cd /Users/saumye/AndroidStudioProjects/nuggets/marketing/site
   git init -b main
   git remote add origin git@github.com:<your-user>/nuggets-site.git
   git add .
   git commit -m "Initial landing site"
   git push -u origin main
   ```

3. On GitHub: **Settings → Pages → Build and deployment → Source: Deploy from a branch → main / (root) → Save.**
4. The site will be live at `https://<your-user>.github.io/nuggets-site/` in ~1 minute.

### Custom domain (optional)

- Rename `CNAME.example` to `CNAME`, replace with your domain, commit/push.
- In your DNS, add a CNAME record from the subdomain to `<your-user>.github.io`.
- In GitHub → Settings → Pages, set the custom domain and check **Enforce HTTPS**.

## Update store links

When the app is live, update the four `<a class="store-btn disabled">` blocks in `index.html` (two in the hero, two in the CTA strip):

```html
<a class="store-btn" href="https://apps.apple.com/app/id...">
  <span><span class="small">Download on the</span><span class="big">App Store</span></span>
</a>
<a class="store-btn" href="https://play.google.com/store/apps/details?id=ai.vastav.nuggets">
  <span><span class="small">Get it on</span><span class="big">Google Play</span></span>
</a>
```

Then remove the `disabled` class and `aria-disabled` attribute. You can also delete the "Coming soon to" prefix.
