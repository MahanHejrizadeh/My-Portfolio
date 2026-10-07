# Digital Pass Portfolio

## ساختار
- `index.html`  صفحه (دست نزن مگر برای ظاهر)
- `content.json`  همه محتوا: نام، بیو، پروژه‌ها، لینک‌ها، ایمیل، CV
- `assets/`  عکس‌ها و فایل CV
- `admin/`  پنل ادمین (Decap CMS) روی آدرس `/admin/`
- `vendor/three.min.js`  کتابخانه 3D (روی خود سایت است)

## راه‌اندازی (یک بار، حدود ۱۵ دقیقه)
1. یک ریپوی خصوصی یا عمومی در GitHub بساز و همه این فایل‌ها را در شاخه `main` بگذار.
2. در Netlify: Add new site > Import from Git > همان ریپو. Build command خالی، Publish directory: `.`
3. در `admin/config.yml` مقدار `repo` را به `username/repo-name` و `site_url` را به آدرس سایتت تغییر بده و commit کن.
4. در GitHub: Settings > Developer settings > OAuth Apps > New. 
   Homepage URL: آدرس سایتت. Callback URL: `https://api.netlify.com/auth/done`
   بعد Client ID و Client Secret را بگیر.
5. در Netlify: Site configuration > Access & security > OAuth > Install provider > GitHub، و Client ID/Secret را وارد کن.
6. برو به `https://سایت-تو/admin/` و با GitHub لاگین کن.

از این به بعد: پروژه اضافه/حذف کن، لینک‌ها را عوض کن، CV و عکس آپلود کن و Publish بزن. چند ثانیه بعد سایت به‌روز می‌شود.

## دامنه شخصی
Netlify: Domain management > Add a domain.

## اجرای محلی
`npx serve` در همین پوشه (باز کردن مستقیم فایل کار نمی‌کند چون content.json با fetch خوانده می‌شود).

## Customization (everything from /admin/)
- Texts and button labels, show/hide for each section (handle, tags, location, map, buttons, social panel, honeycomb, projects)
- Colors: page background (4 stops or an image), frame, panels, text, accent, badge area, orb
- Font (12 Google fonts, including Vazirmatn for Persian), title size, corner radius, dotted texture
- Layout: max width and height, badge position (center, left, right), text direction (ltr or rtl)
- 3D and motion: tilt strength (0 turns it off), idle motion, badge glass color and opacity, light sheen, sway, drop-in intro, size, pointer follow
- SEO: page title, description, tab icon
Anything not listed lives in index.html; the file is plain HTML, CSS and JS.
