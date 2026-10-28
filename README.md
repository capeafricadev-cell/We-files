# Cape Africa Electrical: public website

Static website for capeafricaelectrical.co.za, served by a Cloudflare Worker with static assets.
The staff app (Cape Africa Field) lives in its own, separate repository.

## Layout
- `site/` : everything that is published (`index.html`, `images/`, `_headers`, `_redirects`, `robots.txt`)
- `wrangler.jsonc` : Worker settings. The `name` MUST match the Worker in Cloudflare (`silent-glade-a086`).

## Deploy
Automatic: every push to `main` is built and deployed by Cloudflare Workers Builds
(no build command; deploy command `npx wrangler deploy`).

Manual: `npx wrangler login` then `npx wrangler deploy`.

## Settings to fill in (top of the script in `site/index.html`)
`CFG = { supabaseUrl, supabaseKey, whatsapp, reviewsUrl }`. The Supabase key is the PUBLISHABLE key (safe in the browser).
Never commit a secret or service-role key.

## Before launch
- `site/robots.txt` currently blocks search engines. Remove the `Disallow` line when the real domain points here.
- Confirm staff photos and client names in `site/images` are cleared for public use.
