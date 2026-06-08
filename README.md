# ignite-site

Marketing + legal static site for the **IGNITE** app, served via GitHub Pages at
**https://ignite.totaldebug.uk**.

Built with Jekyll (the same toolchain GitHub Pages runs server-side), with a
custom theme mirroring the app's design tokens — no external Jekyll theme gem.

## Pages

| URL | Source | Purpose |
| --- | --- | --- |
| `/` | `index.html` | App showcase / landing |
| `/privacy/` | `privacy.md` | Privacy policy (App Store + Play require a URL) |
| `/delete-account/` | `delete-account.md` | Account & data deletion (store requirement) |
| `/support/` | `support.md` | Support / FAQ |

Content pages are plain Markdown with a small front-matter block
(`layout: page`, `title`, `permalink`, `updated`). Edit the Markdown and push —
GitHub rebuilds automatically.

## Editing

- **Contact email, store links, site title** live in `_config.yml` under
  `contact_email`, `app_store_url`, `play_store_url`. Change them once there;
  every page picks them up via `{% raw %}{{ site.* }}{% endraw %}`.
- **Theme / colours**: `assets/css/style.css` (`:root` variables mirror
  `constants/colours.ts` in the app repo).
- **Layouts / nav / footer**: `_layouts/` and `_includes/`.

## Local preview

```sh
bundle install
bundle exec jekyll serve   # http://127.0.0.1:4000
```

## Deploy (one-time setup)

1. Create a **public** GitHub repo named `ignite-site`, push this directory.
2. Repo → Settings → Pages → Build from branch `main`, folder `/`.
3. Custom domain is already set via the `CNAME` file (`ignite.totaldebug.uk`).
   Add a DNS **CNAME** record: `ignite` → `<github-username>.github.io`.
4. Tick **Enforce HTTPS** once the certificate provisions.

## Source of truth

The privacy + deletion copy is duplicated from the app repo's
`docs/privacy-policy.md` and `docs/delete-account.md`. When you change one,
update the other (the app repo's `docs/store-listing.md` references both URLs).
