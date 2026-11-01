# Static blog pages

The Google Sheet remains the source of truth. Netlify reads the published Blog and Settings tabs during each build and generates a static HTML page for every row marked Published = yes that contains article text. The existing blogs.html remains the live blog listing and continues to read the Sheet in the browser.

## Automatic refresh setup

Create a Netlify build hook for the main branch, then add its URL to GitHub repository Actions secrets as NETLIFY_BUILD_HOOK. The workflow refreshes the site daily at 05:17 UTC and can be run manually from GitHub Actions. New posts remain visible in the live listing as soon as the Sheet updates; static SEO pages are generated at the next build.

