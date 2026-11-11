# Simons Collaboration on Discrete Subgroups of Lie Groups

This repository hosts the static website for `discrete-subgroups.org`.

## Publishing with GitHub Pages

In **Settings → Pages**, choose **Deploy from a branch**, branch `main`, folder `/ (root)`. Set the custom domain to `discrete-subgroups.org`. The root-level `CNAME` file already contains that domain. The root-level `.nojekyll` file disables Jekyll processing.

Before changing DNS, check that the published site works and that all external assets have been uploaded. The original page references `logos/simons-foundation.svg` (not supplied), and the SFI logo at `logos/SFI_Logo_FULL_RGB.png` (supplied but not yet committed).

## Changing a portrait

All 16 principal investigator portraits are in `photos/`, as JPEGs. To swap a photo, replace that JPEG with a new image under the **same filename**, then commit. The main HTML references these paths; no HTML editing is needed if you preserve the filename.

## Migrating DNS from Netlify

Once the GitHub Pages build is enabled, replace the apex (`@`) Netlify web A/ALIAS records with GitHub Pages A records:

- `185.199.108.153`
- `185.199.109.153`
- `185.199.110.153`
- `185.199.111.153`

Set `www` to a CNAME pointing directly to `tomhutchcroft.github.io`. Keep MX, TXT and other mail-related DNS entries unchanged. Enable **Enforce HTTPS** in GitHub Pages when available. Do not cancel Netlify until the site works on the custom domain.

See https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site.


## Event-page design preview

A GitHub Actions workflow (`.github/workflows/pages.yml`) publishes **two copies of the static website in one Pages deployment**:

- Production: site root (`/`) from `main`.
- Experimental Events design: `/preview/events/#/events` from `events-list-first-fullscreen`.

The preview is refreshed automatically whenever either branch is updated. It does **not** overwrite the production files.

In **Settings → Pages → Build and deployment**, choose **GitHub Actions** as the source. Open **Actions → Publish website and events preview** to inspect deployments.

Before the custom domain is pointed at GitHub Pages, the intended preview URL is:

`https://tomhutchcroft.github.io/discrete-subgroups/preview/events/#/events`

Once the custom domain is configured and resolving to GitHub, the same path works under `https://discrete-subgroups.org/preview/events/#/events`. GitHub may redirect the `github.io` URL to the custom domain if it is already configured in Pages settings, even if DNS has not yet been switched. Keep the Netlify DNS unchanged until GitHub Pages is ready.

GitHub Pages availability for private repositories depends on the account's plan.
