# Rosicrucian Egyptian Museum — Guest Apps

Live at **https://apps.egyptianmuseum.org**

Four visitor apps plus the hub page that lets guests choose between them.
Guests reach the hub by scanning a QR code in the galleries.

| Path        | App                  |
|-------------|----------------------|
| `/`         | Hub — Choose Your Path |
| `/decoded/` | Hieroglyphs Decoded  |
| `/signs/`   | Signs of Power       |
| `/cats/`    | The Golden Cats      |
| `/thoth/`   | Ask Thoth            |

## How to publish a change

Edit the file, commit, done. The site rebuilds and goes live in under a minute.
You can edit directly in GitHub's web interface — open the file, click the pencil
icon, make the change, and click "Commit changes." No software to install.

Every change is recorded with who made it and when, and any change can be undone,
which means edits are safe to make and easy to review.

## How it is built

Each app is a single self-contained HTML file with no build step, no framework,
and no server. Opening a file in a browser runs the app. There is no database and
no back end to maintain.

## Languages

The hub offers English, Spanish, French, Italian, Vietnamese, Chinese, Japanese,
and Arabic. The chosen language passes to each app as `?lang=` in the address, and
each app also falls back to the visitor's own phone language. Translations live in
an `I18N` block near the bottom of each file — to fix wording, edit that entry only.

## Notes for whoever maintains this next

- `_headers` sets security response headers. Cloudflare Pages applies it
  automatically; GitHub Pages ignores it (GitHub Pages cannot set custom headers).
- `/decoded/index.html` is a packed bundle, ~4.6 MB. Its text can be edited in
  place, but it cannot be restructured without the original source.
- The staff password inside `/cats/` is visible in the page source by design. It is
  a casual lock, not security. See the security review for what it does and does not protect.
