# پنل مدیریت SoftEther - MSR

پنل وب برای مدیریت کاربران SoftEther، کنترل حجم مصرفی، تاریخ انقضا و مدیریت سرویس.

## امکانات

- پنل مدیریت وب
- مدیریت کاربران SoftEther
- تعیین حجم مصرفی برای هر کاربر
- مدیریت تاریخ انقضای سرویس
- ساخت کاربر از طریق پنل وب
- ساخت کاربر از طریق ربات تلگرام مدیریت
- ربات تلگرام کاربران
- ثبت و مدیریت مصرف ترافیک
- مدیریت وضعیت سهمیه کاربران
- فعال و غیرفعال کردن کاربران
- حذف کاربر
- تغییر رمز عبور کاربران
- احراز هویت پنل مدیریت
- محافظت CSRF برای عملیات حساس پنل
- API پنل MSR
- سرویس‌ها و Timerهای مبتنی بر systemd
- امکان تعیین پورت پنل هنگام نصب

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

دستور زیر فایل نسخه 1.1.1 را از GitHub دریافت و نصب می‌کند:

```bash
wget https://github.com/lakymood/MSR-panel/releases/download/v1.1.1/msr-softether-panel_1.1.1.deb && sudo apt install -y ./msr-softether-panel_1.1.1.deb
```

### نصب فایل محلی

اگر فایل deb را قبلاً دریافت کرده‌اید:

```bash
sudo apt install -y ./msr-softether-panel_1.1.1.deb
```

## پورت پنل وب

پورت پیش‌فرض پنل:

```text
8080
```

پورت پنل هنگام نصب قابل تغییر است.

## بررسی نصب

برای بررسی نسخه نصب‌شده:

```bash
dpkg -s msr-softether-panel
```

بررسی سرویس‌ها:

```bash
systemctl status msrpanel.socket
systemctl status softether-quota.timer
systemctl status softether-telegram-bot.service
systemctl status softether-user-telegram-bot.service
```

## ارتقا

برای ارتقای نسخه موجود:

```bash
sudo apt install -y ./msr-softether-panel_1.1.1.deb
```

## SHA256

مقدار SHA256 فایل نسخه 1.1.1:

```text
8bfdb4b09ce879b3c3b0b28f95e81bb91a39885d210966d7767d3afd73bd274c
```

برای بررسی فایل دانلودشده:

```bash
sha256sum msr-softether-panel_1.1.1.deb
```

## اطلاعات بسته

| مورد | مقدار |
|---|---|
| نام بسته | msr-softether-panel |
| نسخه | 1.1.1 |
| معماری | all |
| پورت پیش‌فرض پنل | 8080 |
| نوع بسته | Debian .deb |

## نکات امنیتی

- توکن ربات‌های تلگرام را منتشر نکنید.
- فایل‌های تنظیمات Production را منتشر نکنید.
- رمز عبور کاربران SoftEther را منتشر نکنید.
- فایل دیتابیس Production را منتشر نکنید.
- در صورت دسترسی پنل از شبکه غیرقابل اعتماد، از HTTPS استفاده کنید.

## نسخه Release

نسخه فعلی:

v1.1.1

فایل Debian این نسخه در بخش GitHub Releases قرار دارد.
