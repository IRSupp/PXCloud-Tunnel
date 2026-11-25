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

**[Stable 1.6.1](https://github.com/IRSupp/PXCloud-Tunnel/releases/tag/v1.6.1)** · Ubuntu 24.04 · x86_64 · English menu

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

### نصب روی هر دو سرور

در این راهنما **A سرور ایران** و **B سرور خارج** است؛ کشور سرور B محدودیتی ندارد.

از Assets همان نسخه، سه فایل زیر را دریافت و در یک پوشه روی **هر دو سرور** قرار دهید:

- `PXCloud-Tunnel-1.6.1-linux-x86_64.tar.gz`
- `PXCloud-Tunnel-Install.sh`
- `SHA256SUMS`

فایل‌های خودکار **Source code** برای نصب نیستند. سپس در همان پوشه اجرا کنید:

</div>

```bash
sha256sum -c SHA256SUMS
sudo bash PXCloud-Tunnel-Install.sh
sudo pxcloud --version
```

<div dir="rtl">

اگر بررسی checksum موفق نبود، نصب را ادامه ندهید و فایل‌های همان نسخه را دوباره دریافت کنید. موتورهای اتصال همراه بسته هستند؛ نصب بعضی وابستگی‌های سیستم ممکن است به مخازن Ubuntu نیاز داشته باشد.

### راه‌اندازی، قدم‌به‌قدم

**۱. فعال‌سازی در ایران**  
روی A دستور `sudo pxcloud license` را اجرا کنید. در منوی لایسنس، **Activate Iran license** را بزنید و کلید خریداری‌شده از ربات را وارد کنید. IP ثبت‌شده باید با IP عمومی سرور ایران مطابقت داشته باشد. گزینهٔ **Activate exempt Iran IP** فقط برای IPهایی است که مدیر سامانه قبلاً معاف کرده است.

**۲. جفت‌کردن سرور خارج**  
در همان منوی A، **Pair foreign server (from Iran)** را انتخاب کنید؛ IP عمومی B و مسیر خروجی `/root/PXCloud-invitation.json` را بدهید. این فایل خصوصی را با SSH/SCP به B انتقال دهید. روی B دستور `sudo pxcloud license` و گزینهٔ **Join pair (on foreign server)** را اجرا و مسیر فایل را وارد کنید. دعوت‌نامه باید ظرف **۱۵ دقیقه** استفاده شود.

**۳. ساخت اتصال‌ها روی ایران**  
با `sudo pxcloud` منوی اصلی را باز کنید. گزینهٔ **5 — Server setup / Import B bundle** را بزنید، نقش **A** را انتخاب و IP سرور B را وارد کنید. IP ایران به‌صورت خودکار شناسایی می‌شود؛ اگر شناسایی ممکن نبود، برنامه آن را می‌پرسد. سپس از بخش **TUNNELS** اتصال‌های موردنیاز را انتخاب و **Install** کنید. برای Failover حداقل دو مسیر نصب کنید.

**۴. انتقال تنظیمات اتصال به خارج**  
روی A از گزینهٔ **9 — Export B bundle** خروجی بگیرید؛ برای مثال `/root/PXCloud-B.json`. آن را خصوصی به B انتقال دهید. روی B از گزینهٔ **5**، نقش **B** را انتخاب و مسیر فایل را وارد کنید. اتصال‌های موجود در بسته روی B نصب می‌شوند. **این بسته با دعوت‌نامهٔ لایسنس متفاوت است و کلیدهای اتصال را در خود دارد؛ آن را در کانال، مخزن یا پیام عمومی قرار ندهید.**

**۵. انتخاب ترافیک کاربران**  
برای سرویس‌هایی که کاربرانشان رنج داخلی دارند، از گزینهٔ **6 — Client ranges & firewall**، رنج واقعی سرویس خود را وارد کنید. همان رنج‌ها باید در هر دو سمت تنظیم شوند. ابتدا روی **B** و سپس روی **A** مسیریابی را فعال کنید. هیچ رنجی از پیش برای کاربران انتخاب نشده است؛ مسیر کاربران باید از قبل روی A وجود داشته باشد. این بخش برای ترافیک IPv4 است.

برای **V2Ray / Xray** از گزینهٔ **15 — V2Ray / Xray Traffic** استفاده کنید و راهنمای همان بخش را دنبال کنید؛ صرف واردکردن رنج کاربران برای این سرویس‌ها کافی نیست.

**۶. بررسی اتصال**  
گزینهٔ **7 — Quality dashboard** وضعیت و مسیر فعال را نشان می‌دهد. از گزینهٔ **8 — Failover settings** حالت `auto` را انتخاب کنید تا مسیرهای نصب‌شده، از جمله Rakhsh، در انتخاب خودکار شرکت کنند. تنظیمات کیفیت از جابه‌جایی بی‌دلیل و پی‌درپی جلوگیری می‌کنند؛ عبور پینگ از یک عدد ثابت به‌تنهایی همیشه موجب سوئیچ نمی‌شود.

### حذف، نصب مجدد و بازیابی لایسنس

از نسخهٔ **1.6.1**، حذف سرویس‌ها هویت لایسنس را نگه می‌دارد؛ برای نصب مجدد نیازی به ساخت هویت تازه نیست. اگر در نسخهٔ قبلی پس از حذف با خطای `Iran identity already bound` روبه‌رو شده‌اید، ابتدا نسخهٔ جدید را نصب کنید و `sudo pxcloud license recover` را بزنید؛ همین گزینه با نام **Recover saved identity** در منوی لایسنس هم موجود است. بازیابی به بکاپ معتبر محلی و تأیید آنلاین نیاز دارد و تانل‌های حذف‌شده را برنمی‌گرداند. اگر بکاپ موجود نیست، فایل هویت فعلی را پاک نکنید و با پشتیبانی تماس بگیرید.

**Status** فقط وضعیت را می‌خواند. گزینهٔ صفر در صفحهٔ ابتدایی **Exit** است؛ اگر از منوی اصلی وارد لایسنس شده باشید، **Back** به همان منو برمی‌گردد.

**لایسنس تست روی IP معاف:** معافیت ثبت‌شده توسط مدیر، روی همان لایسنس و همان جفت اعمال می‌شود؛ پایان تست تا وقتی IP معاف است موجب قطع نمی‌شود. انتخاب **Activate exempt Iran IP** نیز کلید یا جفت را عوض نمی‌کند. بررسی شش‌ساعته حفظ می‌شود؛ پس از حذف معافیت، سیاست اشتراک اصلی در بررسی بعدی اعمال می‌شود و مجوز قبلی فقط تا موعد امضاشده‌اش اعتبار دارد. معافیت، لغو یا تعلیق لایسنس را دور نمی‌زند.

### آزمون و مدیریت روزمره

برای آماده‌کردن ابزار تست سرعت، روی **هر دو سرور** اجرا کنید:

</div>

```bash
sudo pxcloud test-setup
```

<div dir="rtl">

سپس روی A تست تمام مسیرهای نصب‌شده را اجرا کنید:

</div>

```bash
sudo pxcloud test --tunnel all --full --seconds 20 --streams 1
```

<div dir="rtl">

نتیجهٔ هر مسیر در جدول مقایسه‌ای می‌آید. `--streams 1` یک جریان TCP و `--streams 4` چهار جریان هم‌زمان را می‌سنجد. Upload و Download از دید سروری هستند که تست روی آن اجرا شده است. این سرعت **بین دو سرور** است، نه سرعت اینترنت یا سرور بازی؛ تست سرعت می‌تواند موقتاً روی ترافیک جاری اثر بگذارد.

| کار | مسیر دسترسی |
| :--- | :--- |
| بازکردن منو | `sudo pxcloud` |
| وضعیت یک‌باره | `sudo pxcloud status` |
| نسخهٔ نصب‌شده | `sudo pxcloud --version` |
| وضعیت لایسنس | `sudo pxcloud license status` |
| توقف، شروع، ری‌استارت یا نصب مجدد | انتخاب تونل ← گزینهٔ مربوطه |
| تست و جدول نتایج | گزینهٔ 11 |
| رویدادهای تغییر مسیر | گزینهٔ 10 |
| تنظیم بازیابی پورت wg-custome | گزینهٔ 12 |
| حذف سرویس‌های محصول | گزینهٔ 13؛ پس از بررسی پیام برنامه |

هر تونل به‌صورت سرویس systemd مدیریت می‌شود. نصب مجدد از منوی تونل، کلیدهای اتصال را نگه می‌دارد. پس از افزودن مسیر یا تغییر تنظیماتی که باید بین دو سمت مشترک باشند، بستهٔ B را دوباره صادر و وارد کنید.

### اگر اتصال برقرار نشد

ابتدا اعتبار لایسنس و جفت‌سازی، سپس تطابق IPها، صحیح‌بودن ساعت سرورها و جدیدبودن بستهٔ B را بررسی کنید. وضعیت مسیرها را در داشبورد و رویدادها را در گزینهٔ 10 ببینید. فایروال سیستم و فایروال دیتاسنتر باید ارتباط انتخاب‌شده را مجاز کنند. کلید لایسنس، دعوت‌نامه و بستهٔ خصوصی را در گزارش عمومی ارسال نکنید.

<details>
<summary><strong>پرسش‌های متداول</strong></summary>

**آیا Rakhsh در Failover شرکت می‌کند؟**  
بله. با نصب چند مسیر و فعال‌کردن پایش، Rakhsh نیز در ارزیابی کیفیت و انتخاب مسیر شرکت می‌کند. تنظیمات پایداری، جابه‌جایی مکرر بین مسیرها را محدود می‌کنند. حفظ تمام نشست‌های فعال هنگام تغییر مسیر تضمین نمی‌شود.

**آیا سرعت مشخصی تضمین شده است؟**  
خیر. کیفیت مسیر اینترنت، ظرفیت سرورها و شرایط شبکه تعیین‌کننده‌اند. مقدار پیش‌فرض ۱۰۰ مگابیت‌برثانیه برای تنظیم جدید Rakhsh یک سقف تنظیمی است، نه تضمین سرعت.

**لایسنس چه زمانی بررسی می‌شود؟**  
اعتبارسنجی آنلاین در چرخهٔ ۶ساعته انجام می‌شود؛ درخواست تمدید دو دقیقه پیش از پایان اعتبار آغاز می‌شود تا تأخیر شبکه باعث قطع بی‌دلیل نشود. اشتراک پس از انقضا ۶ ساعت مهلت دارد؛ ادامهٔ کار به معتبرماندن تأییدیهٔ مجوز نیز وابسته است.

**آیا این مخزن شامل سورس اختصاصی محصول است؟**  
خیر. این مخزن برای معرفی و توزیع محصول است. کد اختصاصی در بستهٔ مشتری به‌صورت کامپایل‌شده ارائه می‌شود. اعلان‌ها و فایل‌های الزامی اجزای ثالث همراه بسته حفظ می‌شوند.

</details>

### وضعیت انتشار

**نسخهٔ Stable: [1.6.1](https://github.com/IRSupp/PXCloud-Tunnel/releases/tag/v1.6.1).**  
بستهٔ کامپایل‌شده، نصب‌کننده و checksum آمادهٔ دریافت‌اند. اصلاحیهٔ 1.6.1 با ۹۵ تست مدیر، ۴۶ تست API و آزمون نصب، حذف، نصب مجدد و بازیابی واقعی هویت بررسی شده است. موتورهای تانل نسبت به 1.6.0 تغییر نکرده‌اند؛ نتایج تست مسیرها و Failover مربوط به آن نسخه‌اند. جزئیات محدودهٔ آزمون در یادداشت انتشار آمده است.

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

### Install on both servers

**A is the Iran-side server; B is the foreign server, in any country.** Download these three matching release assets and place them together on **both servers**:

- `PXCloud-Tunnel-1.6.1-linux-x86_64.tar.gz`
- `PXCloud-Tunnel-Install.sh`
- `SHA256SUMS`

GitHub's automatic **Source code** archives are not installers. In the directory containing the assets, run:

```bash
sha256sum -c SHA256SUMS
sudo bash PXCloud-Tunnel-Install.sh
sudo pxcloud --version
```

Stop if checksum verification fails and download the matching assets again. Connection engines are bundled; some system dependencies may still require Ubuntu repositories.

### Configure the pair

1. **Activate A.** Run `sudo pxcloud license` on A. Select **Activate Iran license** and enter your purchased key. The registered public IP must match A. **Activate exempt Iran IP** applies only to addresses previously exempted by the administrator.
2. **Pair B.** On A, select **Pair foreign server (from Iran)**, enter B's public IP and an output path such as `/root/PXCloud-invitation.json`. Transfer this private file to B over SSH/SCP. On B, run `sudo pxcloud license`, choose **Join pair (on foreign server)** and enter the file path. Use the invitation within **15 minutes**.
3. **Configure connections on A.** Open `sudo pxcloud`. Choose **5 — Server setup / Import B bundle**, select **A** and enter B's IP. A's IP is detected automatically, with an interactive prompt if detection fails. Install your chosen connections from **TUNNELS**. Install at least two paths for failover.
4. **Configure B.** On A, choose **9 — Export B bundle**, for example `/root/PXCloud-B.json`, and transfer it privately to B. On B, choose **5**, select **B** and import that file. The offered connections are installed automatically. **The connection bundle is separate from the license invitation and contains private keys. Never post either file publicly.**
5. **Route client traffic.** For services with client subnets, use **6 — Client ranges & firewall** to enter your actual ranges on both servers. Enable routing on **B first, then A**. No client subnet is preselected; the client route must already exist on A. This workflow routes IPv4 traffic. For **V2Ray / Xray**, use **15 — V2Ray / Xray Traffic** and follow its service-specific instructions instead of relying only on client subnets.
6. **Check operation.** **7 — Quality dashboard** displays path health and the active path. Set **8 — Failover settings** to `auto` for automatic selection across installed paths, including Rakhsh. Quality checks and hold times prevent repeated unnecessary switching; exceeding a single fixed ping value does not always trigger a change.

### Uninstall, reinstall and license recovery

From **1.6.1**, uninstall retains the licensing identity. Reinstall does not require a new identity. If an older uninstall caused `Iran identity already bound`, install the update and run `sudo pxcloud license recover`, also available as **Recover saved identity** in the licensing menu. Recovery requires an eligible signed local backup and fresh online approval. It does not restore removed tunnels. If the backup is missing, keep the current identity files and contact support.

**Status** is read-only. The initial licensing screen uses **Exit**; licensing opened from the main menu uses **Back**, which returns to that menu.

**Trials on exempt IPs:** an administrator-approved Iran IP exemption applies to the existing license and pair, so trial expiry does not interrupt an exempt pair. Manual **Activate exempt Iran IP** retains the key and peer. Six-hour checking remains in force. Removing the exemption restores the underlying subscription policy at the next check; an existing lease is usable only until its signed deadline. Revocation and suspension remain enforced.

### Test and manage

Prepare speed testing on **both servers**:

```bash
sudo pxcloud test-setup
```

Then test every installed path from A:

```bash
sudo pxcloud test --tunnel all --full --seconds 20 --streams 1
```

Results appear in a comparison table. `--streams 1` tests one TCP flow; `--streams 4` tests four concurrent flows. Upload/download are relative to the server running the test. These are **server-to-server** measurements, not Internet or game-server speeds. Speed tests may temporarily affect live traffic.

| Task | Access |
| :--- | :--- |
| Open the menu | `sudo pxcloud` |
| One-time status | `sudo pxcloud status` |
| Installed version | `sudo pxcloud --version` |
| License status | `sudo pxcloud license status` |
| Start, stop, restart or reinstall | Select the connection, then the corresponding action |
| Tests and results table | Menu 11 |
| Path-change events | Menu 10 |
| wg-custome port recovery settings | Menu 12 |
| Remove product services | Menu 13; review the displayed message |

Connections run as systemd services. Reinstalling through the connection menu preserves its keys. After adding a path or changing shared settings, export and import an updated B bundle.

### Connection troubleshooting

Check license validity and pairing, matching endpoint IPs, correct server clocks and the current B bundle first. Review path health in the dashboard and events in menu 10. Both the operating-system firewall and the datacenter firewall must permit the selected connection. Keep license keys, invitations and private bundles out of public reports.

<details>
<summary><strong>Operation & licensing</strong></summary>

- Failover requires multiple installed paths and active monitoring. Stability checks reduce repeated switching; uninterrupted survival of every active session is not guaranteed.
- Throughput depends on the network path and server capacity. The 100 Mbps default for new Rakhsh configurations is a configured cap, not a speed guarantee.
- Online verification follows a six-hour lease cycle; renewal starts two minutes before the deadline to avoid interruption while a response is in flight. Subscriptions have a six-hour expiry grace period; a valid license lease is also required.
- This is a product distribution and documentation repository. Proprietary application code is supplied in compiled form. Required third-party notices and corresponding materials remain included.

</details>

### Release status

**Stable release: [1.6.1](https://github.com/IRSupp/PXCloud-Tunnel/releases/tag/v1.6.1).**  
The compiled package, installer and checksums are available. Patch 1.6.1 passed 95 manager tests, 46 API tests, exact-package install/uninstall/reinstall checks and genuine identity recovery. Transport engines are unchanged from 1.6.0; path and failover measurements belong to that baseline. See the release notes for the validation scope.

---

<div align="center">

**[Buy & manage your license](https://t.me/irsupplm_bot) · [Official announcements](https://t.me/irsuppchannel) · [Downloads](https://github.com/IRSupp/PXCloud-Tunnel/releases)**

**PXCloud Tunnel · IRSupp**

</div>
