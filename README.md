<div align="center">

# PXCloud Tunnel

**دو سرور را وصل کنید؛ اتصال‌ها را از یک منو مدیریت کنید.**

Connect your servers. Manage your tunnels from one menu.

<p>
<a href="https://t.me/irsupplm_bot"><img alt="Buy a license" src="https://img.shields.io/badge/BUY_A_LICENSE-irsupplm__bot-F4B942?style=for-the-badge&logo=telegram&logoColor=white"></a>
<a href="https://github.com/IRSupp/PXCloud-Tunnel/releases/tag/v1.7.3"><img alt="Download 1.7.3" src="https://img.shields.io/badge/DOWNLOAD-v1.7.3-2563EB?style=for-the-badge&logo=github&logoColor=white"></a>
</p>

**[خرید لایسنس / Buy a license](https://t.me/irsupplm_bot) · [کانال تلگرام / Telegram channel](https://t.me/irsuppchannel)**

[راهنمای فارسی](#فارسی) · [English guide](#english)

نسخهٔ پایدار **1.7.3** · Ubuntu **24.04** · **x86_64 / amd64**

</div>

---

<div dir="rtl">

## فارسی

PXCloud بین سرور ایران و سرور خارج شما اتصال برقرار می‌کند. بعد مشخص می‌کنید ترافیک کدام کاربران یا سرویس‌ها از سرور خارج عبور کند. از همان منو می‌توانید اتصال را متوقف یا دوباره راه‌اندازی کنید، پینگ و سرعت بگیرید و در صورت نصب چند مسیر، انتخاب مسیر را خودکار کنید.

**اولین بار است نصب می‌کنید؟ مراحل زیر را به‌ترتیب انجام دهید.** این راهنما برای نصب تازه است؛ راهنمای ارتقا و رفع خطا پایین صفحه قرار دارد.

### قبل از شروع چه چیزهایی لازم دارید؟

- یک سرور ایران و یک سرور خارج، هر دو با **Ubuntu 24.04 و معماری amd64 / x86_64**.
- IP، نام کاربری `root` و رمز یا کلید ورود هر دو سرور.
- برنامه‌ای برای ورود به سرور با SSH، مثل نرم‌افزاری که معمولاً برای مدیریت سرور استفاده می‌کنید.
- سرویس کاربران، مثل WireGuard یا Xray، باید جداگانه روی سرور ایران راه‌اندازی شده باشد؛ PXCloud خودش حساب کاربری یا کانفیگ اتصال کاربران نمی‌سازد.

در این راهنما **A یعنی ایران** و **B یعنی خارج**؛ سرور خارج می‌تواند در هر کشوری باشد. دو پنجرهٔ SSH باز کنید و نام آن‌ها را «ایران» و «خارج» بگذارید. دستورها را داخل پنجرهٔ سرور بنویسید، نه در ترمینال ویندوز. در منوها شماره یا حرف کنار گزینه را بنویسید و Enter بزنید؛ حروف بزرگ و کوچک فرقی ندارند. تانل‌ها از 1 تا 5 هستند، لایسنس L، حذف X و خروج یا بازگشت همیشه 0 است.

### ۱. لایسنس بخرید

وارد **[ربات خرید @irsupplm_bot](https://t.me/irsupplm_bot)** شوید، محصول **PXCloud Tunnel** و پلن موردنظر را انتخاب کنید. **IP عمومی سرور ایران** را برای لایسنس ثبت کنید و کلیدی را که ربات می‌دهد نگه دارید. قیمت و مدت هر پلن داخل ربات نمایش داده می‌شود.

یک لایسنس برای یک جفت سرور ایران و خارج است. اگر مدیر قبلاً IP ایران شما را معاف کرده، به‌جای خرید، روش «IP معاف» را در بخش پرسش‌های رایج پایین صفحه بخوانید.

### ۲. برنامه را روی هر دو سرور نصب کنید

**محل اجرا: یک بار روی ایران، یک بار روی خارج.**

با کاربر `root` وارد شوید. تمام دستورهای این کادر را کپی و اجرا کنید؛ فایل‌های نسخهٔ 1.7.3 دریافت و بررسی می‌شوند و سپس نصب شروع می‌شود:

</div>

```bash
mkdir -p /root/pxcloud-install-1.7.3 &&
cd /root/pxcloud-install-1.7.3 &&
curl -fLO https://github.com/IRSupp/PXCloud-Tunnel/releases/download/v1.7.3/PXCloud-Tunnel-1.7.3-linux-x86_64.tar.gz &&
curl -fLO https://github.com/IRSupp/PXCloud-Tunnel/releases/download/v1.7.3/PXCloud-Tunnel-Install.sh &&
curl -fLO https://github.com/IRSupp/PXCloud-Tunnel/releases/download/v1.7.3/SHA256SUMS &&
sha256sum -c SHA256SUMS &&
bash PXCloud-Tunnel-Install.sh
```

<div dir="rtl">

در پایان، با دستور زیر نسخه را ببینید. باید **1.7.3** نمایش داده شود:

</div>

```bash
pxcloud --version
```

<div dir="rtl">

اگر دریافت فایل یا نصب خطا داد، به مرحلهٔ بعد نروید؛ بخش «اگر به مشکل خوردید» را ببینید. موتورهای اتصال داخل بسته هستند، ولی نصب بعضی ابزارهای سیستم همچنان به اینترنت نیاز دارد.

### ۳. لایسنس را فعال و دو سرور را به هم معرفی کنید

**روی ایران** این دستور را اجرا کنید:

</div>

```bash
pxcloud license
```

<div dir="rtl">

1. گزینهٔ **1 — Activate Iran license** را بزنید و کلید خریداری‌شده را وارد کنید.
2. پس از موفقیت، در همان منو گزینهٔ **3 — Pair foreign server (from Iran)** را بزنید.
3. در سؤال `Foreign public IPv4`، **IP سرور خارج** را وارد کنید.
4. در سؤال `Invitation output path`، این مسیر را وارد کنید: `/root/PXCloud-invitation.json`.
5. با **0** از این منو خارج شوید تا بتوانید دستور بعدی را اجرا کنید.

حالا فایل معرفی را به خارج بفرستید. **کادر زیر را روی ایران اجرا کنید.** خودش IP خارج را از شما می‌پرسد؛ بعد ممکن است رمز ورود سرور خارج را بخواهد:

</div>

```bash
read -r -p "Foreign server IP: " PXC_FOREIGN_IP &&
scp /root/PXCloud-invitation.json "root@${PXC_FOREIGN_IP}:/root/PXCloud-invitation.json"
```

<div dir="rtl">

هنگام نوشتن رمز SSH چیزی روی صفحه دیده نمی‌شود؛ طبیعی است. اگر اولین اتصال سؤال تأیید هویت سرور نشان داد، اثرانگشت آن را با اطلاعات سرورتان تطبیق دهید.

**روی خارج** دستور `pxcloud license` را اجرا کنید، گزینهٔ **4 — Join pair (on foreign server)** را بزنید و مسیر `/root/PXCloud-invitation.json` را وارد کنید. پس از موفقیت، **0** را بزنید.

**فایل معرفی را ظرف ۱۵ دقیقه استفاده کنید.** اگر زمانش گذشت، دوباره از گزینهٔ 3 روی ایران فایل تازه بسازید و انتقال دهید. این فایل خصوصی است؛ آن را در کانال یا گروه ارسال نکنید.

### ۴. اولین تانل را بسازید

**روی ایران** دستور `pxcloud` را بزنید:

1. **1 — Rakhsh** و سپس **1 — Install** را انتخاب کنید.
2. اگر اولین اتصال این جفت‌سرور است، نقش **A** و IP سرور خارج را وارد کنید. IP ایران خودکار تشخیص داده می‌شود؛ اگر تشخیص ممکن نباشد، برنامه می‌پرسد.
3. مقابل `Use advanced settings?` برای تنظیمات پیشنهادی فقط Enter بزنید. سؤال‌های سایر تانل‌ها نمایش داده نمی‌شوند.
4. بلافاصله بعد از نصب موفق، عنوان زرد **SERVER B CONNECTION CONFIG** و زیر آن متن کامل کانفیگ نمایش داده می‌شود. همهٔ خط‌ها را از `PXCT1:` تا `END` کپی کنید. تا Enter نزنید، برنامه به منو برنمی‌گردد. مسیر فایل خصوصی هم بالای همین بخش نوشته شده است.

**روی خارج** دستور `pxcloud` را بزنید، **1 — Rakhsh** و سپس **1 — Install** را انتخاب کنید. اگر نقش پرسیده شد، **B** را وارد کنید. برای وارد کردن تنظیمات سه راه دارید؛ فقط یکی را انجام دهید:

| گزینهٔ سمت خارج | چه کار کنید؟ |
| :--- | :--- |
| **1 — Paste Connection Config** | بلوک نمایش‌داده‌شده در پایان نصب ایران را از `PXCT1:` تا `END` کپی کنید و در سؤال سمت خارج بچسبانید. اگر صفحه را بسته‌اید، روی ایران **C — Current Config → P** و سپس `SHOW` آن را دوباره نمایش می‌دهد. |
| **2 — Import Config File** | فایل خصوصی نشان‌داده‌شده روی ایران را به خارج منتقل کنید؛ سپس مسیر آن را وارد کنید. دستور نمونه پایین همین بخش است. |
| **3 — Manual Setup (step by step)** | روی ایران، داخل Current Config گزینهٔ **M** و سپس `SHOW` را بزنید. سمت خارج تک‌تک مقدارها را با همان ترتیب و عنوان می‌پرسد. برای لغو ورود دستی `BACK` بنویسید. |

روش اول معمولاً ساده‌تر است. در بستهٔ اصلاح‌شدهٔ 1.7.3، اگر عنوان زرد SERVER B CONNECTION CONFIG هم همراه بلوک کپی شود، برنامه آن را می‌پذیرد. متن کپی‌شده و مقادیر دستی حاوی کلید خصوصی‌اند؛ آن‌ها را در کانال، گروه یا تیکت عمومی نگذارید. کد کپی‌شدنی صرفاً قالب انتقال است و رمزگذاری محسوب نمی‌شود. کلیدها و گواهی‌های روش دستی باید دقیقاً از خروجی ایران کپی شوند.

<details>
<summary><strong>اگر روش دوم، یعنی فایل، را انتخاب کردید</strong></summary>

برای رخش، دستور زیر را **روی ایران** اجرا کنید. IP و در صورت نیاز رمز SSH سرور خارج را وارد کنید:

</div>

```bash
read -r -p "Foreign server IP: " PXC_FOREIGN_IP &&
scp /etc/pxcloud/connections/next-peer.json "root@${PXC_FOREIGN_IP}:/root/Rakhsh-peer.json"
```

<div dir="rtl">

در روش **Import Config File** سمت خارج، مسیر `/root/Rakhsh-peer.json` را وارد کنید. برای تونل‌های دیگر از مسیر نمایش‌داده‌شده در Current Config همان تونل استفاده کنید.

</details>

**ویرایش رخش بعد از نصب:** روی ایران یا خارج، وارد **Rakhsh → 8 — Edit connection settings** شوید. مقدار خالی یعنی حفظ مقدار فعلی. تغییرات را مرور و با `y` اعمال کنید. پورت، نوع انتقال و پروفایل باید در هر دو سمت یکسان باشند؛ سمت دیگر خودکار تغییر نمی‌کند. محدودیت سرعت مربوط به ترافیک خروجی همان سرور است. کلیدهای اتصال حفظ می‌شوند؛ برای این تغییرها نیازی به ورود دوبارهٔ فایل نیست.

برای به‌روزرسانی تنظیمات اتصال موجود، در منوی همان تانل گزینهٔ **I — Connection Setup** همان سه روش را باز می‌کند. این کار فقط اتصال انتخاب‌شده را نصب یا به‌روزرسانی می‌کند؛ فایل تانل یا جفت‌سرور دیگر رد می‌شود.

**Current Config** همیشه تنظیمات ذخیره‌شده و وضعیت سرویس محلی را نشان می‌دهد. کلیدهای خصوصی در نمایش عادی مخفی‌اند. گزینهٔ **F** با تأیید `SHOW` محتوای کامل فایل خصوصی را نمایش می‌دهد. در تنظیمات رخش، نوع انتقال با نام **UDP** یا **TCP** دیده می‌شود.

برای Light Tunnel، wg-custume، GRE و VXLAN هم از منوی همان تانل بروید. هرکدام تنظیمات مستقل دارند؛ افزودن یا حذف یک تانل کلیدهای بقیه را تغییر نمی‌دهد. لایسنس، هویت جفت‌سرور، مسیریابی کاربران و Failover مشترک‌اند.

**فایل معرفی مرحلهٔ ۳ هنوز لازم است:** `PXCloud-invitation.json` برای جفت‌سازی لایسنس است و این سه روش جای آن را نمی‌گیرند. نمایش `active` فقط وضعیت سرویس محلی است؛ ارتباط دو سمت را در بخش تست بررسی کنید.

### ۵. مشخص کنید ترافیک چه سرویسی از تانل عبور کند

**ساخت تانل به‌تنهایی ترافیک کاربران را منتقل نمی‌کند.** بخش مربوط به سرویس خود را باز کنید:

<details>
<summary><strong>WireGuard، OpenVPN، OpenConnect و سرویس‌هایی که به کاربران IP داخلی می‌دهند</strong></summary>

رنج واقعی IP کاربران را از تنظیمات همان سرویس پیدا کنید؛ مثلاً `10.8.0.0/24` فقط یک نمونه است و نباید بدون بررسی کپی شود. این مقدار، IP عمومی سرور نیست. اگر رنج را نمی‌دانید، آن را از نصب‌کنندهٔ سرویس بگیرید.

1. **اول روی خارج:** در منوی `pxcloud` گزینهٔ **C — Client ranges & firewall** را بزنید.
2. مقابل `Client CIDRs` رنج کاربران را وارد کنید. برای چند رنج، آن‌ها را با کامای انگلیسی `,` جدا کنید.
3. مقابل `Enable routing?` بنویسید **yes**.
4. **بعد روی ایران:** همین سه کار را با **دقیقاً همان رنج‌ها** انجام دهید.
5. با یکی از کاربران سرویس، اتصال و دسترسی به اینترنت را امتحان کنید؛ IP خروجی باید مربوط به سرور خارج باشد.

این بخش برای IPv4 است. سرویس کاربران و مسیر دسترسی به IPهای آن‌ها باید از قبل روی ایران درست کار کند.

</details>

<details>
<summary><strong>V2Ray / Xray یا پنل‌هایی مثل 3x-ui، Marzban و PasarGuard</strong></summary>

این سرویس‌ها علاوه بر تانل، به تنظیم خروجی در خود Xray / V2Ray نیاز دارند؛ واردکردن رنج در گزینهٔ C کافی نیست.

1. **روی خارج و سپس ایران:** از منوی اصلی، **V — V2Ray / Xray Traffic** و بعد **1 — Enable tunnel egress on this server** را انتخاب کنید.
2. **روی ایران:** گزینهٔ **2 — Detect panels / containers** محل‌های شناخته‌شدهٔ نصب را نشان می‌دهد؛ گزینهٔ **7 — Status / integration requirements** شرایط لازم را نمایش می‌دهد.
3. گزینهٔ **3 — Generate core configuration** با دریافت مسیر فایل تنظیمات واقعی سرویس، تنظیمات پیشنهادی می‌سازد. برای همهٔ ورودی‌های کاربران، `Scope` را `all` بگذارید و سؤال `Tags or destinations` را خالی رد کنید؛ نوع هسته را مطابق سرویس خود `xray` یا `v2ray` انتخاب کنید.
4. اگر **پنل** دارید، بخش‌های خروجی، DNS و قوانین مسیرِ فایل پیشنهادی باید از داخل تنظیمات پنل اعمال شوند. فایل تولیدشدهٔ پنل یا دیتابیس آن را جایگزین نکنید. اگر نصب **مستقل و بدون پنل** دارید، گزینهٔ **4 — Apply to standalone core** برای همان حالت است.
5. بعد از اعمال، با یک کاربر واقعی اتصال و IP خروجی را بررسی کنید.

**این بخش نصب یک‌کلیکی روی هر پنلی نیست.** اگر مسیر تنظیمات یا نوع نصب را نمی‌شناسید، مرحلهٔ اعمال را به مدیر همان سرویس بسپارید. در این نسخه سرویس باید از شبکهٔ میزبان استفاده کند؛ Docker bridge و rootless پشتیبانی نمی‌شوند. راهنمای کامل‌تر همان بخش، نیاز به دسترسی شبکه و محدودیت IPv6 را توضیح می‌دهد.

</details>

### ۶. نتیجه را ببینید

**روی ایران**، در منوی اصلی گزینهٔ **Q — Quality dashboard** را باز کنید. وضعیت تانل‌ها و مسیر انتخاب‌شده را می‌بینید. سپس اتصال یک کاربر واقعی را هم امتحان کنید؛ سبزبودن مسیر به‌تنهایی به معنی درست‌بودن تنظیم سرویس کاربران نیست.

برای دفعات بعد فقط این دستور را بزنید:

</div>

```bash
pxcloud
```

<div dir="rtl">

| می‌خواهم… | گزینهٔ منو |
| :--- | :--- |
| وضعیت اتصال را ببینم | **Q — Quality dashboard** |
| پینگ و سرعت بگیرم | **T — Tunnel tests** |
| تانل را ری‌استارت کنم | انتخاب نام تانل ← **4 — Restart** |
| لایسنس را بررسی کنم | **L — License / Pairing** ← **5 — Status** |

<details>
<summary><strong>اختیاری: اگر یک مسیر قطع شد، خودکار از مسیر دیگری استفاده شود</strong></summary>

برای این قابلیت باید **حداقل دو تانل** روی هر دو سرور نصب باشند. روی ایران، تانل دوم را از TUNNELS نصب کنید، فایل مخصوص همان تانل را از **Current Config** بردارید و مانند مرحلهٔ 4 در منوی همان تانل روی خارج وارد کنید.

سپس روی ایران گزینهٔ **F — Failover settings** را باز کنید، برای `Mode` مقدار **auto** را وارد کنید و برای نگه‌داشتن تنظیمات پیشنهادی، سؤال‌های بعدی را با Enter رد کنید. کیفیت مسیرها در انتخاب دخیل است؛ عبور پینگ از یک عدد ثابت لزوماً باعث تغییر فوری مسیر نمی‌شود. حفظ همهٔ نشست‌های کاربران هنگام جابه‌جایی تضمین نمی‌شود.

</details>

<details>
<summary><strong>اختیاری: تست سرعت ۲۰ثانیه‌ای و جدول نتیجه‌ها</strong></summary>

ابتدا روی **هر دو سرور** دستور آماده‌سازی را اجرا کنید:

<div dir="ltr">

```bash
pxcloud test-setup
```

</div>

سپس روی **ایران** اجرا کنید:

<div dir="ltr">

```bash
pxcloud test --tunnel all --full --seconds 20 --streams 1
```

</div>

برای هر تانل، ارسال و دریافت جداگانه آزمایش می‌شود؛ ۲۰ ثانیه برای هر جهت است، نه زمان کل همهٔ تست‌ها. نتیجه‌ها در یک جدول می‌آیند. این دستور یک جریان TCP را می‌سنجد؛ برای چهار جریان هم‌زمان، `--streams 1` را به `--streams 4` تغییر دهید. سرعت، بین دو سرور اندازه‌گیری می‌شود و ممکن است حین تست روی کاربران اثر بگذارد. سرعت ثابت یا مشخصی تضمین نمی‌شود.

</details>

بالای منو، **Server IPv4** با رنگ زرد روشن آدرس همین سرور را نشان می‌دهد. اگر چند IP عمومی روی سرور باشد، همه نمایش داده می‌شوند. اگر فقط IP داخلی پیدا شود، با برچسب **local** نمایش داده می‌شود؛ خطای تشخیص IP مانع بازشدن منو نمی‌شود.

### کلیدهای منوی اصلی

| کلید | گزینه |
| :--- | :--- |
| **1** | Rakhsh — سبز |
| **2** | Light Tunnel — آبی روشن |
| **3** | wg-custume — قرمز |
| **4** | GRE — فیروزه‌ای |
| **5** | VXLAN — بنفش |
| **S / C / E / V** | تنظیم سرورها / رنج کاربران / خروجی تنظیمات خارج / ترافیک Xray |
| **Q / F / G / T / W** | داشبورد / تغییر مسیر خودکار / رویدادها / تست / بازیابی پورت |
| **U** | دریافت و نصب آخرین نسخهٔ پایدار |
| **L / X / 0** | لایسنس / حذف / خروج یا بازگشت |

`L` برای License محفوظ است؛ Event Log با `G` باز می‌شود. حذف با `X` همچنان تأیید جداگانه می‌خواهد. رنگ‌ها فقط در ترمینال سازگار نمایش داده می‌شوند. این کلیدها مربوط به نسخهٔ **1.7.3** هستند؛ شماره‌های نسخه‌های قبلی متفاوت‌اند.

نصب‌های قبلی بدون ساخت مجدد اتصال‌ها قابل استفاده‌اند. برای گرفتن فایل مستقل، روی ایران وارد **Current Config** همان تانل شوید. ابتدا هر دو سمت را به نسخهٔ جدید ارتقا دهید. فایل‌های قدیمی چندتانلی فقط برای سازگاری در مسیر قدیمی Import پذیرفته می‌شوند؛ آن‌ها را در Connection Setup وارد نکنید.

### آپدیت از داخل برنامه

**اگر قبلاً 1.7.3 را نصب کرده‌اید:** برای دریافت اصلاح کپی کانفیگ و ویرایش تنظیمات، دستورهای مرحلهٔ ۲ را دوباره روی هر دو سرور اجرا کنید و منوی قدیمی را ببندید و باز کنید. گزینهٔ U بستهٔ هم‌شماره را دوباره نصب نمی‌کند. تنظیمات ذخیره‌شده حفظ می‌شوند.

از نسخهٔ **1.7.2** به بعد، در منوی اصلی **U — Update to latest stable version** را بزنید. برنامه آخرین نسخهٔ پایدار گیت‌هاب را بررسی می‌کند؛ اگر جدیدتر باشد، دانلود و پس از تأیید امضا و صحت فایل‌ها نصب می‌شود. بعد، منوی نسخهٔ جدید خودکار باز می‌شود. اگر آپدیتی نباشد، چیزی تغییر نمی‌کند.

**روی هر دو سرور جداگانه انجام دهید.** تنظیمات و لایسنس حفظ می‌شوند و سرویس‌های در حال اجرا خودکار ری‌استارت نمی‌شوند. اگر نصب یا بررسی نسخه شکست بخورد، برنامه تلاش می‌کند مسیر اجرا و لانچر قبلی را برگرداند. اگر نشست قبلی در تنظیمات منتظر ورودی باشد، بسته می‌شود و نشست جدید جای آن را می‌گیرد. تغییرات ذخیره‌نشدهٔ نشست قبلی اعمال نمی‌شوند. اگر قبلی وسط نصب یا اعمال تغییرات باشد، نشست جدید تا پایان امن عملیات صبر می‌کند؛ سرویس‌های تانل قطع نمی‌شوند.

برای انجام همین کار بدون ورود به منو:

</div>

```bash
pxcloud update
```

<div dir="rtl">

فقط بررسی نسخه، بدون دانلود بسته یا نصب:

</div>

```bash
pxcloud update --check
```

<div dir="rtl">

**اگر نسخهٔ فعلی شما 1.7.1 یا قدیمی‌تر است، یک بار با دستورهای مرحلهٔ ۲ ارتقا دهید تا گزینهٔ U اضافه شود.** از آن به بعد آپدیت از داخل برنامه انجام می‌شود. پس از ارتقا، منوهای قدیمیِ باز را ببندید و دوباره باز کنید. این گزینه با انتخاب شما اجرا می‌شود؛ بررسی یا نصب زمان‌بندی‌شدهٔ پس‌زمینه ندارد. در خطای اینترنت، امضا یا checksum، فایل دریافت‌شده نصب نمی‌شود.

### اگر به مشکل خوردید

| مشکل | کار بعدی |
| :--- | :--- |
| پیام `curl: command not found` | روی همان سرور `apt-get update && apt-get install -y curl ca-certificates` را اجرا و مرحلهٔ نصب را تکرار کنید. |
| دانلود یا بررسی فایل خطا می‌دهد | ارتباط سرور با GitHub را بررسی و مرحلهٔ 2 را دوباره اجرا کنید. فایل‌های **Source code** در Releases برای نصب نیستند. |
| لایسنس فعال نمی‌شود | IP ثبت‌شده در ربات باید IP عمومی **ایران** باشد. دستور `pxcloud license status` وضعیت را نشان می‌دهد. |
| دعوت‌نامه منقضی شده | مرحلهٔ 3 را از ساخت دعوت‌نامهٔ تازه ادامه دهید؛ نیازی به خرید دوباره نیست. |
| تانل قطع است | IPها، واردکردن فایل جدید در خارج و اجازهٔ ارتباط در فایروال سرور و دیتاسنتر را بررسی کنید؛ گزینهٔ **G — Event log** را ببینید. |
| تانل وصل است ولی کاربران اینترنت ندارند | مرحلهٔ 5 را بررسی کنید؛ مسیریابی باید در هر دو سمت فعال و تنظیم سرویس کاربران هم درست باشد. |

<details>
<summary><strong>SSH سرور خارج روی پورتی غیر از ۲۲ است</strong></summary>

دستورهای انتقال بالا پورت ۲۲ را در نظر می‌گیرند. اگر مثلاً پورت شما 2222 است، ابتدای دستور انتقال را به `scp -P 2222` تغییر دهید؛ مسیر فایل‌ها و مقصد همان می‌مانند. اگر ورود با کلید دارید، از کلید مجاز خود استفاده کنید.

</details>

<details>
<summary><strong>از قبل نصب کرده‌ام / پس از حذف، خطای Iran identity already bound می‌بینم</strong></summary>

برای ارتقا، بستهٔ مرحلهٔ 2 را نصب کنید. نصب‌کننده سرویس‌های در حال اجرا را خودکار ری‌استارت نمی‌کند. اگر نصب قدیمی شما از نسخهٔ سورسی استفاده می‌کند، تغییر سرویس‌ها باید در زمان نگهداری انجام شود.

از نسخهٔ **1.6.1**، حذف سرویس‌ها هویت لایسنس را نگه می‌دارد. اگر حذف در نسخهٔ قدیمی باعث خطای بالا شده، بعد از ارتقا اجرا کنید:

<div dir="ltr">

```bash
pxcloud license recover
```

</div>

بازیابی به بکاپ معتبر روی همان سرور و دسترسی آنلاین نیاز دارد و تانل‌های حذف‌شده را برنمی‌گرداند. اگر بکاپ پیدا نشد، فایل‌های هویت را پاک نکنید و از پشتیبانی کمک بگیرید.

</details>

<details>
<summary><strong>IP معاف، انقضای لایسنس و چند سؤال رایج</strong></summary>

- **IP معاف دارم:** روی ایران، `pxcloud license` و گزینهٔ **2 — Activate exempt Iran IP** را انتخاب کنید. برای تشخیص خودکار IP، Enter بزنید. فقط IPهایی پذیرفته می‌شوند که مدیر قبلاً معاف کرده باشد؛ بعد مرحلهٔ جفت‌سازی را انجام دهید.
- **قبلاً لایسنس تست گرفته‌ام ولی IP معاف است:** تا زمان باقی‌ماندن معافیت، پایان تست باعث قطع نمی‌شود. فعال‌کردن معافیت، لایسنس و جفت فعلی را عوض نمی‌کند. حذف معافیت در بررسی بعدی قوانین اشتراک را برمی‌گرداند؛ لغو یا تعلیق لایسنس همچنان معتبر است.
- **بررسی لایسنس:** آنلاین و در چرخهٔ شش‌ساعته است. اشتراک پس از انقضا شش ساعت مهلت دارد؛ معتبرماندن تأییدیهٔ آنلاین هم لازم است.
- **Back و Exit:** Back به منوی قبلی برمی‌گردد؛ Exit از برنامه خارج می‌شود. خروج از منو، تانل را خاموش نمی‌کند.
- **این مخزن سورس محصول است؟** خیر؛ برای راهنما و دانلود است. کد اختصاصی به‌صورت کامپایل‌شده عرضه می‌شود و فایل‌های الزامی اجزای ثالث همراه آن باقی می‌مانند.

</details>

هنگام گزارش خطا، شمارهٔ مرحله و متن خطا را بفرستید؛ رمز سرور، کلید لایسنس و فایل‌های خصوصی را در پیام عمومی نگذارید. جزئیات تغییرات و تست‌های نسخه در **[صفحهٔ انتشار 1.7.3](https://github.com/IRSupp/PXCloud-Tunnel/releases/tag/v1.7.3)** است.

</div>

---

## English

PXCloud connects your Iran-side server to a foreign server. You choose which users or services send traffic through that connection. The menu also provides restart controls, quality monitoring, speed tests and automatic path selection when you install multiple tunnels.

**New installation? Follow these steps in order.** Upgrade and recovery instructions are below.

### Before you start

- Two servers: one in Iran (**A**), one abroad (**B**, any country).
- **Ubuntu 24.04, amd64 / x86_64** on both, with root SSH access.
- The public IP and login credentials for each server.
- An existing user service, such as WireGuard or Xray, on A. PXCloud does not create user accounts or end-user connection profiles.

Open two SSH windows and label them **Iran** and **Foreign**. Run commands in the indicated server window, not in your local Windows terminal. To select a menu option, type its number or letter and press Enter; letters are case-insensitive. Tunnels use 1–5, licensing uses L, uninstall uses X, and Exit or Back is always 0.

### 1. Buy a license

Open **[@irsupplm_bot](https://t.me/irsupplm_bot)**, choose **PXCloud Tunnel** and your plan, and register the **Iran server's public IP**. Keep the license key supplied by the bot. Prices and durations are shown there. One license covers one server pair.

If your Iran IP has already been exempted by the administrator, see **Exempt IPs and licensing** below instead of purchasing.

### 2. Install on both servers

**Run this once on Iran and once on Foreign, logged in as root.** Copy the whole block. It downloads, checks and installs version 1.7.3:

```bash
mkdir -p /root/pxcloud-install-1.7.3 &&
cd /root/pxcloud-install-1.7.3 &&
curl -fLO https://github.com/IRSupp/PXCloud-Tunnel/releases/download/v1.7.3/PXCloud-Tunnel-1.7.3-linux-x86_64.tar.gz &&
curl -fLO https://github.com/IRSupp/PXCloud-Tunnel/releases/download/v1.7.3/PXCloud-Tunnel-Install.sh &&
curl -fLO https://github.com/IRSupp/PXCloud-Tunnel/releases/download/v1.7.3/SHA256SUMS &&
sha256sum -c SHA256SUMS &&
bash PXCloud-Tunnel-Install.sh
```

Check the installed version; it should show **1.7.3**:

```bash
pxcloud --version
```

If downloading or installation fails, stop and use **Troubleshooting** below. Engines are bundled, but some system dependencies still need Internet access.

### 3. Activate the license and pair the servers

**On Iran**, run:

```bash
pxcloud license
```

1. Select **1 — Activate Iran license** and enter your purchased key.
2. After success, select **3 — Pair foreign server (from Iran)** in the same menu.
3. Enter the foreign server's public IP at `Foreign public IPv4`.
4. Enter `/root/PXCloud-invitation.json` at `Invitation output path`.
5. Select **0** to leave this menu before running the next command.

**On Iran**, copy the invitation to Foreign. This block asks for the foreign IP, then SSH may ask for that server's password:

```bash
read -r -p "Foreign server IP: " PXC_FOREIGN_IP &&
scp /root/PXCloud-invitation.json "root@${PXC_FOREIGN_IP}:/root/PXCloud-invitation.json"
```

SSH passwords are not displayed while typing. For a first-time host-key prompt, check the fingerprint against your server's records.

**On Foreign**, run `pxcloud license`, select **4 — Join pair (on foreign server)** and enter `/root/PXCloud-invitation.json`. After success, select **0**.

Use the invitation within **15 minutes**. If it expires, create and transfer a fresh one using option 3 on Iran. Keep this file private.

### 4. Create your first tunnel

**On Iran**, run `pxcloud`:

1. Select **1 — Rakhsh**, then **1 — Install**.
2. For the first connection in this pair, choose **A** and enter the foreign server IP. The local IP is detected automatically, or requested if detection is inconclusive.
3. Press Enter at `Use advanced settings?` for the recommended defaults. Other tunnels' settings are not requested.
4. After successful installation, the yellow **SERVER B CONNECTION CONFIG** heading appears automatically, followed by the complete connection block. Copy every line from `PXCT1:` through `END`. The menu waits until you press Enter. The saved private file path appears above this section.

**On Foreign**, run `pxcloud`, select **1 — Rakhsh**, then **1 — Install**. Choose **B** if asked for the role. Choose just one of these three methods:

| Foreign setup option | What to do |
| :--- | :--- |
| **1 — Paste Connection Config** | Copy the block shown automatically after installation on Iran, from `PXCT1:` through `END`, and paste it into the Foreign prompt. To display it again later, use **C — Current Config → P**, then type `SHOW` on Iran. |
| **2 — Import Config File** | Transfer the private peer file from Iran, then enter its local path on Foreign. See the example below. |
| **3 — Manual Setup (step by step)** | On Iran, choose **M** in Current Config, then `SHOW`. Enter each displayed value at the matching Foreign prompt, in the same order. Type `BACK` to cancel manual entry. |

Paste is usually the simplest option. The corrected 1.7.3 package also accepts the yellow SERVER B CONNECTION CONFIG heading if it is included in the selection. The block and manual values contain private keys; keep them out of public messages. The copyable code is a transfer format, not encryption. Copy certificates and keys exactly from Iran.

<details>
<summary><strong>If you selected Import Config File</strong></summary>

For Rakhsh, run this **on Iran**. Enter the Foreign IP and SSH password if requested:

```bash
read -r -p "Foreign server IP: " PXC_FOREIGN_IP &&
scp /etc/pxcloud/connections/next-peer.json "root@${PXC_FOREIGN_IP}:/root/Rakhsh-peer.json"
```

Enter `/root/Rakhsh-peer.json` in **Import Config File** on Foreign. For another tunnel, use the path in its own Current Config.

</details>

**Edit Rakhsh after installation:** on either endpoint, open **Rakhsh → 8 — Edit connection settings**. Press Enter to keep a value, review your changes, then confirm with `y`. Match profile, transport and port on both servers; the peer is not changed automatically. The rate limit controls this server’s outbound traffic. Keys are preserved, and no config-file import is required for these edits.

To update an existing connection, open **I — Connection Setup** in that tunnel's menu. It offers the same three methods. Only the selected tunnel is installed or updated; wrong-tunnel and wrong-pair settings are rejected.

**Current Config** shows saved settings and local service state at any time. Secrets remain hidden by default. **F**, followed by `SHOW`, displays the full private file. Rakhsh's transport setting is displayed as **UDP** or **TCP**.

The same workflow applies to Light Tunnel, wg-custume, GRE and VXLAN. Each has independent connection settings. Adding or removing one preserves the other connections' keys. Licensing, server-pair identity, user routing and failover remain shared.

**Step 3 still applies:** `PXCloud-invitation.json` pairs the license; these three methods do not replace it. A local `active` service does not prove end-to-end connectivity; use Tunnel tests.

### 5. Choose which user traffic uses the tunnel

**Installing a tunnel alone does not route your users.** Open the section for your service:

<details>
<summary><strong>WireGuard, OpenVPN, OpenConnect or other services with private client IPs</strong></summary>

Find the actual client subnet in your service's settings. `10.8.0.0/24` is only an example; do not copy it unless it matches your configuration. This is not the server's public IP. Ask your service administrator if you do not know it.

1. **On Foreign first:** open `pxcloud`, then **C — Client ranges & firewall**.
2. Enter the client subnet at `Client CIDRs`. Separate multiple subnets with commas.
3. Enter **yes** at `Enable routing?`.
4. **On Iran next:** repeat with exactly the same subnets.
5. Connect a real user and check Internet access and the exit IP; it should belong to the foreign server.

This feature routes IPv4. The user service and routes to its clients must already work on Iran.

</details>

<details>
<summary><strong>V2Ray / Xray, including 3x-ui, Marzban and PasarGuard panels</strong></summary>

These services also need an outbound configuration in Xray / V2Ray. Adding a client subnet in menu C is not sufficient.

1. **On Foreign, then Iran:** select **V — V2Ray / Xray Traffic**, then **1 — Enable tunnel egress on this server**.
2. **On Iran:** option **2 — Detect panels / containers** lists known installation locations. Option **7 — Status / integration requirements** shows the requirements.
3. Option **3 — Generate core configuration** asks for the effective core configuration file and generates proposed settings. For all current user inbounds, set `Scope` to `all` and leave `Tags or destinations` blank. Choose `xray` or `v2ray` to match your installed core.
4. For a **panel**, merge the proposed outbound, DNS and routing rules through that panel's settings. Do not overwrite its database or generated runtime file. Option **4 — Apply to standalone core** is only for a standalone installation without a panel.
5. After applying, check a real user's connectivity and exit IP.

**This is not a one-click integration for every panel.** If you do not know the effective configuration path or installation type, have the service administrator handle the apply step. Host networking is required; Docker bridge and rootless setups are unsupported. The in-menu requirements explain networking permissions and IPv6 limitations.

</details>

### 6. Check the result

**On Iran**, select **Q — Quality dashboard** to see tunnel health and the selected path. Also test a real user: a healthy path alone does not confirm that the user service is configured correctly.

To return to the menu later, run:

```bash
pxcloud
```

| I want to… | Menu option |
| :--- | :--- |
| See connection health | **Q — Quality dashboard** |
| Test ping and speed | **T — Tunnel tests** |
| Restart a tunnel | Choose its name → **4 — Restart** |
| Check the license | **L — License / Pairing** → **5 — Status** |

<details>
<summary><strong>Optional: switch automatically when a path fails</strong></summary>

Install **at least two tunnels** on both servers. On Iran, install a second tunnel from TUNNELS, use its own **Current Config** peer file, and import it from the matching tunnel menu on Foreign as in step 4.

Then on Iran, select **F — Failover settings**, enter **auto** for `Mode`, and press Enter at the remaining questions to keep the suggested settings. Selection considers path quality; crossing one fixed ping value does not always cause an immediate switch. Every existing session is not guaranteed to survive a path change.

</details>

<details>
<summary><strong>Optional: 20-second speed tests with a results table</strong></summary>

Prepare testing on **both servers**:

```bash
pxcloud test-setup
```

Then run this **on Iran**:

```bash
pxcloud test --tunnel all --full --seconds 20 --streams 1
```

Each tunnel is tested in both directions, **20 seconds per direction**, not 20 seconds for the entire suite. Results appear in one table. This tests one TCP flow; use `--streams 4` for four simultaneous flows. Speeds are measured between your servers, may affect live traffic during testing, and are not guaranteed.

</details>

The bold yellow **Server IPv4** line above the menu identifies the current server. Multiple public addresses are listed together. Private-only addresses are labelled **local**; unavailable address information does not prevent the menu from opening.

### Main menu keys

| Key | Option |
| :--- | :--- |
| **1** | Rakhsh — green |
| **2** | Light Tunnel — light blue |
| **3** | wg-custume — red |
| **4** | GRE — cyan |
| **5** | VXLAN — purple |
| **S / C / E / V** | Server setup / Client ranges / Export peer config / V2Ray traffic |
| **Q / F / G / T / W** | Quality dashboard / Failover / Event log / Tests / Port recovery |
| **U** | Download and install the latest stable version |
| **L / X / 0** | Licensing / Uninstall / Exit or Back |

`L` is reserved for License; Event Log uses `G`. Uninstall with `X` still requires confirmation. Colors appear only in supported terminals. These keys apply to **1.7.3**; earlier versions use different numbers.

Existing connections remain usable without rebuilding them. Upgrade both endpoints before using the new peer files. On Iran, open the connection's **Current Config** to generate its own file. Legacy multi-tunnel bundles remain supported only by the legacy import path; do not use them with Connection Setup.

### Update from the menu

**Already on 1.7.3?** Rerun step 2 on each endpoint to obtain the paste and settings fixes, then reopen old menus. U does not reinstall a package with the same version number. Saved settings are retained.

Starting with **1.7.2**, select **U — Update to latest stable version** in the main menu. A newer stable GitHub release is downloaded, its signature and checksums are verified, and the package is installed. The updated menu opens automatically. If there is no newer version, nothing changes.

**Run the update on each endpoint separately.** Settings and licensing are preserved; running services are not restarted automatically. If installation or the version check fails, the updater attempts to restore the previous program link and launcher. A newer configuration session replaces an older session waiting for input; unsaved answers are discarded. If the old session is applying changes, the new one waits for that operation to finish safely. Tunnel services are not terminated.

The equivalent command is:

```bash
pxcloud update
```

To check only, without downloading or installing the package:

```bash
pxcloud update --check
```

**For 1.7.1 or earlier, upgrade once using step 2 to obtain the U option.** Later updates can use the menu. Close and reopen old menu processes after upgrading. Updates run only when requested; there is no background auto-install schedule. Network, signature or checksum failures prevent installation.

### Troubleshooting

| Problem | Next step |
| :--- | :--- |
| `curl: command not found` | Run `apt-get update && apt-get install -y curl ca-certificates` on that server, then repeat installation. |
| Download or checksum failure | Check access to GitHub and repeat step 2. GitHub's **Source code** archives are not installers. |
| License activation fails | The bot must have the **Iran server's public IP**. Run `pxcloud license status` to see its state. |
| Invitation expired | Create and transfer a new invitation in step 3. You do not need to buy another license. |
| Tunnel is down | Check endpoint IPs, the imported bundle and server/datacenter firewalls; review **G — Event log**. |
| Tunnel is healthy but users have no Internet | Check step 5: both endpoints need routing enabled, and the user service needs the correct configuration. |

<details>
<summary><strong>The foreign server uses a non-default SSH port</strong></summary>

The transfer commands above use port 22. For port 2222, for example, change the start of each transfer command to `scp -P 2222`; keep the paths and destination unchanged. Use your authorized SSH key if password login is not enabled.

</details>

<details>
<summary><strong>Upgrading / Iran identity already bound after an earlier uninstall</strong></summary>

Install the package from step 2 to upgrade. The installer does not automatically restart running services. Older source-based service definitions require a planned maintenance migration.

From **1.6.1**, uninstall retains the licensing identity. If an older uninstall caused `Iran identity already bound`, upgrade and run:

```bash
pxcloud license recover
```

Recovery requires a valid local backup and fresh online approval. It does not restore removed tunnels. If no usable backup is found, keep existing identity files and contact support.

</details>

<details>
<summary><strong>Exempt IPs and licensing</strong></summary>

- **Exempt IP:** on Iran, run `pxcloud license` and choose **2 — Activate exempt Iran IP**. Press Enter for automatic IP detection. Only administrator-approved addresses qualify. Then continue with pairing.
- **An existing trial on an exempt IP:** expiry does not interrupt service while the IP remains exempt. Manual exemption activation keeps the existing license and pair. Removing the exemption restores the subscription policy on the next check; revocation and suspension still apply.
- **Online checks:** follow a six-hour cycle. Subscriptions have a six-hour expiry grace period; a valid online entitlement is also required.
- **Back / Exit:** Back returns to the parent menu; Exit closes the program. Leaving the menu does not stop running tunnels.
- **Source code:** this repository provides documentation and downloads. Proprietary code is distributed compiled; required third-party materials remain included.

</details>

When reporting an error, include the step number and error text. Keep server passwords, license keys and private files out of public messages. See the **[1.7.3 release notes](https://github.com/IRSupp/PXCloud-Tunnel/releases/tag/v1.7.3)** for changes, validation details and signed-checksum instructions.

---

<div align="center">

**[خرید لایسنس / Buy a license](https://t.me/irsupplm_bot) · [کانال رسمی / Official channel](https://t.me/irsuppchannel) · [دانلود / Downloads](https://github.com/IRSupp/PXCloud-Tunnel/releases/tag/v1.7.3)**

</div>
