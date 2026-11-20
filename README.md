# PXCloud Tunnel

### 🇮🇷 فارسی | 🇬🇧 English

## 🛒 [خرید و مدیریت لایسنس | Buy & Manage Your License](https://t.me/irsupplm_bot)

**ربات رسمی / Official bot: [@irsupplm_bot](https://t.me/irsupplm_bot)**

## 📣 [کانال رسمی تلگرام | Official Telegram Channel](https://t.me/irsuppchannel)

**اخبار و اطلاعیه‌ها / News & announcements: [@irsuppchannel](https://t.me/irsuppchannel)**

---

<div dir="rtl">

## فارسی

### اتصال بین سرورها، با مدیریت یکپارچه

**PXCloud Tunnel** ابزاری برای راه‌اندازی و مدیریت اتصال بین دو سرور است؛ برای نمونه، یک سرور ایران و یک سرور خارج. با تعریف مسیرهای موردنظر، ترافیک انتخاب‌شده از اتصال بین این دو سرور عبور می‌کند. هدف پروژه، ساده‌ترکردن نصب، مدیریت مسیر ترافیک و بررسی کیفیت اتصال در یک محیط منظم است.

این مجموعه چند گزینهٔ اتصال، از جمله **Rakhsh**، در اختیار مدیر سرور قرار می‌دهد. جزئیات طراحی و سازوکار داخلی این گزینه‌ها در صفحهٔ محصول منتشر نمی‌شود.

### امکانات

- **مدیریت از یک منوی مشترک:** نصب، راه‌اندازی مجدد، حذف و تنظیم گزینه‌های اتصال.
- **پایش کیفیت:** بررسی تأخیر، اتلاف بسته و وضعیت مسیرهای نصب‌شده.
- **جابه‌جایی خودکار مسیر (Failover):** انتخاب مسیر جایگزین هنگام قطع اتصال یا افت کیفیت، در صورت وجود مسیر مناسب. Rakhsh نیز در این انتخاب شرکت می‌کند.
- **تست و مقایسه:** نمایش نتایج پینگ، اتلاف بسته و سرعت ارسال و دریافت در جدول مشترک.
- **هدایت ترافیک انتخابی:** تعریف رنج IP کاربران و تنظیم مسیر ترافیک سرویس‌های پشتیبانی‌شده.
- **تنظیمات فایروال و سرویس:** مدیریت اتصال‌ها از طریق سرویس‌های سیستم و ابزارهای مدیریتی پروژه.
- **لایسنس وابسته به سرور:** فعال‌سازی و بررسی مجوز برای جفت سرور ثبت‌شده.

### جابه‌جایی خودکار چگونه کمک می‌کند؟

وقتی چند مسیر نصب و مانیتورینگ فعال باشد، سیستم کیفیت آن‌ها را مقایسه می‌کند. قطع مسیر یا افزایش اتلاف بسته می‌تواند باعث انتخاب مسیر جایگزین شود. برای تغییر مسیر صرفاً به‌دلیل کیفیت بهتر، شرایط پایداری نیز بررسی می‌شود تا جابه‌جایی‌های مکرر کمتر شود. این قابلیت تضمین نمی‌کند که تمام نشست‌های فعال بدون وقفه باقی بمانند.

### لایسنس و شروع استفاده

1. برای خرید و مدیریت مجوز، وارد **[ربات رسمی خرید لایسنس](https://t.me/irsupplm_bot)** شوید.
2. اطلاعات سرور ایران را برای ثبت مجوز ارائه کنید؛ سرور مقابل از طریق فرایند جفت‌سازی به مجوز مرتبط می‌شود.
3. پس از انتشار نسخهٔ قابل نصب، بسته را فقط از بخش **[Releases](https://github.com/IRSupp/PXCloud-Tunnel/releases)** و اطلاعیه‌های رسمی دریافت کنید.
4. اتصال‌های موردنیاز، رنج ترافیک و تنظیمات پایش را متناسب با شبکهٔ خود تنظیم کنید.

بررسی دوره‌ای آنلاین مجوز هر **۶ ساعت** انجام می‌شود. برای انقضای اشتراک، مهلت **۶ساعته** در نظر گرفته شده است؛ ادامهٔ کار همچنین به معتبرماندن تأییدیهٔ آنلاین وابسته است. قیمت و پلن‌های قابل خرید را در ربات بررسی کنید.

### پیش‌نیاز و وضعیت نسخه

- محیط هدف فعلی: **Ubuntu 24.04، معماری x86_64**، روی هر دو سرور.
- دسترسی مدیریتی و ارتباط شبکهٔ قابل‌استفاده بین دو سرور لازم است.
- منوی مدیریت فعلی **انگلیسی** است.
- نسخهٔ پایه: **1.6.0-rc.1 — نامزد انتشار**. بستهٔ نهایی کامپایل‌شده هنوز در این مخزن منتشر نشده است. عنوان Stable پس از تکمیل اعتبارسنجی بستهٔ نهایی تعیین می‌شود.
- سقف ارسال پیش‌فرض Rakhsh برای تنظیمات جدید **۱۰۰ مگابیت‌برثانیه** است؛ این عدد تضمین سرعت واقعی نیست و تنظیمات قبلی را تغییر نمی‌دهد.

سرعت، تأخیر و پایداری به مسیر شبکه، ظرفیت سرورها، محدودیت‌های دیتاسنتر و نوع ترافیک وابسته‌اند. پروژه تضمین سرعت ثابت، پینگ مشخص یا اتصال بدون قطعی ارائه نمی‌کند.

**کد اختصاصی پروژه منتشر نمی‌شود.** این مخزن برای معرفی محصول، اطلاعیه‌ها و خروجی‌های تأییدشدهٔ انتشار است. اعلان‌ها و الزامات مجوز وابستگی‌های ثالث حفظ می‌شوند.

</div>

---

## English

### Server-to-server connectivity, managed in one place

**PXCloud Tunnel** helps administrators deploy and manage connectivity between two servers—for example, one in Iran and one abroad. Selected traffic can be routed through this connection according to the configured rules. The project brings installation, traffic routing and connection-quality checks into a single management environment.

The suite offers multiple connection options, including **Rakhsh**. Internal implementation details and transport mechanisms are not disclosed on this product page.

### Features

- **Unified management:** install, restart, remove and configure connection options.
- **Quality monitoring:** track latency, packet loss and the health of installed paths.
- **Automatic failover:** select an available alternative when the active path fails or deteriorates. Rakhsh participates in path selection.
- **Tests and comparisons:** view ping, packet loss, upload and download results in a shared table.
- **Selective traffic routing:** configure client IP ranges and routing for supported services.
- **Firewall and service management:** manage connections through system services and the project tools.
- **Server-bound licensing:** activate and validate the registered server pair.

### Automatic path selection

With multiple paths installed and monitoring enabled, the system compares their quality. A failed path or excessive packet loss can trigger a switch to a suitable alternative. Quality-driven switches also require sustained improvement to reduce unnecessary switching. Failover does not guarantee uninterrupted continuity for every existing session.

### Licensing and getting started

1. Visit the **[official licensing bot](https://t.me/irsupplm_bot)** to purchase and manage your license.
2. Provide the Iran server information for registration; the remote server is associated through the pairing process.
3. Once an installable build is published, obtain it only from **[Releases](https://github.com/IRSupp/PXCloud-Tunnel/releases)** and official announcements.
4. Configure your connections, traffic ranges and monitoring settings for your network.

Online license checks run every **six hours**. Subscription expiration has a **six-hour grace period**; continued operation also requires a valid online lease. Consult the bot for available plans and pricing.

### Requirements and release status

- Current target: **Ubuntu 24.04, x86_64**, on both servers.
- Administrative access and usable network connectivity between the servers are required.
- The management menu is currently **English**.
- Baseline version: **1.6.0-rc.1 — release candidate**. No final compiled package has been published in this repository yet. Stable status requires validation of the final artifact.
- New Rakhsh configurations default to a **100 Mbps sending cap**. This is not a throughput guarantee and does not modify existing configurations.

Throughput, latency and stability depend on network routing, server capacity, datacenter restrictions and traffic characteristics. No fixed speed, specific latency or uninterrupted connectivity is guaranteed.

**Proprietary source code is not published.** This repository is reserved for product information, announcements and approved release artifacts. Applicable third-party notices and license obligations are preserved.

---

**🛒 [خرید لایسنس / Buy a license](https://t.me/irsupplm_bot) · 📣 [کانال تلگرام / Telegram channel](https://t.me/irsuppchannel)**
