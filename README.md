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
