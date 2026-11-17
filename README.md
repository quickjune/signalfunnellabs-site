# SignalFunnelLabs website

Dark, single-page marketing site for SignalFunnelLabs: post-click ad revenue systems (CRO + GEO).

It is plain HTML, CSS and a little JavaScript in one file. No build step, no dependencies. Fonts load from Google Fonts.

## Files

- `index.html` is the whole site.
- `404.html` is the not-found page GitHub Pages serves automatically.
- `robots.txt` allows all crawlers.
- `.nojekyll` tells GitHub Pages to serve the files as they are.
- `design/` holds the original Claude Design source the site was converted from. It is not served and not needed for the live site.

## Put it live on your domain with GitHub Pages

1. In the repo, open **Settings > Pages**.
2. Under **Build and deployment**, choose **Deploy from a branch**, pick `main` and `/ (root)`, then save.
3. Under **Custom domain**, enter your domain and save. GitHub adds a `CNAME` file to the repo for you.
4. At your domain registrar, add the DNS records GitHub lists for your domain type (an apex domain uses four `A` records, a `www` subdomain uses a `CNAME` to `quickjune.github.io`).
5. When the certificate is ready, tick **Enforce HTTPS**.

GitHub Pages on a free account needs a public repo. A private repo needs a paid plan.

## Fill in before you go live

Find every placeholder with:

```
grep -n "\[YOUR" index.html
```

- `[YOUR PRICE]` on the sprint and revenue-partner offers
- `[YOUR NAME]` and `[YOUR EMAIL]`
- The three case-study cards (`[CLIENT NAME]`, `[INDUSTRY]`, `[RESULT]` and friends)

## Contact form

Pages is static, so the form needs a destination. At the top of the script in `index.html`, set one of:

- `FORM_ENDPOINT` to a form service URL such as a Formspree endpoint, or
- `CONTACT_EMAIL` to open the visitor's email app with the details filled in.

With both empty, the form tells the visitor it is not connected and sends nothing.
