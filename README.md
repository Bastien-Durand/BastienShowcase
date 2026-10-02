# bastien-portfolio

Personal portfolio site for Bastien Durand. Plain static HTML, CSS and JS: no build step.

## Structure

```
index.html      the whole page (styles and script inline)
assets/         images, including og.jpg (link preview image)
amplify.yml     AWS Amplify build settings
```

## Run locally

Open `index.html` in a browser, or run `npx serve .` and visit http://localhost:3000.

## Deploy option A: GitHub Pages (free)

1. Create a public repo, upload these files (drag and drop works on github.com), commit to `main`.
2. Repo → Settings → Pages → Source: "Deploy from a branch" → `main` / root → Save.
3. Live in about a minute at `https://<username>.github.io/<repo>/`.
4. Custom domain: Settings → Pages → Custom domain → enter it, then at your registrar add the A records (185.199.108.153, .109.153, .110.153, .111.153) for the root domain and a CNAME `www` → `<username>.github.io`. Tick "Enforce HTTPS" once it appears.

## Deploy option B: AWS Amplify

1. Push this folder to a GitHub repo.
2. AWS Console → Amplify → Create new app → GitHub → pick the repo and the `main` branch.
3. Amplify detects `amplify.yml`. Leave the defaults and click Save and deploy.
4. Every push to `main` redeploys automatically.

## Custom domain

Amplify → your app → Hosting → Custom domains → Add domain. If the domain is in Route 53 it's one click; otherwise add the CNAME records Amplify shows at your registrar. HTTPS is set up for you.

After the domain is live, update the `og:url` and `og:image` tags in `index.html` to absolute URLs on that domain so LinkedIn and WhatsApp previews show the image.

## Editing content

- Product tabs: the `products` array in the `<script>` at the bottom of `index.html`.
- To swap a product image, replace the file in `assets/` with one of the same name.
- Book covers: see `assets/books/README.md` for the file names.
