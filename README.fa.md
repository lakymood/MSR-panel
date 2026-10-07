# پنل مدیریت SoftEther - MSR

پنل وب برای مدیریت کاربران SoftEther، کنترل حجم مصرفی، تاریخ انقضا و مدیریت سرویس.

## امکانات

- پنل مدیریت وب MSR
- مدیریت کاربران SoftEther
- ساخت کاربر از طریق پنل وب
- ساخت کاربر از طریق ربات تلگرام مدیریت
- تعیین حجم مصرفی برای هر کاربر
- مدیریت تاریخ انقضای سرویس
- افزودن روز سرویس
- افزایش Quota کاربر
- فعال و غیرفعال کردن کاربران
- حذف کاربر
- تغییر رمز عبور کاربران
- Reset کاربر بدون تغییر مصرف قبلی
- تعیین محدودیت اتصال همزمان برای هر کاربر
- ربات تلگرام کاربران
- اتصال و حذف اتصال حساب تلگرام کاربر
- ثبت و مدیریت مصرف ترافیک
- مدیریت وضعیت سهمیه کاربران
- داشبورد مدیریتی با نمایش CPU، RAM، Disk و نمودار زنده شبکه
- احراز هویت پنل مدیریت
- محافظت CSRF برای عملیات حساس پنل
- API پنل MSR
- API مبتنی بر Unix Socket
- سرویس‌ها و Timerهای مبتنی بر systemd
- امکان تعیین پورت HTTPS پنل هنگام نصب
- حفظ تنظیمات و وضعیت سرویس‌ها هنگام Upgrade
- مدیریت تنظیمات Apache

## نیازمندی‌ها

- Ubuntu یا Debian
- Apache2
- PHP
- Python 3
- SoftEther VPN Server
- SoftEther VPN Command Line Utility
- systemd

## نصب

### نصب مستقیم

wget https://github.com/lakymood/MSR-panel/releases/download/v1.2.0/msr-softether-panel_1.2.0.deb
sudo apt install -y ./msr-softether-panel_1.2.0.deb

### نصب فایل محلی

sudo apt install -y ./msr-softether-panel_1.2.0.deb

## پورت پنل وب

پورت پیش‌فرض HTTPS پنل:

1033

پورت پنل هنگام نصب قابل تغییر است.

## سرویس‌های تلگرام

در نصب Fresh:

- سرویس ربات تلگرام مدیریت فقط در صورت وجود Token ربات مدیریت فعال و اجرا می‌شود.
- سرویس ربات تلگرام کاربران فقط در صورت وجود Token ربات کاربران فعال و اجرا می‌شود.
- Timer مربوط به Notification Checker در صورت وجود Token ربات کاربران فعال و اجرا می‌شود.

در زمان Upgrade، وضعیت فعلی سرویس‌های تلگرام تغییر داده نمی‌شود.

## بررسی نصب

dpkg -s msr-softether-panel

بررسی سرویس‌ها:

systemctl status msrpanel.socket
systemctl status softether-quota.timer
systemctl status softether-telegram-bot.service
systemctl status softether-user-telegram-bot.service
systemctl status softether-notification-checker.timer

بررسی API Socket:

ls -l /run/msrpanel/api.sock

## ارتقا

sudo apt install -y ./msr-softether-panel_1.2.0.deb

تنظیمات موجود، دیتابیس سهمیه کاربران، State و اطلاعات Telegram در زمان Upgrade حفظ می‌شوند.

وضعیت فعلی سرویس‌های Telegram نیز در زمان Upgrade تغییر داده نمی‌شود.

## حذف

sudo apt remove msr-softether-panel

سرویس‌های مدیریت‌شده غیرفعال و تنظیمات سایت Apache حذف می‌شوند. تنظیمات و اطلاعات کاربران عمداً حفظ می‌شوند.

## SHA256

61cdc7529f59594df8a420b76d51d978b13b1eb1d4f93715ff062375bb471d3e

برای بررسی فایل:

sha256sum msr-softether-panel_1.2.0.deb

## اطلاعات بسته

| مورد | مقدار |
|---|---|
| نام بسته | msr-softether-panel |
| نسخه | 1.2.0 |
| معماری | all |
| پورت پیش‌فرض HTTPS پنل | 1033 |
| نوع بسته | Debian .deb |

## نکات امنیتی

- توکن ربات‌های تلگرام را منتشر نکنید.
- فایل‌های تنظیمات Production را منتشر نکنید.
- رمز عبور کاربران SoftEther را منتشر نکنید.
- فایل دیتابیس Production را منتشر نکنید.
- در صورت دسترسی پنل از شبکه غیرقابل اعتماد، از HTTPS استفاده کنید.

## نسخه Release

نسخه فعلی:

v1.2.0

فایل Debian این نسخه در بخش GitHub Releases قرار می‌گیرد.
