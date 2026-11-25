<div align="center">

# PXCloud Tunnel

**دو سرور را وصل کنید؛ اتصال‌ها را از یک منو مدیریت کنید.**

Connect your servers. Manage your tunnels from one menu.

<p>
<a href="https://t.me/irsupplm_bot"><img alt="Buy a license" src="https://img.shields.io/badge/BUY_A_LICENSE-irsupplm__bot-F4B942?style=for-the-badge&logo=telegram&logoColor=white"></a>
<a href="https://github.com/IRSupp/PXCloud-Tunnel/releases/tag/v1.6.1"><img alt="Download 1.6.1" src="https://img.shields.io/badge/DOWNLOAD-v1.6.1-2563EB?style=for-the-badge&logo=github&logoColor=white"></a>
</p>

**[خرید لایسنس / Buy a license](https://t.me/irsupplm_bot) · [کانال تلگرام / Telegram channel](https://t.me/irsuppchannel)**

[راهنمای فارسی](#فارسی) · [English guide](#english)

نسخهٔ پایدار **1.6.1** · Ubuntu **24.04** · **x86_64 / amd64**

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

در این راهنما **A یعنی ایران** و **B یعنی خارج**؛ سرور خارج می‌تواند در هر کشوری باشد. دو پنجرهٔ SSH باز کنید و نام آن‌ها را «ایران» و «خارج» بگذارید. دستورها را داخل پنجرهٔ سرور بنویسید، نه در ترمینال ویندوز. در منوها شمارهٔ گزینه را بنویسید و Enter بزنید.

### ۱. لایسنس بخرید

وارد **[ربات خرید @irsupplm_bot](https://t.me/irsupplm_bot)** شوید، محصول **PXCloud Tunnel** و پلن موردنظر را انتخاب کنید. **IP عمومی سرور ایران** را برای لایسنس ثبت کنید و کلیدی را که ربات می‌دهد نگه دارید. قیمت و مدت هر پلن داخل ربات نمایش داده می‌شود.

یک لایسنس برای یک جفت سرور ایران و خارج است. اگر مدیر قبلاً IP ایران شما را معاف کرده، به‌جای خرید، روش «IP معاف» را در بخش پرسش‌های رایج پایین صفحه بخوانید.

### ۲. برنامه را روی هر دو سرور نصب کنید

**محل اجرا: یک بار روی ایران، یک بار روی خارج.**

با کاربر `root` وارد شوید. تمام دستورهای این کادر را کپی و اجرا کنید؛ فایل‌های نسخهٔ 1.6.1 دریافت و بررسی می‌شوند و سپس نصب شروع می‌شود:

</div>

```bash
mkdir -p /root/pxcloud-install-1.6.1 &&
cd /root/pxcloud-install-1.6.1 &&
curl -fLO https://github.com/IRSupp/PXCloud-Tunnel/releases/download/v1.6.1/PXCloud-Tunnel-1.6.1-linux-x86_64.tar.gz &&
curl -fLO https://github.com/IRSupp/PXCloud-Tunnel/releases/download/v1.6.1/PXCloud-Tunnel-Install.sh &&
curl -fLO https://github.com/IRSupp/PXCloud-Tunnel/releases/download/v1.6.1/SHA256SUMS &&
sha256sum -c SHA256SUMS &&
bash PXCloud-Tunnel-Install.sh
```

<div dir="rtl">

در پایان، با دستور زیر نسخه را ببینید. باید **1.6.1** نمایش داده شود:

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

**روی ایران** منوی اصلی را باز کنید:

</div>

```bash
pxcloud
```

<div dir="rtl">

1. گزینهٔ **5 — Server setup / Import B bundle** را بزنید.
2. در سؤال نقش سرور، **A** بنویسید.
3. IP سرور خارج را وارد کنید. IP ایران خودکار تشخیص داده می‌شود.
4. برای سؤال‌های پورت، اگر تنظیم خاصی ندارید Enter بزنید تا مقدار پیشنهادی حفظ شود. اگر برنامه خطا داد، همان خطا را برطرف کنید و ادامه ندهید.
5. به منوی اصلی که برگشتید، **16 — Rakhsh** و سپس **1 — Install** را بزنید. این مثال راه‌اندازی یک تانل است؛ گزینه‌های دیگر هم از بخش TUNNELS نصب می‌شوند.
6. بعد از پایان نصب، **0 — Back** را بزنید و از منوی اصلی **9 — Export B bundle** را انتخاب کنید. فایل `/root/PXCloud-B.json` ساخته می‌شود.
7. با **0 — Exit** از منوی اصلی خارج شوید.

این بار فایل تنظیمات تانل را بفرستید. **روی ایران** اجرا کنید:

</div>

```bash
read -r -p "Foreign server IP: " PXC_FOREIGN_IP &&
scp /root/PXCloud-B.json "root@${PXC_FOREIGN_IP}:/root/PXCloud-B.json"
```

<div dir="rtl">

**روی خارج** دستور `pxcloud` را اجرا کنید. گزینهٔ **5** را بزنید، نقش **B** را انتخاب کنید و مسیر `/root/PXCloud-B.json` را بدهید. اتصال‌های داخل فایل نصب می‌شوند.

**دو فایل را اشتباه نگیرید:** `PXCloud-invitation.json` برای لایسنس است؛ `PXCloud-B.json` برای تنظیم تانل. هر دو خصوصی‌اند.

### ۵. مشخص کنید ترافیک چه سرویسی از تانل عبور کند

**ساخت تانل به‌تنهایی ترافیک کاربران را منتقل نمی‌کند.** بخش مربوط به سرویس خود را باز کنید:

<details>
<summary><strong>WireGuard، OpenVPN، OpenConnect و سرویس‌هایی که به کاربران IP داخلی می‌دهند</strong></summary>

رنج واقعی IP کاربران را از تنظیمات همان سرویس پیدا کنید؛ مثلاً `10.8.0.0/24` فقط یک نمونه است و نباید بدون بررسی کپی شود. این مقدار، IP عمومی سرور نیست. اگر رنج را نمی‌دانید، آن را از نصب‌کنندهٔ سرویس بگیرید.

1. **اول روی خارج:** در منوی `pxcloud` گزینهٔ **6 — Client ranges & firewall** را بزنید.
2. مقابل `Client CIDRs` رنج کاربران را وارد کنید. برای چند رنج، آن‌ها را با کامای انگلیسی `,` جدا کنید.
3. مقابل `Enable routing?` بنویسید **yes**.
4. **بعد روی ایران:** همین سه کار را با **دقیقاً همان رنج‌ها** انجام دهید.
5. با یکی از کاربران سرویس، اتصال و دسترسی به اینترنت را امتحان کنید؛ IP خروجی باید مربوط به سرور خارج باشد.

این بخش برای IPv4 است. سرویس کاربران و مسیر دسترسی به IPهای آن‌ها باید از قبل روی ایران درست کار کند.

</details>

<details>
<summary><strong>V2Ray / Xray یا پنل‌هایی مثل 3x-ui، Marzban و PasarGuard</strong></summary>

این سرویس‌ها علاوه بر تانل، به تنظیم خروجی در خود Xray / V2Ray نیاز دارند؛ واردکردن رنج در گزینهٔ 6 کافی نیست.

1. **روی خارج و سپس ایران:** از منوی اصلی، **15 — V2Ray / Xray Traffic** و بعد **1 — Enable tunnel egress on this server** را انتخاب کنید.
2. **روی ایران:** گزینهٔ **2 — Detect panels / containers** محل‌های شناخته‌شدهٔ نصب را نشان می‌دهد؛ گزینهٔ **7 — Status / integration requirements** شرایط لازم را نمایش می‌دهد.
3. گزینهٔ **3 — Generate core configuration** با دریافت مسیر فایل تنظیمات واقعی سرویس، تنظیمات پیشنهادی می‌سازد. برای همهٔ ورودی‌های کاربران، `Scope` را `all` بگذارید و سؤال `Tags or destinations` را خالی رد کنید؛ نوع هسته را مطابق سرویس خود `xray` یا `v2ray` انتخاب کنید.
4. اگر **پنل** دارید، بخش‌های خروجی، DNS و قوانین مسیرِ فایل پیشنهادی باید از داخل تنظیمات پنل اعمال شوند. فایل تولیدشدهٔ پنل یا دیتابیس آن را جایگزین نکنید. اگر نصب **مستقل و بدون پنل** دارید، گزینهٔ **4 — Apply to standalone core** برای همان حالت است.
5. بعد از اعمال، با یک کاربر واقعی اتصال و IP خروجی را بررسی کنید.

**این بخش نصب یک‌کلیکی روی هر پنلی نیست.** اگر مسیر تنظیمات یا نوع نصب را نمی‌شناسید، مرحلهٔ اعمال را به مدیر همان سرویس بسپارید. در این نسخه سرویس باید از شبکهٔ میزبان استفاده کند؛ Docker bridge و rootless پشتیبانی نمی‌شوند. راهنمای کامل‌تر همان بخش، نیاز به دسترسی شبکه و محدودیت IPv6 را توضیح می‌دهد.

</details>

### ۶. نتیجه را ببینید

**روی ایران**، در منوی اصلی گزینهٔ **7 — Quality dashboard** را باز کنید. وضعیت تانل‌ها و مسیر انتخاب‌شده را می‌بینید. سپس اتصال یک کاربر واقعی را هم امتحان کنید؛ سبزبودن مسیر به‌تنهایی به معنی درست‌بودن تنظیم سرویس کاربران نیست.

برای دفعات بعد فقط این دستور را بزنید:

</div>

```bash
pxcloud
```

<div dir="rtl">

| می‌خواهم… | گزینهٔ منو |
| :--- | :--- |
| وضعیت اتصال را ببینم | **7 — Quality dashboard** |
| پینگ و سرعت بگیرم | **11 — Tunnel tests** |
| تانل را ری‌استارت کنم | انتخاب نام تانل ← **4 — Restart** |
| لایسنس را بررسی کنم | **14 — License / Pairing** ← **5 — Status** |

<details>
<summary><strong>اختیاری: اگر یک مسیر قطع شد، خودکار از مسیر دیگری استفاده شود</strong></summary>

برای این قابلیت باید **حداقل دو تانل** روی هر دو سرور نصب باشند. روی ایران، تانل دوم را از TUNNELS نصب کنید، با گزینهٔ **9** فایل جدید بگیرید و مانند مرحلهٔ 4 روی خارج وارد کنید.

سپس روی ایران گزینهٔ **8 — Failover settings** را باز کنید، برای `Mode` مقدار **auto** را وارد کنید و برای نگه‌داشتن تنظیمات پیشنهادی، سؤال‌های بعدی را با Enter رد کنید. کیفیت مسیرها در انتخاب دخیل است؛ عبور پینگ از یک عدد ثابت لزوماً باعث تغییر فوری مسیر نمی‌شود. حفظ همهٔ نشست‌های کاربران هنگام جابه‌جایی تضمین نمی‌شود.

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

### اگر به مشکل خوردید

| مشکل | کار بعدی |
| :--- | :--- |
| پیام `curl: command not found` | روی همان سرور `apt-get update && apt-get install -y curl ca-certificates` را اجرا و مرحلهٔ نصب را تکرار کنید. |
| دانلود یا بررسی فایل خطا می‌دهد | ارتباط سرور با GitHub را بررسی و مرحلهٔ 2 را دوباره اجرا کنید. فایل‌های **Source code** در Releases برای نصب نیستند. |
| لایسنس فعال نمی‌شود | IP ثبت‌شده در ربات باید IP عمومی **ایران** باشد. دستور `pxcloud license status` وضعیت را نشان می‌دهد. |
| دعوت‌نامه منقضی شده | مرحلهٔ 3 را از ساخت دعوت‌نامهٔ تازه ادامه دهید؛ نیازی به خرید دوباره نیست. |
| تانل قطع است | IPها، واردکردن فایل جدید در خارج و اجازهٔ ارتباط در فایروال سرور و دیتاسنتر را بررسی کنید؛ گزینهٔ **10 — Event log** را ببینید. |
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

هنگام گزارش خطا، شمارهٔ مرحله و متن خطا را بفرستید؛ رمز سرور، کلید لایسنس و فایل‌های خصوصی را در پیام عمومی نگذارید. جزئیات تغییرات و تست‌های نسخه در **[صفحهٔ انتشار 1.6.1](https://github.com/IRSupp/PXCloud-Tunnel/releases/tag/v1.6.1)** است.

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

Open two SSH windows and label them **Iran** and **Foreign**. Run commands in the indicated server window, not in your local Windows terminal. To select a menu option, type its number and press Enter.

### 1. Buy a license

Open **[@irsupplm_bot](https://t.me/irsupplm_bot)**, choose **PXCloud Tunnel** and your plan, and register the **Iran server's public IP**. Keep the license key supplied by the bot. Prices and durations are shown there. One license covers one server pair.

If your Iran IP has already been exempted by the administrator, see **Exempt IPs and licensing** below instead of purchasing.

### 2. Install on both servers

**Run this once on Iran and once on Foreign, logged in as root.** Copy the whole block. It downloads, checks and installs version 1.6.1:

```bash
mkdir -p /root/pxcloud-install-1.6.1 &&
cd /root/pxcloud-install-1.6.1 &&
curl -fLO https://github.com/IRSupp/PXCloud-Tunnel/releases/download/v1.6.1/PXCloud-Tunnel-1.6.1-linux-x86_64.tar.gz &&
curl -fLO https://github.com/IRSupp/PXCloud-Tunnel/releases/download/v1.6.1/PXCloud-Tunnel-Install.sh &&
curl -fLO https://github.com/IRSupp/PXCloud-Tunnel/releases/download/v1.6.1/SHA256SUMS &&
sha256sum -c SHA256SUMS &&
bash PXCloud-Tunnel-Install.sh
```

Check the installed version; it should show **1.6.1**:

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

**On Iran**, open the main menu:

```bash
pxcloud
```

1. Select **5 — Server setup / Import B bundle**.
2. Enter **A** for the server role, then the foreign server's IP. Iran's IP is detected automatically.
3. Press Enter at the port questions to keep the suggested values unless you have specific requirements. Resolve any error before continuing.
4. Back in the main menu, select **16 — Rakhsh**, then **1 — Install**. This walkthrough starts with one tunnel; other choices are under TUNNELS.
5. After installation, select **0 — Back**, then **9 — Export B bundle** from the main menu. This creates `/root/PXCloud-B.json`.
6. Select **0 — Exit** to return to the terminal.

**On Iran**, transfer the tunnel settings:

```bash
read -r -p "Foreign server IP: " PXC_FOREIGN_IP &&
scp /root/PXCloud-B.json "root@${PXC_FOREIGN_IP}:/root/PXCloud-B.json"
```

**On Foreign**, run `pxcloud`, select **5**, choose role **B** and enter `/root/PXCloud-B.json`. The connections in the bundle are installed.

**These are two different files:** `PXCloud-invitation.json` pairs the license; `PXCloud-B.json` contains tunnel settings. Keep both private.

### 5. Choose which user traffic uses the tunnel

**Installing a tunnel alone does not route your users.** Open the section for your service:

<details>
<summary><strong>WireGuard, OpenVPN, OpenConnect or other services with private client IPs</strong></summary>

Find the actual client subnet in your service's settings. `10.8.0.0/24` is only an example; do not copy it unless it matches your configuration. This is not the server's public IP. Ask your service administrator if you do not know it.

1. **On Foreign first:** open `pxcloud`, then **6 — Client ranges & firewall**.
2. Enter the client subnet at `Client CIDRs`. Separate multiple subnets with commas.
3. Enter **yes** at `Enable routing?`.
4. **On Iran next:** repeat with exactly the same subnets.
5. Connect a real user and check Internet access and the exit IP; it should belong to the foreign server.

This feature routes IPv4. The user service and routes to its clients must already work on Iran.

</details>

<details>
<summary><strong>V2Ray / Xray, including 3x-ui, Marzban and PasarGuard panels</strong></summary>

These services also need an outbound configuration in Xray / V2Ray. Adding a client subnet in menu 6 is not sufficient.

1. **On Foreign, then Iran:** select **15 — V2Ray / Xray Traffic**, then **1 — Enable tunnel egress on this server**.
2. **On Iran:** option **2 — Detect panels / containers** lists known installation locations. Option **7 — Status / integration requirements** shows the requirements.
3. Option **3 — Generate core configuration** asks for the effective core configuration file and generates proposed settings. For all current user inbounds, set `Scope` to `all` and leave `Tags or destinations` blank. Choose `xray` or `v2ray` to match your installed core.
4. For a **panel**, merge the proposed outbound, DNS and routing rules through that panel's settings. Do not overwrite its database or generated runtime file. Option **4 — Apply to standalone core** is only for a standalone installation without a panel.
5. After applying, check a real user's connectivity and exit IP.

**This is not a one-click integration for every panel.** If you do not know the effective configuration path or installation type, have the service administrator handle the apply step. Host networking is required; Docker bridge and rootless setups are unsupported. The in-menu requirements explain networking permissions and IPv6 limitations.

</details>

### 6. Check the result

**On Iran**, select **7 — Quality dashboard** to see tunnel health and the selected path. Also test a real user: a healthy path alone does not confirm that the user service is configured correctly.

To return to the menu later, run:

```bash
pxcloud
```

| I want to… | Menu option |
| :--- | :--- |
| See connection health | **7 — Quality dashboard** |
| Test ping and speed | **11 — Tunnel tests** |
| Restart a tunnel | Choose its name → **4 — Restart** |
| Check the license | **14 — License / Pairing** → **5 — Status** |

<details>
<summary><strong>Optional: switch automatically when a path fails</strong></summary>

Install **at least two tunnels** on both servers. On Iran, install a second tunnel from TUNNELS, export a new bundle with option **9**, and transfer/import it on Foreign as in step 4.

Then on Iran, select **8 — Failover settings**, enter **auto** for `Mode`, and press Enter at the remaining questions to keep the suggested settings. Selection considers path quality; crossing one fixed ping value does not always cause an immediate switch. Every existing session is not guaranteed to survive a path change.

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

### Troubleshooting

| Problem | Next step |
| :--- | :--- |
| `curl: command not found` | Run `apt-get update && apt-get install -y curl ca-certificates` on that server, then repeat installation. |
| Download or checksum failure | Check access to GitHub and repeat step 2. GitHub's **Source code** archives are not installers. |
| License activation fails | The bot must have the **Iran server's public IP**. Run `pxcloud license status` to see its state. |
| Invitation expired | Create and transfer a new invitation in step 3. You do not need to buy another license. |
| Tunnel is down | Check endpoint IPs, the imported bundle and server/datacenter firewalls; review **10 — Event log**. |
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

When reporting an error, include the step number and error text. Keep server passwords, license keys and private files out of public messages. See the **[1.6.1 release notes](https://github.com/IRSupp/PXCloud-Tunnel/releases/tag/v1.6.1)** for changes, validation details and signed-checksum instructions.

---

<div align="center">

**[خرید لایسنس / Buy a license](https://t.me/irsupplm_bot) · [کانال رسمی / Official channel](https://t.me/irsuppchannel) · [دانلود / Downloads](https://github.com/IRSupp/PXCloud-Tunnel/releases/tag/v1.6.1)**

</div>
