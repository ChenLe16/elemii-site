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

The 29 October refund-help update adds Apple's refund request link and instructions
to Support and Terms. These are local source edits, not a published site update.
Copy the changed files to the public repository when ready to publish; the
privacy policy has no new data collection to describe for this link.
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

## Google Search Console and OAuth — ownership blocker

Owner reports the published homepage is
`https://chenle16.github.io/elemii-site/`, but Google Branding says the homepage
is not registered to the owner. Search Console property/account results have not
been independently inspected. The web browsing tool could not retrieve the live
site; that does not establish a website outage.

The supplied HTML verification tag remains in `index.html`'s `<head>`. It can
verify a Search Console **URL-prefix property**, but Google's dedicated
[OAuth domain-verification troubleshooting](https://support.google.com/cloud/answer/13804266)
now explicitly requires a **Domain property verified at DNS level**, rather than
a URL-prefix/Site property, with the correct Google Cloud Project Owner account.
Earlier advice to use the HTML tag as the potential OAuth solution was incomplete.

The developer does not control DNS for the free `chenle16.github.io` hostname,
so this site cannot complete that documented DNS-verification route as-is.
Do not repeat tag edits, move the tag to another GitHub page or create more
URL-prefix properties expecting them to establish DNS ownership.

A custom domain under the owner's DNS control can still use free GitHub Pages
hosting and these exact site files. If that route is adopted:

1. Configure the owned custom domain for this Pages site and HTTPS.
2. Add its **Domain** property in Search Console with the Cloud Project Owner
   account, add Google's supplied DNS TXT record, and verify.
3. Update Branding homepage/privacy/terms URLs and Authorized domains to the new
   domain; resolve Google's actual checks before publishing or reauthorizing.
4. Retain verification records and review the live pages. Site verification,
   brand/scope approval and publishing remain distinct checks.

No domain purchase, DNS change or account change is authorized by this guide.
The existing GitHub Pages URL remains usable as an ordinary website. These
files remain the local editing source and can be reused unchanged under a
custom domain. OAuth personal-use exceptions require a separate review and
should not be treated as an automatic bypass of this observed ownership check.

The Google service name currently is **Elemii Email Test**, also explained on
the homepage/privacy page. Before public production, reconcile the service name,
feature status, policy date, real providers and retention with the actual release.
The current copy describes private synthetic report-download tests, the locally tested thirty-day PDF/temporary-content policy and historical email tests. Customer generation and purchases are not enabled. Failed-job/support-mail/metadata periods remain open; these local edits do not publish the site.

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
