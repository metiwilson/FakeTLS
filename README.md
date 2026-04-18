خیلی خوب! این یک **README کامل، حرفه‌ای و آماده انتشار در گیت‌هاب** است.  
فرمت استاندارد، تمیز، با Badge و ساختار مناسب.

می‌تونی همینو مستقیماً در فایل `README.md` پروژه‌ت قرار بدی:

--------------------------------------------

# MTProto FakeTLS Proxy for Windows  
اجرای پروکسی MTProto با FakeTLS روی ویندوز

[![Platform](https://img.shields.io/badge/Platform-Windows-blue.svg)]()  
[![Proxy](https://img.shields.io/badge/Protocol-MTProto%20FakeTLS-green.svg)]()  
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)]()

این مخزن یک آموزش کوتاه و ساده برای اجرای پروکسی MTProto با قابلیت **FakeTLS** روی ویندوز است.  
با استفاده از ابزار **mtg** می‌تونید روی ویندوز یک سرور پروکسی سبک، سریع و امن راه‌اندازی کنید.

---

## 📥 دانلود

آخرین نسخه mtg را از صفحه Releases دانلود کنید:

https://github.com/9seconds/mtg/releases

فایل ZIP مخصوص Windows را دریافت کنید و داخل یک پوشه Extract کنید.

---

## 🔑 ساخت Secret

در پوشه برنامه، یک PowerShell باز کرده و دستور زیر را اجرا کنید:

```powershell
mtg.exe generate-secret tg-secret
```

خروجی این دستور یک Secret معتبر برای پروکسی شماست.  
آن را برای مراحل بعدی نگه دارید.

---

## 🚀 اجرای پروکسی با FakeTLS

پروکسی را با دستور زیر اجرا کنید:

```powershell
mtg.exe run --bind-ip 0.0.0.0:443 --secret SECRET --fake-tls google.com
```

- پورت 443 کمک می‌کند ترافیک شما شبیه HTTPS واقعی دیده شود  
- گزینه `--fake-tls` باعث می‌شود پروکسی به شکل یک سایت واقعی (اینجا google.com) رفتار کند  
- مقدار `SECRET` را با مقدار ساخته شده جایگزین کنید

---

## 🔗 ساخت لینک اتصال تلگرام

برای تولید لینک اتصال تلگرام:

```powershell
mtg.exe generate-link 1 SECRET
```

یک لینک به شکل:

```
tg://proxy?server=IP&port=443&secret=SECRET
```

به شما داده می‌شود.  
کافیست روی آن کلیک کنید تا تلگرام شما به پروکسی متصل شود.

---

## ✔️ ویژگی‌ها

- پشتیبانی کامل از MTProto با FakeTLS  
- اجرا روی ویندوز بدون نیاز به WSL یا Docker  
- سرعت بالا و شناسایی سخت توسط DPI  
- بدون وابستگی اضافه و قابل حمل  

---

## ⚠️ نکته مهم

برای استفاده عمومی، لازم است پروکسی روی یک IP عمومی (VPS) اجرا شود.  
اجرای پروکسی روی ویندوز داخل ایران معمولاً قابل دسترس از بیرون نیست.
