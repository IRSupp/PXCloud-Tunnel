<div align="center">

# PXCloud Tunnel

### Your servers. One control center.

**اتصال بین سرورها، با مدیریت یکپارچه**

راه‌اندازی · پایش کیفیت · مسیریابی انتخابی · جابه‌جایی خودکار

<p>
<a href="https://t.me/irsupplm_bot"><img alt="Buy a license" src="https://img.shields.io/badge/BUY_A_LICENSE-irsupplm__bot-F4B942?style=for-the-badge&logo=telegram&logoColor=white"></a>
<a href="https://github.com/IRSupp/PXCloud-Tunnel/releases"><img alt="Downloads" src="https://img.shields.io/badge/DOWNLOADS-Releases-2563EB?style=for-the-badge&logo=github&logoColor=white"></a>
<a href="https://t.me/irsuppchannel"><img alt="Official channel" src="https://img.shields.io/badge/NEWS-irsuppchannel-0D9488?style=for-the-badge&logo=telegram&logoColor=white"></a>
</p>

**[خرید و مدیریت لایسنس](https://t.me/irsupplm_bot) · [کانال رسمی](https://t.me/irsuppchannel)**

Ubuntu 24.04 · x86_64 · English management menu

[فارسی](#فارسی)  /  [English](#english)

</div>

---

<div dir="rtl">

## فارسی

### کنترل مسیر، از یک نقطه

**PXCloud Tunnel** مجموعه‌ای برای اتصال دو سرور و مدیریت ترافیک میان آن‌هاست. مسیرهای موردنیاز را راه‌اندازی کنید، کیفیت اتصال را ببینید و مشخص کنید ترافیک کدام کاربران یا سرویس‌ها از سرور مقابل عبور کند؛ همه از یک منوی مدیریتی.

چند گزینهٔ اتصال، از جمله **Rakhsh**، در یک محیط مشترک مدیریت می‌شوند. نصب، پایش، تست و مدیریت مسیرها به ابزارهای پراکنده نیاز ندارد.

### امکانات در یک نگاه

| قابلیت | کاربرد |
| :--- | :--- |
| **مدیریت یکپارچه** | نصب، توقف، راه‌اندازی مجدد، حذف و تنظیم اتصال‌ها |
| **پایش کیفیت** | مشاهدهٔ وضعیت مسیرها، تأخیر و اتلاف بسته |
| **Failover خودکار** | انتخاب مسیر جایگزین هنگام قطع یا افت کیفیت؛ شامل Rakhsh |
| **تست مقایسه‌ای** | نمایش پینگ، اتلاف بسته و سرعت ارسال و دریافت در یک جدول |
| **مسیریابی انتخابی** | هدایت رنج کاربران و ترافیک سرویس‌های پشتیبانی‌شده |
| **مدیریت سرویس و فایروال** | تنظیمات اتصال و سرویس‌های سیستم از یک محیط |
| **لایسنس وابسته به سرور** | ثبت سرور ایران و جفت‌سازی سرور مقابل |

### شروع استفاده

**۱ — دریافت مجوز**  
از **[ربات رسمی @irsupplm_bot](https://t.me/irsupplm_bot)** پلن موردنظر را انتخاب و اطلاعات سرور ایران را ثبت کنید. قیمت و شرایط هر پلن در ربات نمایش داده می‌شود.

**۲ — دریافت بسته**  
بسته‌های قابل نصب و یادداشت تغییرات در **[Releases](https://github.com/IRSupp/PXCloud-Tunnel/releases)** قرار می‌گیرند. فایل نصب و بستهٔ همان نسخه را کنار هم نگه دارید و مراحل همان انتشار را دنبال کنید. فایل خودکار «Source code» گیت‌هاب، بستهٔ نصب محصول نیست.

**۳ — تنظیم اتصال**  
مجوز را فعال کنید، سرور مقابل را جفت کنید و اتصال‌ها، مسیر ترافیک و پایش کیفیت را تنظیم کنید. دستور بازکردن منوی مدیریت پس از نصب: **`pxcloud`**.

### پیش‌نیازها

| مورد | نیاز فعلی |
| :--- | :--- |
| سیستم‌عامل هر دو سرور | Ubuntu 24.04 |
| معماری | x86_64 / amd64 |
| دسترسی | root یا دسترسی مدیریتی معادل |
| شبکه | ارتباط قابل‌استفاده بین دو سرور |
| زبان منو | انگلیسی |

<details>
<summary><strong>پرسش‌های متداول</strong></summary>

**آیا Rakhsh در Failover شرکت می‌کند؟**  
بله. با نصب چند مسیر و فعال‌کردن پایش، Rakhsh نیز در ارزیابی کیفیت و انتخاب مسیر شرکت می‌کند. تنظیمات پایداری، جابه‌جایی مکرر بین مسیرها را محدود می‌کنند. حفظ تمام نشست‌های فعال هنگام تغییر مسیر تضمین نمی‌شود.

**آیا سرعت مشخصی تضمین شده است؟**  
خیر. کیفیت مسیر اینترنت، ظرفیت سرورها و شرایط شبکه تعیین‌کننده‌اند. مقدار پیش‌فرض ۱۰۰ مگابیت‌برثانیه برای تنظیم جدید Rakhsh یک سقف تنظیمی است، نه تضمین سرعت.

**لایسنس چه زمانی بررسی می‌شود؟**  
بررسی آنلاین دوره‌ای هر ۶ ساعت انجام می‌شود. اشتراک پس از انقضا ۶ ساعت مهلت دارد؛ ادامهٔ کار به معتبرماندن تأییدیهٔ مجوز نیز وابسته است.

**آیا این مخزن شامل سورس اختصاصی محصول است؟**  
خیر. این مخزن برای معرفی و توزیع محصول است. کد اختصاصی در بستهٔ مشتری به‌صورت کامپایل‌شده ارائه می‌شود. اعلان‌ها و فایل‌های الزامی اجزای ثالث همراه بسته حفظ می‌شوند.

</details>

### وضعیت انتشار

**نسخهٔ آزمایشی منتشرشده: [1.6.0-rc.2](https://github.com/IRSupp/PXCloud-Tunnel/releases/tag/v1.6.0-rc.2).**  
بستهٔ کامپایل‌شده، نصب‌کننده و checksum آمادهٔ دریافت‌اند. آزمون‌های تکمیلی برای انتشار Stable ادامه دارند. فقط فایل‌هایی را دریافت کنید که همراه یادداشت انتشار و checksum در بخش Releases قرار گرفته‌اند.

**خرید و مدیریت اشتراک:** [@irsupplm_bot](https://t.me/irsupplm_bot)  
**اخبار و نسخه‌های جدید:** [@irsuppchannel](https://t.me/irsuppchannel)

</div>

---

## English

### One place to manage your server connections

**PXCloud Tunnel** connects two servers and gives you a shared control center for deployment, traffic routing and connection quality. Choose which users or supported services use the remote server, compare available paths and manage their lifecycle from one menu.

Multiple connection options, including **Rakhsh**, share the same management, monitoring and testing workflow.

### Built for everyday operation

| Capability | What it provides |
| :--- | :--- |
| **Unified management** | Install, stop, restart, remove and configure connections |
| **Quality monitoring** | Connection status, latency and packet loss |
| **Automatic failover** | Alternate-path selection on failure or quality degradation, including Rakhsh |
| **Comparative testing** | Ping, loss, upload and download results in one table |
| **Selective routing** | Route client subnets and supported service traffic |
| **Service & firewall controls** | Manage connection settings and system services |
| **Server-bound licensing** | Register the Iran-side server and pair its remote endpoint |

### Get started

1. **Get a license** through **[@irsupplm_bot](https://t.me/irsupplm_bot)** and register the Iran-side server. Plans and pricing are listed in the bot.
2. **Get the matching installer and package** from **[Releases](https://github.com/IRSupp/PXCloud-Tunnel/releases)**. Keep them in the same directory and follow the instructions for that version. GitHub’s automatic “Source code” downloads are not product installers.
3. **Activate and configure** your license, pair the remote endpoint, then set up connections, traffic routing and monitoring. After installation, open the management menu with `pxcloud`.

**Requirements:** Ubuntu 24.04 on both servers, x86_64 / amd64, administrative access and a usable network path. The management menu is in English.

<details>
<summary><strong>Operation & licensing</strong></summary>

- Failover requires multiple installed paths and active monitoring. Stability checks reduce repeated switching; uninterrupted survival of every active session is not guaranteed.
- Throughput depends on the network path and server capacity. The 100 Mbps default for new Rakhsh configurations is a configured cap, not a speed guarantee.
- Online license checks run every six hours. Subscriptions have a six-hour expiry grace period; a valid license lease is also required.
- This is a product distribution and documentation repository. Proprietary application code is supplied in compiled form. Required third-party notices and corresponding materials remain included.

</details>

### Release status

**Available preview: [1.6.0-rc.2](https://github.com/IRSupp/PXCloud-Tunnel/releases/tag/v1.6.0-rc.2).**  
The compiled package, installer and checksums are available. Further validation for Stable is in progress. Use only assets accompanied by release notes and checksums in Releases.

---

<div align="center">

**[Buy & manage your license](https://t.me/irsupplm_bot) · [Official announcements](https://t.me/irsuppchannel) · [Downloads](https://github.com/IRSupp/PXCloud-Tunnel/releases)**

**PXCloud Tunnel · IRSupp**

</div>
