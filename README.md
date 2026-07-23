# mahjongnook-legal

Public, statically-hosted legal documents for the MahjongNook game — served via **GitHub Pages**
so the App Store, Google Play, and Steam can link a stable HTTPS URL.

- `index.html` — landing page linking the two documents
- `privacy.html` — Privacy Policy
- `terms.html` — Terms of Service / EULA
- `style.css` — shared styling

These are MahjongNook's **live** Privacy Policy and Terms, served via GitHub Pages. All placeholders
were resolved and the documents finalized on 2026-07-22.

## Field status (all resolved)

| Field | Value |
|---|---|
| Contact email | `dumplingfishgames@gmail.com` |
| Legal entity | `dumplingfish (a sole proprietorship)` |
| Contact address | Intentionally omitted — email is the contact method; a postal address is not required in the policy itself (note: Google Play requires a developer address on the account, and Apple's EU DSA trader address applies only if the EU is not excluded) |
| Governing law | `the State of California, USA` |
| Minimum age | `16` |
| Liability cap window | `12` months |

GDPR legal-bases + supervisory-authority + CPRA "sharing"/non-discrimination language added; each
third-party provider's privacy policy is linked in `privacy.html` (section 3).

## Publish (create the repo + enable Pages)

This must be a **separate, public** repo (GitHub Pages on a private repo needs a paid plan). From this
folder, in your own terminal (authenticated as your GitHub account):

```bash
git init -b main
git add .
git commit -m "Add MahjongNook privacy policy and terms"

# Create the public repo and push (GitHub CLI):
gh repo create mahjongnook-legal --public --source=. --remote=origin --push
```

Then enable Pages: **GitHub → repo → Settings → Pages → Source: Deploy from a branch → `main` / root → Save.**

Your URLs become:

- `https://<your-username>.github.io/mahjongnook-legal/privacy.html`
- `https://<your-username>.github.io/mahjongnook-legal/terms.html`

Use those in App Store Connect, Play Console, and the Steamworks store page (and link them in-app).

## Custom domain (at launch)

When you have the game's domain, point Pages at it: add a `CNAME` file containing the domain
(e.g. `mahjongnook.com`), configure DNS, and set the custom domain under Settings → Pages. Pick the
launch domain **before** submitting to stores so the policy URL never has to change.

## Updating

Edit the HTML, bump the "Last updated" date, commit, push — Pages redeploys automatically.
