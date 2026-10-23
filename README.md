# Elemii public website — copy this folder's contents

This folder is the editable source for the public information site. It is
independent of the iPhone app, article publisher and report services. No build
tool, package install, generated assets or environment variables are needed.

## Files

| File | Edit for |
| --- | --- |
| `index.html` | Homepage, app description and Google verification tag |
| `support.html` | Support information and email |
| `privacy.html` | Current data handling and development-test disclosures |
| `terms.html` | Basic website terms; available for Google's terms URL field |
| `styles.css` | Shared colors, fonts, spacing and mobile layout |

Only public content belongs here. Never copy OAuth credential JSON, API keys,
`.wrangler`, app source, test outputs or birth records into the website repo.

## Copy and publish

1. User creates a new **public** repository on GitHub.
2. Copy the **contents** of this `web/` folder into that repository's root.
   `index.html` must be at the top level, not inside another `web` folder. The
   README may be included; it is documentation, not a secret or a site dependency.
3. User commits/pushes the files. In repository **Settings → Pages**, select
   **Deploy from a branch**, select the actual published branch and **/(root)**,
   then save. Wait for GitHub to show the live URL.
4. Open the live homepage and check Support, Privacy policy and Terms of use.
   All links are relative, so a project URL such as
   `https://YOUR-USERNAME.github.io/YOUR-REPO/` works without editing paths.
5. For later changes, edit the originals in this folder, copy the changed files
   into the public repository, then commit/push there. This folder does not sync
   or publish automatically. Keep the verification tag in both copies.

A repository named `YOUR-USERNAME.github.io` serves the host root. Another name
serves a project path. Use the actual URL GitHub provides; no repository name or
GitHub account has been assumed. A user-site repository is convenient for
verifying the hostname root, but do not replace an existing site unintentionally.

## Google Search Console and OAuth

1. Sign in to Search Console with the Google account that owns the Cloud project.
2. Add a **URL-prefix** property for the exact published homepage URL, including
   `https://` and any repository path. Choose **HTML tag**.
3. The owner-supplied Google verification tag is now saved in `index.html`'s
   `<head>`. It is intended to be public; OAuth client secrets and refresh tokens
   are not. If you later verify another property/account, use its exact supplied
   tag and preserve any verification tags still in use.
4. Copy the updated file into the public repo, commit/push, wait for deployment,
   and confirm the tag appears in the live page source before clicking Verify.
5. Keep the tag after verification. If Google requires ownership at the hostname
   root as well, verify that root site; a project-path verification does not
   establish control of its parent. Do not claim ownership of all `github.io`.
6. In OAuth Branding, use the actual live homepage, `privacy.html` and
   `terms.html` URLs under the same base. Use the hostname without scheme/path
   when entering Authorized domains, if Google accepts it. Inspect any rejection
   rather than switching to a different domain or bypassing verification.
7. Check Google's actual Branding/Audience result. Search Console ownership is
   one check; it does not guarantee OAuth branding/scope approval or production
   publishing. No custom-domain purchase is assumed by this experiment.

The Google service name currently is **Elemii Email Test**, also explained on
the homepage/privacy page. Before public production, reconcile the service name,
feature status, policy date, real providers and retention with the actual release.
The current copy describes a development email pilot, not live paid delivery.

## Preview locally

Open `index.html` directly in a browser; local links/styles need no server.
For an HTTP preview, run this from the `web/` directory:

```sh
python3 -m http.server 8765 --bind 127.0.0.1
```

Then open `http://127.0.0.1:8765/`. Stop with Control-C. Local preview cannot be
verified by Google; the site must first be published publicly.

References: [GitHub Pages publishing](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site),
[Search Console verification](https://support.google.com/webmasters/answer/9008080),
[Google Branding requirements](https://support.google.com/cloud/answer/15549049).
