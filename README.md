<div dir="rtl" markdown="1">

# 📖 راهنمای جامع AIO-Downloader

**All‑in‑One GitHub Actions Downloader — بدون فیلتر · بدون تحریم**

⭐⭐⭐ اگر این پروژه برایتان مفید است، لطفاً ستاره بدهید — به دیگران کمک میکند پیدایش کنند! ⭐⭐⭐

---

## 📚 فهرست مطالب

1. [پیشنیازها](#-پیشنیازها)
2. [فورک و راهاندازی اولیه](#-فورک-و-راهاندازی-اولیه)
3. [راهنمای جامع تمام Secretها و Tokenهای مورد نیاز](#-راهنمای-جامع-تمام-secretها-و-tokenهای-مورد-نیاز)
   - [نحوه استخراج کوکی (Cookie) با روش robots.txt](#۱-نحوه-استخراج-کوکی-cookie-با-روش-robotstxt-توصیه-اصلی)
   - [کوکی یوتیوب (YOUTUBE_COOKIES)](#۲-کوکی-یوتیوب-youtube_cookies)
   - [کوکی اینستاگرام (INSTAGRAM_COOKIES)](#۳-کوکی-اینستاگرام-instagram_cookies)
   - [کوکی X/توییتر (X_COOKIES)](#۴-کوکی-xتوییتر-x_cookies)
   - [کلید احراز هویت تونل (TUNNEL_AUTH_KEY)](#۵-کلید-احراز-هویت-تونل-tunnel_auth_key)
   - [توکن استاتیک Cloudflare (CF_TUNNEL_TOKEN)](#۶-توکن-استاتیک-cloudflare-cf_tunnel_token)
   - [آپلود در Google Drive (GOOGLE_CLIENT_ID, GOOGLE_CLIENT_SECRET, GOOGLE_REFRESH_TOKEN)](#۷-آپلود-در-google-drive-google_client_id-google_client_secret-google_refresh_token)
4. [راهنمای کامل هر گردش کار (Workflow)](#-راهنمای-کامل-هر-گردش-کار-workflow)
   - [۱. دانلودر یوتیوب (youtube-downloader)](#۱-دانلودر-یوتیوب-youtube-downloader)
   - [۲. دانلودر اینستاگرام (instagram-downloader)](#۲-دانلودر-اینستاگرام-instagram-downloader)
   - [۳. دانلودر X/توییتر (x-downloader)](#۳-دانلودر-xتوییتر-x-downloader)
   - [۴. دانلودر مستقیم (direct-downloader)](#۴-دانلودر-مستقیم-direct-downloader)
   - [۵. آرشیو کانال تلگرام (telegram-fetcher)](#۵-آرشیو-کانال-تلگرام-telegram-fetcher)
   - [۶. دانلودر تلگرام بتا (telegram-downloader-beta)](#۶-دانلودر-تلگرام-بتا-telegram-downloader-beta)
   - [۷. ضبط وبسایت - PDF و MHTML (website-capture)](#۷-ضبط-وبسایت---pdf-و-mhtml-website-capture)
   - [۸. لیچر قدرتمند (aio-leecher)](#۸-لیچر-قدرتمند-aio-leecher)
   - [۹. دانلودر ساندکلود (soundcloud-downloader)](#۹-دانلودر-ساندکلود-soundcloud-downloader)
   - [۱۰. دانلودر اسپاتیفای (spotify-downloader)](#۱۰-دانلودر-اسپاتیفای-spotify-downloader)
   - [۱۱. پاککننده جامع (aio-cleaner)](#۱۱-پاککننده-جامع-aio-cleaner)
   - [۱۲. دانلودر گوگل پلی (google-play-downloader)](#۱۲-دانلودر-گوگل-پلی-google-play-downloader)
   - [۱۳. دانلودر MEGA.nz (mega-nz-downloader)](#۱۳-دانلودر-meganz-mega-nz-downloader)
   - [۱۴. Exit Node پایتون - داینامیک (python-mhrv-dynamic-exit-node)](#۱۴-exit-node-پایتون---داینامیک-python-mhrv-dynamic-exit-node)
   - [۱۵. Exit Node پایتون - استاتیک (python-mhrv-static-exit-node)](#۱۵-exit-node-پایتون---استاتیک-python-mhrv-static-exit-node)
   - [۱۶. Exit Node Zyrln - داینامیک (zyrln-cloudflare-dynamic-exit-node)](#۱۶-exit-node-zyrln---داینامیک-zyrln-cloudflare-dynamic-exit-node)
   - [۱۷. Exit Node Zyrln - استاتیک (zyrln-cloudflare-static-exit-node)](#۱۷-exit-node-zyrln---استاتیک-zyrln-cloudflare-static-exit-node)
5. [ویژگیهای جدید (که در README قبلی نیستند)](#-ویژگیهای-جدید-که-در-readme-قبلی-نیستند)
6. [مشکل کندی checkout و راهحل آن](#-مشکل-کندی-checkout-و-راهحل-آن)
7. [محدودیتها و هشدارهای مهم](#-محدودیتها-و-هشدارهای-مهم)
8. [پشتیبانی](#-پشتیبانی)

---

## ⚠️ پیشنیازها

| نیاز | توضیح |
|---|---|
| **حساب GitHub** | رایگان — همین کافیست |
| **مرورگر + افزونه Get cookies.txt LOCALLY** | Chrome / Firefox / Edge |
| **حساب اینستاگرام** | (اختیاری) برای استوری و محتوای خصوصی |
| **حساب X (توییتر)** | **الزامی** برای دانلودر X |
| **حساب Google Cloud** | (اختیاری) برای آپلود خودکار در Google Drive |
| **حساب Cloudflare** | (اختیاری) برای Exit Nodeهای استاتیک |
| **تلگرام، ضبط وبسایت، گوگل پلی، MEGA** | هیچ چیز اضافی نیاز ندارند |

---

## 🚀 فورک و راهاندازی اولیه

### مرحله ۱: فورک کردن
روی دکمه **Fork** در بالای صفحه کلیک کنید.

### مرحله ۲: فعالسازی Actions
1. به تنظیمات بروید: **Settings** → **Actions** → **General**
2. **Actions permissions**: گزینه **Allow all actions and reusable workflows**
3. **Workflow permissions**: گزینه **Read and write permissions**
4. ذخیره کنید.

> ⚠️ **اگر دسترسی نوشتن ندهید، آپلود فایلها با خطا مواجه میشود!**

### مرحله ۳: پاکسازی اولیه (اکیداً توصیه میشود)
مخزن فورکشده شامل فایلهای رسانهای از مخزن اصلی است. برای شروع تمیز، به **Actions** → **aio-cleaner** بروید، **Clean ALL platforms** را تیک بزنید و اجرا کنید.

### مرحله ۴: تنظیم Secretها
با توجه به نیاز خود، Secretهای مورد نظر را تنظیم کنید (راهنمای کامل در بخش بعدی).

---

## 🔐 راهنمای جامع تمام Secretها و Tokenهای مورد نیاز

در این بخش، **تکتک Secretهایی که هر Workflow نیاز دارد** به همراه **آموزش گامبهگام و تصویری** برای دریافت آنها توضیح داده شده است. هر Secret در بخش Workflow مربوطه نیز ذکر شده است.

---

### ۱. نحوه استخراج کوکی (Cookie) با روش robots.txt (توصیه اصلی)

> ⭐ **روش جدید و بهتر:** به جای رفتن به صفحه اصلی سایت، از آدرس `https://website.com/robots.txt` کوکی导出 کنید. این روش **نرخ موفقیت بالاتری** دارد زیرا robots.txt یک فایل ساده و سبک است و درخواستهای مشکوک کمتری روی آن اعمال میشود.

<div dir="ltr" markdown="1">

#### 📝 مراحل استخراج کوکی:

</div>

1. یک پنجره **Private/Incognito** در مرورگر خود باز کنید.
2. افزونه **Get cookies.txt LOCALLY** را نصب کنید (از فروشگاه افزونه مرورگرتان).
3. به آدرس زیر بروید (بسته به سرویس مورد نظر):

<div dir="ltr" markdown="1">

```
https://www.youtube.com/robots.txt
https://www.instagram.com/robots.txt
https://x.com/robots.txt
```

</div>

4. روی آیکون افزونه کلیک کنید → **Export** (فرمت Netscape) → فایل txt را ذخیره کنید.
5. **پنجره خصوصی را کاملاً ببندید** (این کار نشست را میبندد ولی کوکی معتبر میماند).

> **چرا robots.txt بهتر است؟** robots.txt یک فایل متنی ساده است که هیچ محتوای سنگین یا اسکریپتهای امنیتی ندارد. در نتیجه:
> - کوکیهای دریافتی «تمیزتر» هستند
> - احتمال trigger شدن سیستمهای ضد-ربات کمتر است
> - نشست شما معتبرتر باقی میماند

> **چرا پنجره ناشناس؟** اگر در پنجره عادی لاگاوت کنید، کوکیها بیاعتبار میشوند. با بستن پنجره ناشناس، نشست بسته میشود ولی کوکی معتبر میماند.

> ⚠️ **نشانههای خرابی کوکی:** خطای `Sign in to confirm you're not a bot` (یوتیوب)، خطای `429 Too Many Requests` (اینستاگرام)، یا دانلود موفق ولی بدون فایل خروجی. راه حل: کوکی جدید از پنجره ناشناس بگیرید و Secret را بهروز کنید.

---

### ۲. کوکی یوتیوب (YOUTUBE_COOKIES)

<div dir="ltr" markdown="1">

**Secret Name:** `YOUTUBE_COOKIES`
**وضعیت:** اختیاری (اما بهشدت توصیه میشود)
**مورد استفاده در:** youtube-downloader, aio-leecher

</div>

#### 📝 مراحل:
1. پنجره Private باز کنید.
2. به `https://www.youtube.com/robots.txt` بروید.
3. **وارد اکانت گوگل خود شوید** (حتماً در همان پنجره ناشناس).
4. افزونه Get cookies.txt LOCALLY را باز کرده و Export بزنید.
5. محتوای فایل txt را کپی کنید.
6. به **Settings** → **Secrets and variables** → **Actions** بروید.
7. **New repository secret** بزنید.
8. نام: `YOUTUBE_COOKIES` | مقدار: محتوای فایل txt را بچسبانید.
9. پنجره ناشناس را ببندید.

---

### ۳. کوکی اینستاگرام (INSTAGRAM_COOKIES)

<div dir="ltr" markdown="1">

**Secret Name:** `INSTAGRAM_COOKIES`
**وضعیت:** اختیاری (برای استوری و محتوای خصوصی الزامی)
**مورد استفاده در:** instagram-downloader, aio-leecher

</div>

#### 📝 مراحل:
1. پنجره Private باز کنید.
2. به `https://www.instagram.com/robots.txt` بروید.
3. **وارد اکانت اینستاگرام خود شوید** (حتماً در همان پنجره ناشناس).
4. افزونه را باز کرده و Export بزنید.
5. Secret با نام `INSTAGRAM_COOKIES` بسازید و محتوای فایل را بچسبانید.
6. پنجره ناشناس را ببندید.

---

### ۴. کوکی X/توییتر (X_COOKIES)

<div dir="ltr" markdown="1">

**Secret Name:** `X_COOKIES`
**وضعیت:** **الزامی** ⚠️
**مورد استفاده در:** x-downloader, aio-leecher

</div>

#### 📝 مراحل:
1. پنجره Private باز کنید.
2. به `https://x.com/robots.txt` بروید.
3. **وارد اکانت X شوید** (حتماً در همان پنجره ناشناس).
4. افزونه را باز کرده و Export بزنید.
5. Secret با نام `X_COOKIES` بسازید.
6. پنجره ناشناس را ببندید.

> ⚠️ بدون کوکی X، دانلودر X اصلاً کار نمیکند!

---

### ۵. کلید احراز هویت تونل (TUNNEL_AUTH_KEY)

<div dir="ltr" markdown="1">

**Secret Name:** `TUNNEL_AUTH_KEY`
**وضعیت:** اختیاری
**مورد استفاده در:** python-mhrv-dynamic-exit-node, python-mhrv-static-exit-node, zyrln-cloudflare-dynamic-exit-node, zyrln-cloudflare-static-exit-node

</div>

#### 📝 مراحل:
1. یک رمز عبور قوی (Pre-Shared Key) انتخاب کنید (مثلاً ترکیبی از حروف و اعداد حداقل ۱۶ کاراکتری).
2. به **Settings** → **Secrets and variables** → **Actions** بروید.
3. Secret با نام `TUNNEL_AUTH_KEY` بسازید و رمز خود را وارد کنید.
4. همین رمز را در کانفیگ VPN خود (فیلد `psk`) نیز قرار دهید.

> ⚠️ این رمز باید دقیقاً با `psk` در `config.json` پروژه VPN شما یکی باشد. URL و PSK را کنار هم منتشر نکنید.

---

### ۶. توکن استاتیک Cloudflare (CF_TUNNEL_TOKEN)

<div dir="ltr" markdown="1">

**Secret Name:** `CF_TUNNEL_TOKEN`
**وضعیت:** اختیاری (فقط برای Exit Nodeهای استاتیک)
**مورد استفاده در:** python-mhrv-static-exit-node, zyrln-cloudflare-static-exit-node

</div>

#### 📝 مراحل:
1. به [Cloudflare Zero Trust Dashboard](https://one.dash.cloudflare.com/) بروید.
2. **Access** → **Tunnels** → **Create a tunnel**.
3. نام دلخواه بدهید و **Save** کنید.
4. نوع اتصال را **Cloudflared** انتخاب کنید.
5. دستور نمایش داده شده شامل توکن است. توکن را کپی کنید.
6. Secret با نام `CF_TUNNEL_TOKEN` بسازید و توکن را بچسبانید.

> ℹ️ این Secret فقط برای Exit Nodeهای **استاتیک** (با دامنه ثابت) نیاز است. برای Exit Nodeهای داینامیک (با آدرس trycloudflare.com موقت)، نیازی به این توکن نیست.

---

### ۷. آپلود در Google Drive (GOOGLE_CLIENT_ID, GOOGLE_CLIENT_SECRET, GOOGLE_REFRESH_TOKEN)

<div dir="ltr" markdown="1">

**Secret Names:** `GOOGLE_CLIENT_ID`, `GOOGLE_CLIENT_SECRET`, `GOOGLE_REFRESH_TOKEN`
**وضعیت:** کاملاً اختیاری
**مورد استفاده در:** تمام workflowهایی که گزینه `upload_to_drive` دارند (youtube-downloader, instagram-downloader, direct-downloader, website-capture, aio-leecher, soundcloud-downloader, spotify-downloader, google-play-downloader, mega-nz-downloader)

</div>

این ویژگی جدید به شما امکان میدهد فایلهای دانلودی را **مستقیماً در Google Drive خود** (در پوشه `github-actions`) ذخیره کنید، بدون اینکه فضای مخزن GitHub را اشغال کنید!

#### 📝 مراحل گامبهگام:

<div dir="ltr" markdown="1">

**قسمت اول: ایجاد پروژه در Google Cloud Console**

</div>

1. به [Google Cloud Console](https://console.cloud.google.com/) بروید.
2. یک پروژه جدید بسازید (یا پروژه موجود را انتخاب کنید).
3. **APIs & Services** → **Library**.
4. **Google Drive API** را جستجو و **Enable** کنید.

<div dir="ltr" markdown="1">

**قسمت دوم: ایجاد OAuth Client ID**

</div>

5. **APIs & Services** → **Credentials**.
6. **Create Credentials** → **OAuth client ID**.
7. نوع اپلیکیشن: **Desktop app** (یا Web application).
8. نام دلخواه بدهید و **Create** کنید.
9. **Client ID** و **Client Secret** نمایش داده میشود. آنها را کپی کنید.
10. Secretهای زیر را در GitHub بسازید:

<div dir="ltr" markdown="1">

```
GOOGLE_CLIENT_ID → Client ID خود را بچسبانید
GOOGLE_CLIENT_SECRET → Client Secret خود را بچسبانید
```

</div>

<div dir="ltr" markdown="1">

**قسمت سوم: دریافت Refresh Token با OAuth Playground**

</div>

11. به [Google OAuth Playground](https://developers.google.com/oauthplayground/) بروید.
12. روی آیکون ⚙️ (تنظیمات) کلیک کنید.
13. تیک **Use your own OAuth credentials** را بزنید.
14. Client ID و Client Secret خود را وارد کنید و **Close** کنید.
15. در **Step 1**، در بخش **Drive API v3**، scope زیر را انتخاب کنید:

<div dir="ltr" markdown="1">

```
https://www.googleapis.com/auth/drive
```

</div>

16. روی **Authorize APIs** کلیک کنید و اجازه دسترسی بدهید.
17. در **Step 2**، تیک **Auto-refresh the token before it expires** را بزنید.
18. روی **Exchange authorization code for tokens** کلیک کنید.
19. **Refresh token** نمایش داده میشود. آن را کپی کنید.
20. Secret زیر را در GitHub بسازید:

<div dir="ltr" markdown="1">

```
GOOGLE_REFRESH_TOKEN → Refresh Token خود را بچسبانید
```

</div>

> ⚠️ **نکته مهم:** Refresh Token فقط **یک بار** نمایش داده میشود. اگر آن را گم کنید، باید دوباره از اول مراحل را طی کنید. همچنین اگر از OAuth Playground استفاده میکنید، حتماً تیک Auto-refresh را بزنید.

> ℹ️ پس از تنظیم هر سه Secret، در هر workflow که اجرا میکنید، کافیست گزینه **upload_to_drive** را تیک بزنید تا فایلها به جای مخزن GitHub، در Google Drive شما (پوشه `github-actions`) ذخیره شوند.

---

## 📋 راهنمای کامل هر گردش کار (Workflow)

در این بخش، **تمامی ۱۷ گردش کار** به همراه **Secretهای مورد نیاز هر کدام**، **نحوه استفاده**، و **نکات مهم** توضیح داده شده است.

---

### ۱. دانلودر یوتیوب (youtube-downloader)

<div dir="ltr" markdown="1">

**Secretهای مورد نیاز:** `YOUTUBE_COOKIES` (اختیاری، توصیه میشود)
**Secretهای Google Drive:** `GOOGLE_CLIENT_ID`, `GOOGLE_CLIENT_SECRET`, `GOOGLE_REFRESH_TOKEN` (اختیاری)
**زمان اجرا:** حداکثر ۷۰۰ دقیقه

</div>

#### ✨ ویژگیها:
- تلاش با شبیهسازی کلاینت اندروید، iOS، و بدون کوکی
- در صورت شکست، از ابزارهای جایگزین مانند pytube، سرویسهای API خارجی و youtube‑dl استفاده میکند
- پشتیبانی از لینکهای غیر یوتیوب (دانلود مستقیم با wget)
- انتخاب هوشمند نزدیکترین کیفیت موجود
- Remux خودکار با ffmpeg برای سازگاری کامل
- تقسیم خودکار فایلهای >۹۹MB به ZIP چندبخشی
- **🆕 آپلود خودکار در Google Drive**

#### 📝 نحوه استفاده:
1. **Actions** → **youtube-downloader** → **Run workflow**
2. ورودی: `URL v/a رزولوشن fps` (fps اختیاری)

<div dir="ltr" markdown="1">

```
https://www.youtube.com/watch?v=dfdXGw1xY9A v 480
https://www.youtube.com/watch?v=dfdXGw1xY9A v 1080 60
https://www.youtube.com/watch?v=VIDEO_ID a max
https://www.youtube.com/watch?v=VIDEO_ID v 4k
```

</div>

- `v` = ویدیو، `a` = صدا
- رزولوشن: `max`, `min`, `1080`, `2k`, `4k` و …
- FPS: اختیاری (مثلاً `60`)
- اگر `v/a` ندهید، پیشفرض **حداکثر کیفیت ویدیو** انتخاب میشود.
- برای صدا (`a max`) خروجی به صورت `.opus` است.

3. **🆕 گزینههای جدید:**
   - `output_format`: انتخاب فرمت خروجی (mp4 یا mp3)
   - `video_quality`: حداکثر رزولوشن (4K, 1080, 720, 480, 360, best)
   - `audio_quality`: بیتریت صدا (320, 192, 128, 64)
   - `bundle_all`: تجمیع همه فایلها در یک ZIP
   - `upload_as_release`: آپلود به عنوان GitHub Release
   - `upload_to_drive`: **🆕 آپلود در Google Drive** (به جای مخزن)

4. خروجی در پوشه `youtube/` (فایلهای بزرگ به ZIP چندبخشی تبدیل میشوند)

---

### ۲. دانلودر اینستاگرام (instagram-downloader)

<div dir="ltr" markdown="1">

**Secretهای مورد نیاز:** `INSTAGRAM_COOKIES` (اختیاری)
**Secretهای Google Drive:** `GOOGLE_CLIENT_ID`, `GOOGLE_CLIENT_SECRET`, `GOOGLE_REFRESH_TOKEN` (اختیاری)

</div>

#### 📝 نحوه استفاده:
1. **Actions** → **instagram-downloader** → **Run workflow**
2. لینکها را با کاما، فاصله یا خط جدید جدا کنید.

<div dir="ltr" markdown="1">

```
https://www.instagram.com/p/DX2y7oLDFOb/,
https://www.instagram.com/reel/DVRXhn0gjL3/,
https://www.instagram.com/p/DX6US4uCNGb/
```

</div>

3. **🆕 گزینههای جدید:**
   - `upload_as_release`: آپلود به عنوان GitHub Release
   - `upload_to_drive`: **🆕 آپلود در Google Drive**

4. خروجی ZIP در پوشه `instagram/`.

> ⚠️ خطای ۴۲۹ یعنی کوکی اینستاگرام منقضی یا محدود شده — کوکی جدید بگیرید.

---

### ۳. دانلودر X/توییتر (x-downloader)

<div dir="ltr" markdown="1">

**Secretهای مورد نیاز:** `X_COOKIES` (**الزامی** ⚠️)

</div>

#### 📝 نحوه استفاده:
1. **Actions** → **x-downloader** → **Run workflow**
2. لینکها را با کاما، فاصله یا خط جدید وارد کنید.

<div dir="ltr" markdown="1">

```
https://x.com/username/status/123456789,
https://x.com/otheruser/status/987654321
```

</div>

3. خروجی ZIP در پوشه `x/`.

---

### ۴. دانلودر مستقیم (direct-downloader)

<div dir="ltr" markdown="1">

**Secretهای مورد نیاز:** هیچکدام الزامی نیست
**Secretهای Google Drive:** `GOOGLE_CLIENT_ID`, `GOOGLE_CLIENT_SECRET`, `GOOGLE_REFRESH_TOKEN` (اختیاری)

</div>

#### ✨ ویژگیها:
- دانلود با `aria2c` (۱۶ اتصال همزمان — بسیار سریع)
- پشتیبانی از تمام لینکهای مستقیم (`.zip`, `.mp4`, `.apk`, `.pdf` و …)

#### 📝 نحوه استفاده:
1. **Actions** → **direct-downloader** → **Run workflow**
2. لینکهای مستقیم را بچسبانید.

<div dir="ltr" markdown="1">

```
https://example.com/file.zip, https://example.com/video.mp4
```

</div>

3. **🆕 گزینههای جدید:**
   - `bundle_all`: تجمیع همه فایلها در یک ZIP
   - `upload_as_release`: آپلود به عنوان GitHub Release
   - `upload_to_drive`: **🆕 آپلود در Google Drive**

4. فایلها در `direct/` ذخیره میشوند (بزرگتر از ۹۹MB به ZIP چندبخشی تقسیم میشوند).

---

### ۵. آرشیو کانال تلگرام (telegram-fetcher)

<div dir="ltr" markdown="1">

**Secretهای مورد نیاز:** هیچکدام
**اجرای خودکار:** هر ۳۰ دقیقه یکبار (cron)

</div>

#### 📝 نحوه استفاده:
1. فایل `telegram/channels.json` را ویرایش کنید. **نام کانال را بدون @ وارد کنید.**

<div dir="ltr" markdown="1">

```
["VahidOOnLine", "mwarmonitor", "channelname"]
```

</div>

2. **Actions** → **telegram-fetcher** → **Run workflow** (یا منتظر اجرای خودکار بمانید).

> ⚠️ فقط کانالهای عمومی. زمانبندی خودکار ممکن است با تأخیر ۱ تا ۶ ساعت اجرا شود.

---

### ۶. دانلودر تلگرام بتا (telegram-downloader-beta)

<div dir="ltr" markdown="1">

**Secretهای مورد نیاز:** هیچکدام
**محدودیت:** حداکثر ۱۰۰۰ لینک

</div>

#### 📝 نحوه استفاده:
1. **Actions** → **telegram-downloader-beta** → **Run workflow**
2. لینک پستهای تلگرام را وارد کنید.

<div dir="ltr" markdown="1">

```
https://t.me/channelname/123, https://t.me/channelname/456
```

</div>

3. فایلها در `telegram/downloader/` ذخیره میشوند.

---

### ۷. ضبط وبسایت — PDF و MHTML (website-capture)

<div dir="ltr" markdown="1">

**Secretهای مورد نیاز:** هیچکدام
**Secretهای Google Drive:** `GOOGLE_CLIENT_ID`, `GOOGLE_CLIENT_SECRET`, `GOOGLE_REFRESH_TOKEN` (اختیاری)
**محدودیت:** حداکثر ۵۰۰ لینک داخلی، مهلت ۳۰ دقیقه

</div>

#### ✨ ویژگیها:
- **PDF** با کیفیت بالا (مناسب برای چاپ و آرشیو)
- **MHTML** (بایگانی کامل صفحه شامل تصاویر، CSS و فونتها — قابل باز شدن در مرورگر)
- رندر با **Playwright + Chromium** برای صفحات داینامیک

#### 📝 نحوه استفاده:
1. **Actions** → **website-capture** → **Run workflow**
2. آدرس کامل با `https://` را وارد کنید.

<div dir="ltr" markdown="1">

```
https://example.com/article
https://github.com/ProAlit/aio-downloader
```

</div>

3. **🆕 گزینههای جدید:**
   - `capture_mhtml`: ذخیره به صورت MHTML (پیشفرض: فعال)
   - `capture_pdf`: ذخیره به صورت PDF (پیشفرض: فعال)
   - `upload_as_release`: آپلود به عنوان GitHub Release
   - `upload_to_drive`: **🆕 آپلود در Google Drive**

4. خروجیها در پوشه `website/` — هم فایل PDF و هم فایل MHTML.

> ⚠️ فقط سایتهای عمومی. صفحات SPA سنگین ممکن است کامل رندر نشوند.

---

### ۸. لیچر قدرتمند (aio-leecher)

<div dir="ltr" markdown="1">

**Secretهای مورد نیاز:** `YOUTUBE_COOKIES`, `INSTAGRAM_COOKIES`, `X_COOKIES` (همگی اختیاری، خودکار تشخیص داده میشوند)
**Secretهای Google Drive:** `GOOGLE_CLIENT_ID`, `GOOGLE_CLIENT_SECRET`, `GOOGLE_REFRESH_TOKEN` (اختیاری)
**زمان اجرا:** حداکثر ۷۰۰ دقیقه

</div>

**قدرتمندترین بخش!** از یوتیوب و اینستاگرام تا تیکتاک، ساندکلاد، اسپاتیفای و بیش از ۱۸۰۰ سایت دیگر.

#### ⚡ حالت خام (Raw) — توصیه اصلی
برای بهترین نتیجه، **حتماً از حالت خام استفاده کنید.** کافیست بعد از لینک، دو خط فاصله `--` بگذارید و سپس هر آرگومان معتبر `yt-dlp` را بنویسید.

<div dir="ltr" markdown="1">

```
https://www.youtube.com/watch?v=VIDEO_ID -- --format "bestvideo[height<=1080]+bestaudio/best[height<=1080]" --merge-output-format mkv
https://www.tiktok.com/@user/video/ID -- --write-subs --sub-lang en
# یوتیوب با زیرنویس
https://www.youtube.com/watch?v=ID -- -f "bestvideo[height<=1080]+bestaudio" --write-subs --sub-lang en --merge-output-format mp4
# اینستاگرام
https://www.instagram.com/p/CODE -- --format best
# توییتر
https://x.com/user/status/ID -- --format best
# پینترست
https://www.pinterest.com/pin/ID -- --format best
# ساندکلاد
https://soundcloud.com/artist/track -- --format bestaudio
```

</div>

#### حالت میانبر
هنوز هم میتوانید از `v` (ویدیو) و `a` (صدا) استفاده کنید، ولی برای محتوایی که ویدیو/صدا/موسیقی نیست، نرخ شکست بالایی دارد.

<div dir="ltr" markdown="1">

```
https://www.youtube.com/watch?v=dfdXGw1xY9A v 1080
https://soundcloud.com/artist/track a 320
```

</div>

#### ❓ اگر دستور بلد نیستید
از چتباتهای هوش مصنوعی مثل **[chat.deepseek.com](https://chat.deepseek.com)** (بدون فیلتر) بپرسید: *"یک دستور yt‑dlp برای دانلود این لینک با بهترین کیفیت بنویس"* — دستور تولید شده را در حالت خام استفاده کنید.

#### 🆕 گزینههای جدید:
- `bundle_all`: تجمیع همه فایلها در یک ZIP
- `upload_as_release`: آپلود به عنوان GitHub Release
- `upload_to_drive`: **🆕 آپلود در Google Drive**

---

### ۹. دانلودر ساندکلود (soundcloud-downloader)

<div dir="ltr" markdown="1">

**Secretهای مورد نیاز:** هیچکدام
**Secretهای Google Drive:** `GOOGLE_CLIENT_ID`, `GOOGLE_CLIENT_SECRET`, `GOOGLE_REFRESH_TOKEN` (اختیاری)

</div>

#### 📝 نحوه استفاده:
1. **Actions** → **soundcloud-downloader** → **Run workflow**
2. لینکها را وارد کنید.

<div dir="ltr" markdown="1">

```
https://soundcloud.com/artist/track,
https://soundcloud.com/artist/track
```

</div>

3. **🆕 گزینههای جدید:**
   - `output_format`: فرمت خروجی (mp3, flac, ogg, opus, m4a, wav)
   - `audio_quality`: کیفیت صدا (128k, 192k, 256k, 320k)
   - `upload_as_release`: آپلود به عنوان GitHub Release
   - `upload_to_drive`: **🆕 آپلود در Google Drive**

4. فایلها در `music/` (تبدیل خودکار با ffmpeg).

---

### ۱۰. دانلودر اسپاتیفای (spotify-downloader) 🆕

<div dir="ltr" markdown="1">

**Secretهای مورد نیاز:** هیچکدام (SpotiFLAC بدون نیاز به اکانت کار میکند)
**Secretهای Google Drive:** `GOOGLE_CLIENT_ID`, `GOOGLE_CLIENT_SECRET`, `GOOGLE_REFRESH_TOKEN` (اختیاری)
**سرویسهای پشتیبانیشده:** Spotify, Tidal, Apple Music, SoundCloud, YouTube, Pandora

</div>

> ℹ️ این دانلودر از **SpotiFLAC** استفاده میکند که بدون نیاز به هیچ اکانتی، موسیقی را با بهترین کیفیت ممکن (از جمله FLAC بدون اتلاف) دانلود میکند.

#### 📝 نحوه استفاده:
1. **Actions** → **spotify-downloader** → **Run workflow**
2. لینکها را وارد کنید (ترک، آلبوم، پلیلیست، آرتیست).

<div dir="ltr" markdown="1">

```
https://open.spotify.com/track/xxxxx,
https://open.spotify.com/album/xxxxx,
https://open.spotify.com/playlist/xxxxx
```

</div>

3. **گزینهها:**
   - `output_format`: فرمت خروجی (flac, mp3, m4a, ogg, opus, wav) — پیشفرض: flac
   - `audio_quality`: کیفیت (LOSSLESS, HI_RES_LOSSLESS, DOLBY_ATMOS, HIGH, LOW, 320k, 256k, 192k, 128k) — پیشفرض: LOSSLESS
   - `upload_as_release`: آپلود به عنوان GitHub Release
   - `upload_to_drive`: **🆕 آپلود در Google Drive**

4. فایلها در `music/` ذخیره میشوند.

---

### ۱۱. پاککننده جامع (aio-cleaner)

<div dir="ltr" markdown="1">

**Secretهای مورد نیاز:** هیچکدام

</div>

> ⚠️ فضای مخزن رایگان GitHub حدود ۵ گیگابایت است. فایلهای حجیم فضا را پر میکنند — **مرتب پاکسازی کنید.**

#### 📝 پلتفرمهای قابل پاک شدن:

| پلتفرم | چه چیزهایی حذف میشود |
|---|---|
| تلگرام | `telegram/content/`، `telegram.md`، `last_ids.json` |
| تلگرام دانلودر | `telegram/downloader/` |
| یوتیوب | کل `youtube/` |
| اینستاگرام | کل `instagram/` |
| X | کل `x/` |
| وبسایت | کل `website/` |
| لیچر | کل `leecher/` |
| گوگل پلی | کل `google-play/` |
| موسیقی | کل `music/` |
| مستقیم | کل `direct/` |
| MEGA | کل `mega-nz/` 🆕 |

#### 📝 نحوه اجرا:
1. **Actions** → **aio-cleaner** → **Run workflow**
2. چکباکسهای دلخواه را تیک بزنید (یا **Clean ALL platforms**)
3. اجرا کنید.

> ❗ حذف دائمی است — ابتدا فایلهای مهم را دانلود کنید. **حتما بعد هر آپدیت مرحله کلینر رو برای همه اجرا کنید وگرنه دانلودهاتون به شدت کند انجام میشه!!**

---

### ۱۲. دانلودر گوگل پلی (google-play-downloader)

<div dir="ltr" markdown="1">

**Secretهای مورد نیاز:** هیچکدام (احراز هویت خودکار)
**Secretهای Google Drive:** `GOOGLE_CLIENT_ID`, `GOOGLE_CLIENT_SECRET`, `GOOGLE_REFRESH_TOKEN` (اختیاری)

</div>

#### 📝 نحوه استفاده:
1. **Actions** → **google-play-downloader** → **Run workflow**
2. **app**: نام پکیج (مثلاً `com.google.android.youtube`) یا لینک گوگل پلی.
3. **architecture**: `arm64` (پیشفرض) یا `armv7`.
4. **merge_splits**: ادغام APKهای چندبخشی (پیشفرض فعال).

<div dir="ltr" markdown="1">

```
app: com.spotify.music
architecture: arm64
merge_splits: true
```

</div>

5. **🆕 گزینههای جدید:**
   - `bundle_all`: تجمیع همه APKها در یک ZIP
   - `upload_as_release`: آپلود به عنوان GitHub Release
   - `upload_to_drive`: **🆕 آپلود در Google Drive**

6. فایل APK (زیپشده) در `google-play/`.

> ℹ️ برای پیدا کردن نام پکیج، به لینک برنامه در گوگل پلی دقت کنید: `id=com.example.app`.

---

### ۱۳. دانلودر MEGA.nz (mega-nz-downloader) 🆕

<div dir="ltr" markdown="1">

**Secretهای مورد نیاز:** هیچکدام (بدون نیاز به اکانت MEGA)
**Secretهای Google Drive:** `GOOGLE_CLIENT_ID`, `GOOGLE_CLIENT_SECRET`, `GOOGLE_REFRESH_TOKEN` (اختیاری)

</div>

#### ✨ ویژگیها:
- دانلود فایل و فولدر از MEGA.nz بدون نیاز به اکانت
- استفاده از megatools برای دانلود مطمئن
- پشتیبانی از لینکهای فایل و فولدر

#### 📝 نحوه استفاده:
1. **Actions** → **mega-nz-downloader** → **Run workflow**
2. لینکهای MEGA را وارد کنید.

<div dir="ltr" markdown="1">

```
https://mega.nz/file/xxxxx,
https://mega.nz/folder/xxxxx
```

</div>

3. **گزینهها:**
   - `bundle_all`: تجمیع همه فایلها در یک ZIP
   - `upload_method`: روش آپلود (`split_push` یا `release`)
   - `upload_to_drive`: **🆕 آپلود در Google Drive**

4. فایلها در `mega-nz/` ذخیره میشوند.

---

### ۱۴. Exit Node پایتون — داینامیک (python-mhrv-dynamic-exit-node)

<div dir="ltr" markdown="1">

**Secretهای مورد نیاز:** `TUNNEL_AUTH_KEY` (اختیاری)
**خروجی:** URL موقت trycloudflare.com (اعتبار ۶ ساعت)

</div>

#### 📝 نحوه استفاده:
1. **Actions** → **python-mhrv-dynamic-exit-node** → **Run workflow**
2. پس از ۲۰-۳۰ ثانیه در لاگ، خطی شبیه زیر میبینید:

<div dir="ltr" markdown="1">

```
https://random-name.trycloudflare.com
```

</div>

3. این URL را کپی و در بخش `exit_node` کانفیگ VPN خود قرار دهید:

<div dir="ltr" markdown="1">

```
"exit_node": {
  "enabled": true,
  "provider": "vps",
  "url": "https://random-name.trycloudflare.com",
  "psk": "همان_رمز_مخفی"
}
```

</div>

> ⏱️ اعتبار هر URL تا ۶ ساعت است. بعداً باید دوباره اجرا کنید.

---

### ۱۵. Exit Node پایتون — استاتیک (python-mhrv-static-exit-node) 🆕

<div dir="ltr" markdown="1">

**Secretهای مورد نیاز:** `TUNNEL_AUTH_KEY` (اختیاری), `CF_TUNNEL_TOKEN` (الزامی ⚠️)
**خروجی:** دامنه ثابت Cloudflare (مثلاً `exit.yourdomain.com`)

</div>

#### 📝 نحوه استفاده:
1. ابتدا `CF_TUNNEL_TOKEN` را تنظیم کنید (راهنما در بخش Secretها).
2. **Actions** → **python-mhrv-static-exit-node** → **Run workflow**
3. تونل روی دامنه ثابت شما فعال میشود.

> ℹ️ مزیت این روش نسبت به داینامیک: URL ثابت است و نیازی به بهروزرسانی مداوم کانفیگ نیست.

---

### ۱۶. Exit Node Zyrln — داینامیک (zyrln-cloudflare-dynamic-exit-node) 🆕

<div dir="ltr" markdown="1">

**Secretهای مورد نیاز:** `TUNNEL_AUTH_KEY` (اختیاری)
**زبان برنامهنویسی:** Go (عملکرد سریعتر)
**خروجی:** URL موقت trycloudflare.com (اعتبار ۶ ساعت)

</div>

#### 📝 نحوه استفاده:
1. **Actions** → **zyrln-cloudflare-dynamic-exit-node** → **Run workflow**
2. URL موقت در لاگ نمایش داده میشود.
3. مانند روش پایتون، URL را در کانفیگ VPN خود قرار دهید.

> ℹ️ این نسخه با زبان Go نوشته شده و برای کاربرانی که به دنبال عملکرد سریعتر و مصرف کمتر هستند مناسب است.

---

### ۱۷. Exit Node Zyrln — استاتیک (zyrln-cloudflare-static-exit-node) 🆕

<div dir="ltr" markdown="1">

**Secretهای مورد نیاز:** `TUNNEL_AUTH_KEY` (اختیاری), `CF_TUNNEL_TOKEN` (الزامی ⚠️)
**زبان برنامهنویسی:** Go

</div>

#### 📝 نحوه استفاده:
1. `CF_TUNNEL_TOKEN` را تنظیم کنید.
2. **Actions** → **zyrln-cloudflare-static-exit-node** → **Run workflow**
3. تونل روی دامنه ثابت Cloudflare شما فعال میشود.

---

## 🆕 ویژگیهای جدید (که در README قبلی نیستند)

### ۱. آپلود خودکار در Google Drive
تمام workflowهای اصلی اکنون از گزینه `upload_to_drive` پشتیبانی میکنند. با تنظیم سه Secret مربوط به Google، فایلها مستقیماً در پوشه `github-actions` در Google Drive شما ذخیره میشوند. این ویژگی:
- فضای مخزن GitHub را اشغال نمیکند
- محدودیت ۵ گیگابایتی مخزن را دور میزند
- فایلهای حجیم (>2GB) را میتوان بدون تقسیم شدن آپلود کرد

### ۲. آپلود به عنوان GitHub Release
گزینه `upload_as_release` در بسیاری از workflowها اضافه شده است. این گزینه فایلها را به عنوان Release در مخزن شما منتشر میکند (به جای push در مخزن).

### ۳. گزینه bundle_all
در workflowهای یوتیوب، مستقیم، گوگل پلی، لیچر و MEGA، گزینه `bundle_all` به شما امکان میدهد همه فایلهای دانلودی را در یک فایل ZIP تجمیع کنید.

### ۴. دانلودر MEGA.nz
دانلود فایل و فولدر از MEGA.nz بدون نیاز به اکانت.

### ۵. دانلودر اسپاتیفای (مجزا از ساندکلود)
قبلاً در README به صورت ترکیبی با ساندکلود ذکر شده بود. اکنون یک workflow مجزا با پشتیبانی از Spotify, Tidal, Apple Music, SoundCloud, YouTube, Pandora و قابلیت دانلود FLAC بدون اتلاف.

### ۶. Exit Nodeهای Zyrln (Go)
دو workflow جدید برای Exit Node با زبان Go اضافه شده است (داینامیک و استاتیک).

### ۷. Exit Node استاتیک پایتون
قبلاً فقط نسخه داینامیک در README بود. نسخه استاتیک با دامنه ثابت اضافه شده است.

### ۸. گزینههای پیشرفته در youtube-downloader
ورودیهای جدید: `output_format` (mp4/mp3), `video_quality`, `audio_quality`.

---

## 🐢 مشکل کندی checkout و راهحل آن

گاهی مرحلهی **Checkout repository** در workflowها بسیار کند میشود. این مشکل دو علت اصلی دارد:

| دلیل | توضیح |
|---|---|
| **انباشته شدن فایلهای ریز تلگرام** | اگر از telegram-fetcher زیاد استفاده کنید، هزاران فایل کوچک در `telegram/content/` ذخیره میشود. از آنجا که checkout کل مخزن را میخواند، این حجم بالا سرعت را کاهش میدهد و روی **تمام workflowهای دیگر** اثر میگذارد. |
| **اوج مصرف GitHub Actions (Peak Times)** | در ساعات شلوغی سرورهای GitHub (معمولاً روزهای کاری، ساعتهای اداری UTC)، عملیات checkout برای همه کندتر میشود — حتی اگر فایلهای کمی داشته باشید. |

### راه حل:
- **برای فایلهای تلگرام:** هر از گاهی با `aio-cleaner`، گزینه **Clean Telegram** را اجرا کنید.
- **برای peak times:** صبر کنید تا از ساعت شلوغی خارج شوید، یا workflow را در ساعات خلوتتر اجرا کنید.

> ❗ **نکته خیلی مهم!!! حتما بعد هر آپدیت مرحله کلینر رو برای همه اجرا کنید وگرنه دانلودهاتون به شدت کند انجام میشه!!**

---

## ⚠️ محدودیتها و هشدارهای مهم

| هشدار | توضیح |
|---|---|
| **فضای مخزن ≈ ۵ گیگابایت** | فایلهای دانلودی (مخصوصاً ویدیو) به سرعت فضا را پر میکنند. مرتباً از AIO Cleaner استفاده کنید یا از Google Drive برای آپلود استفاده کنید. |
| **حداکثر زمان اجرا** | ۶ ساعت (برای مخازن عمومی، دقیقه رایگان نامحدود) |
| **فایلهای >۹۹MB** | خودکار به ZIP چندبخشی تقسیم میشوند — با 7‑Zip یا WinRAR باز کنید. |
| **دانلودر X** | حتماً کوکی `X_COOKIES` را تنظیم کنید. |
| **تلگرام** | فقط کانالهای عمومی. نام کانال را **بدون @** وارد کنید. |
| **وبسایت** | فقط صفحات عمومی (بدون دیوار ورود). |
| **گوگل پلی** | احراز هویت خودکار — بدون نیاز به اکانت گوگل. |
| **MEGA** | بدون نیاز به اکانت — لینکهای عمومی را دانلود میکند. |
| **همگامسازی فورک** | حداقل هفتهای یکبار با دکمه Sync fork انجام دهید. اگر commit اضافی دارید، آن را Discard کنید. |
| **کوکیها** | فقط در پنجره ناشناس استخراج کنید و پس از خروجی گرفتن، پنجره را ببندید. **حتماً از robots.txt استفاده کنید.** |
| **Google Drive** | Refresh Token ممکن است بعد از مدتها منقضی شود — در صورت خطای 401، دوباره Refresh Token بگیرید. |

---

## 📞 پشتیبانی

باگ یا پیشنهاد؟ یک [Issue](https://github.com/ProAlit/aio-downloader/issues) باز کنید و ذکر کنید:
- نام گردشکار
- ورودی (بدون کوکی)
- پیام خطا از تب Actions

---

## 📋 خلاصه تمام Secretها

| Secret Name | Workflowها | الزامی؟ | توضیح |
|---|---|---|---|
| `YOUTUBE_COOKIES` | youtube-downloader, aio-leecher | اختیاری | کوکی یوتیوب (با robots.txt بگیرید) |
| `INSTAGRAM_COOKIES` | instagram-downloader, aio-leecher | اختیاری | کوکی اینستاگرام (با robots.txt بگیرید) |
| `X_COOKIES` | x-downloader, aio-leecher | **الزامی** | کوکی X/توییتر (با robots.txt بگیرید) |
| `TUNNEL_AUTH_KEY` | exit-nodeها | اختیاری | رمز PSK دلخواه برای تونل |
| `CF_TUNNEL_TOKEN` | exit-nodeهای استاتیک | اختیاری | توکن تونل Cloudflare |
| `GOOGLE_CLIENT_ID` | تمام workflowها (آپلود در Drive) | اختیاری | OAuth Client ID از Google Cloud |
| `GOOGLE_CLIENT_SECRET` | تمام workflowها (آپلود در Drive) | اختیاری | OAuth Client Secret از Google Cloud |
| `GOOGLE_REFRESH_TOKEN` | تمام workflowها (آپلود در Drive) | اختیاری | Refresh Token از OAuth Playground |

---

⭐⭐⭐ **اگر این پروژه برایتان مفید است، لطفاً ستاره بدهید!** ⭐⭐⭐

</div>
