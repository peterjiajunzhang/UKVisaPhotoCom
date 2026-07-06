# UKVisaPhotoCom — marketing site

Live site: **https://uk.visaphoto1tap.com/**

| Path | Purpose |
|------|---------|
| `index.html` | Landing; App Store CTA is a **"Coming soon"** badge |
| `privacy.html` | Privacy policy (linked from App Store Connect) |
| `sitemap.xml` / `robots.txt` | SEO |
| `AppIcon.png` | **Real app icon**, copied from `VisaPhotoApps/UKVisaPhoto/Assets.xcassets/AppIcon.appiconset/AppIcon.png` — unlike India/Japan/Canada, this one already existed |
| `VisaPhotoApps/Marketing/UK/xiaohongshu/` | Xiaohongshu post previews & export scripts |
| `VisaPhotoApps/Marketing/UK/appstore/` | App Store screenshot campaign previews & export scripts |
| `screenshots/` | Real device screenshots — **5 of 6 captured** (missing `05-exported.png`); confirmed showing the correct `#E8E8E2` grey/cream background (not white) |
| `demos/` | Real before/after export pairs — all 6 captured, confirmed showing the correct `#E8E8E2` grey/cream background (not white) |

**Status:** real screenshots and demo pairs are mostly in. `index.html` has a real `#demos` before/after wall and a real `#app` screenshot grid (currently 5 screens: home, checklist, paywall, saved photos, languages). **Still needed: `05-exported.png`** (the unlocked-result screen with Share/Rate/Review/Download/Start over) — drop it into `screenshots/` and add its `<figure>` back into `index.html`'s `#app` grid + the App Store campaign slide that references it. iOS app has no Info.plist/App.swift yet and no Apple ID.

## The one thing that makes UK different from every other app in this family

**Background is light grey/cream, not white.** Every other market (US, China, Schengen, India, Japan, Canada) composites onto pure white. gov.uk's guidance explicitly says **plain light-coloured — cream or light grey**. The implemented color is `UIColor(red: 232/255, green: 232/255, blue: 226/255)` = **`#E8E8E2`** (see `USVisaPhoto/UKPhotoProcessor.swift`). This is called out prominently on the landing page (`#background-rule` section, a dedicated white-vs-grey/cream visual comparison) — **don't let it get diluted to "white" in future copy edits**, it's the single most distinctive fact about this product line.

## Before submitting to App Store Connect

1. Once `AppStoreAppleID` is filled in (once the UKVisaPhoto target has an Info.plist and Connect record), update the CTA to a real App Store link.
2. Capture `05-exported.png` (see Status above) — the last missing canonical screenshot.
3. Re-run exports after any new screenshot lands:
   ```bash
   cd VisaPhotoApps/Marketing/UK/appstore && npm run export
   cd VisaPhotoApps/Marketing/UK/xiaohongshu && npm run export
   ```

**Product facts baked into this site** (source: `VisaPhotoApps/docs/uk-visa-photo-spec.md` — the **best-sourced** spec of the five new countries, gov.uk pages directly fetched, high confidence):
- Digital-first (UKVI account upload); 35×45mm at **630×810 px** export (exceeds gov.uk's 600×750px minimum at the correct aspect ratio).
- Head height 64–76% (29–34mm of 45mm frame); JPEG 50 KB – 6 MB (re-verify the 6MB vs. 10MB figure close to submission — some third-party aggregators cite 10MB, but the visa-specific gov.uk page says 6MB).
- **No print-layout feature** (digital-first, like China/Schengen/India/Canada, unlike Japan).
- Accent color: Union Jack navy `#012169` — deliberately **not** another red (China/Japan/Canada already use red-family accents; a 4th red would blur together).

**iOS app repo:** [VisaPhotoApps](https://github.com/peterjiajunzhang/VisaPhotoApps) — scheme `UKVisaPhoto` (once scaffolded with Info.plist/App.swift).

Clone on a new machine:

```bash
git clone https://github.com/peterjiajunzhang/UKVisaPhotoCom.git
git clone https://github.com/peterjiajunzhang/VisaPhotoApps.git
```

Open **`VisaPhotoApps/README.md`** for full workstation setup.
