# tachiyomi-extensions-ntk

Custom Mihon / Tachiyomi extension repository for the Korean **NTK** (newtoki) source.

- Extension source: [`source` branch → `src/ko/ntk`](https://github.com/celestinemoffi-jpg/tachiyomi-extensions-ntk/tree/source/src/ko/ntk)
- Current version: **v1.6.43**

## Add to Mihon / Tachiyomi

In the app, go to **More → Settings → Browse → Extension repos → Add**, paste:

```
https://celestinemoffi-jpg.github.io/tachiyomi-extensions-ntk/index.min.json
```

Then open **Browse → Extensions** and install **NTK**.

## Sources

| Source | Language | Path | Notes |
|---|---|---|---|
| NTK 만화 | ko | `/manhwa` | NSFW |
| NTK 웹툰 | ko | `/webtoon` | |

The shipped default domain is `newtoki1.org`. If the site moves, change it in
**Extension settings → Base URL** — no update is required for a domain change.

## Features

- **Two sources, one extension** — 만화 (manhwa) and 웹툰 (webtoon) listings, latest updates, and search.
- **Filters** — sort order, genre, publication status (만화), category / day of week / platform (웹툰),
  and initial consonant (초성). Filters apply to browsing only, not keyword search.
- **Full chapter list** — follows the site's `epage` chapter pagination so long serials are not cut off.
- **Chapter recognition** — numbered episodes (`73화`, `73-1화`, `5화. 부제`) are recognised as
  chapters; volumes (`77권`) stay separate and are grouped after specials.
- **Reader via WebView** — the site gates reader images behind a script challenge, hidden WebView
  captures the image list. First load of a chapter can take a few seconds; failures surface as a
  normal "couldn't load" instead of a crash.
- **Deeplinks** — `https://<domain>/manhwa/...` and `https://<domain>/webtoon/...` links open the
  app entry.

## Troubleshooting

- **Images won't load / reader times out** — the reader needs the WebView (and, on some devices,
  Chrome/WebView component up to date). Retry the chapter; if the domain changed, update the base
  URL first.
- **Extension won't install / update** — make sure you added the repo URL exactly as above. The APK
  is signed with the repo's key; installing over a previous repo copy requires the same key.

## Contents

- `index.min.json` — repository index consumed by Mihon/Tachiyomi
- `index.json` / `index.pb` — same index in full JSON / protobuf form
- `apk/` — built extension APKs
- `icon/` — extension icons (PNG)
- `repo.json` — repo metadata incl. the APK signing key fingerprint

## Credits

Based on the [Keiyoushi](https://github.com/keiyoushi) extension toolchain. The underlying source
parser carries the usual upstream attribution for the original newtoki extension.
