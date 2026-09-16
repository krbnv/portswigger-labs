# PortSwigger laboratoriya ishi

## Vazifaning maqsadi

Bu laboratoriyada **Broken Access Control** zaifligini amalda ko‘rib chiqdim. Ya’ni saytning administrator sahifasi yashirilgan bo‘lsa ham, agar server foydalanuvchining huquqini tekshirmasa, oddiy foydalanuvchi ham admin panelga kirib qolishi mumkin.

## Bajarilgan ishlar

Avval laboratoriya saytini ochdim. Keyin sayt manzilining oxiriga:

```text
/robots.txt
```

deb yozdim.

`robots.txt` fayli qidiruv tizimlariga qaysi sahifalarni indekslamaslik kerakligini ko‘rsatadi. Shu fayl ichida quyidagi manzil bor edi:

```text
/administrator-panel
```

Shundan keyin sayt manzilining oxiriga:

```text
/administrator-panel
```

deb yozib, administrator paneliga kirdim.

Admin panel ochilgandan keyin foydalanuvchilar ro‘yxati chiqdi. Vazifa bo‘yicha `carlos` nomli foydalanuvchini o‘chirish kerak edi. Men `carlos` foydalanuvchisini topib, **Delete** tugmasini bosdim.

Shundan keyin laboratoriya muvaffaqiyatli bajarildi.

## Nima uchun bu zaiflik hisoblanadi?

Muammo shundaki, administrator sahifasi faqat yashirilgan, lekin to‘g‘ri himoyalanmagan.

`robots.txt` ichida admin panel manzilini ko‘rsatish sahifani himoya qilmaydi. Agar foydalanuvchi shu manzilni topsa va server uning admin ekanligini tekshirmasa, u administrator funksiyalariga kira olishi mumkin.

Bu holat **Broken Access Control** deb ataladi.

## Xulosa

Bu vazifada men `robots.txt` orqali yashirin admin sahifani topishni va noto‘g‘ri sozlangan access control qanday muammo keltirib chiqarishini tushundim.

Admin panel kabi muhim sahifalar faqat URL’ni yashirish bilan emas, server tomonda foydalanuvchining huquqini tekshirish orqali himoyalanishi kerak.

> Ushbu amaliyot faqat PortSwigger Web Security Academy o‘quv laboratoriyasida bajarildi.
