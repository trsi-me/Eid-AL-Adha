# Eid AL-Adha

## 1. ما هو المشروع؟

صفحة تهنئة بعيد الأضحى. العنوان: `Eid AL-Adha | عيد الأضحى`. النص الظاهر: `كل عام والمبرمجين بخير` ثم `- عيد أضحى مبارك -`، مع صورة خروف وظل متحرك.

## 2. لماذا يوجد هذا المشروع؟

استنتاج من الكود: الصفحة بطاقة عرض ثابتة للتهنئة مع حركة CSS وصورة.

## 3. من يستخدمه؟

الزائر الذي يفتح `Eid AL-Adha.html`. مستخدمون مسجلون غير موجودين.

## 4. ماذا يستطيع النظام أن يفعل؟

عرض عنوان وعبارة تهنئة. تحريك الصورة للأعلى والأسفل عبر `sheep-float` كل 2 ثانية، وتحريك الظل عبر `sheep-shadow`. إظهار العناصر بحركة ScrollReveal من الأعلى والأسفل.

## 5. كيف يعمل النظام؟

المتصفح يحمّل HTML ثم CSS ثم سكربتين لـ ScrollReveal ثم `Eid AL-Adha.js`. السكربت ينشئ `ScrollReveal` بمسافة 90px ومدة 3000 ويكشف `.home-data` من الأعلى بتأخير 400 و`.home-img` من الأسفل بتأخير 600.

## 6. أمثلة واقعية

فتح الصفحة يظهر النص والتهنئة. صورة `Sheep.png` تتحرك 15 بكسل عمودياً. إن غاب ملف الصورة يظهر بديل النص `Sheep Img` في سمة alt.

## 7. رحلة المستخدم

فتح `Eid AL-Adha.html`. القراءة من اليمين لأن `dir="rtl"` و`lang="ar"`. أزرار أو خطوات حفظ غير موجودة.

## 8. الوحدات والأقسام

| الجزء | الملف | الوظيفة |
| --- | --- | --- |
| المحتوى | Eid AL-Adha.html | العنوان والنص والصورة |
| الحركة والتخطيط | Eid AL-Adha.css | تدرج الخلفية وحركة الخروف |
| الظهور | Eid AL-Adha.js | ScrollReveal |

## 9. الشركات والكيانات

غير موجود في الملفات الحالية.

## 10. الصلاحيات

غير موجود في الملفات الحالية.

## 11. الأتمتة وWorkflows

حركتان CSS لا نهائيتان `alternate` مدتهما 2s. ScrollReveal عند التحميل. سير عمل خادم غير موجود.

## 12. التكامل بين الوحدات

HTML يحدد الأصناف `home-data` و`home-img`. CSS يحرّك `img` داخل `.home-img`. JS يستهدف الصنفين نفسيهما.

## 13. المصطلحات

| المصطلح | المعنى |
| --- | --- |
| home-containner | اسم الصنف كما هو مكتوب (بحرف n زائد) |
| sheep-float | حركة الصورة |
| ScrollReveal | مكتبة إظهار عند التمرير |

## 14. الأسئلة الشائعة

**أين صورة الخروف؟** المسار في الصفحة: `../ProjectsVSCode/Gallery/Sheep.png`، وهذا الملف غير موجود داخل مجلد `Eid AL-Adha`.

**لماذا سكربت ScrollReveal مرتين؟** الصفحة تحمّل `../Files For Programing/scrollreveal.min.js` ثم `https://unpkg.com/scrollreveal`.

## 15. Architecture

```
Browser
  -> Eid AL-Adha.html
  -> Eid AL-Adha.css + Google Fonts
  -> scrollreveal (مسار محلي نسبي + unpkg)
  -> Eid AL-Adha.js
  -> صورة خارج المجلد
```

## 16. Tech Stack

HTML وCSS وJavaScript. الخط IBM Plex Sans Arabic من Google Fonts بأوزان 100 إلى 700. مكتبة ScrollReveal من مسار نسبي ومن unpkg، رقم الإصدار في رابط unpkg غير موثق.

## 17. Project Structure

```
Eid AL-Adha/
  Eid AL-Adha.html
  Eid AL-Adha.css
  Eid AL-Adha.js
```

## 18. Frontend

صفحة واحدة RTL. متغيرات الخط في `:root`: 0.75rem و1.5rem و2.375rem، وتكبر عند `min-width: 1024px`. عند `min-width: 2048px` قيمة `zoom: 1.7`، وعند `min-width: 3848px` قيمة `zoom: 3.1`. أصناف `.home-containner` في استعلامات العرض مكتوبة بينما جسم الصفحة يستخدم `.home`.

## 19. Backend

غير موجود في الملفات الحالية.

## 20. Request Flow

```
Browser
  -> HTML
  -> CSS animations
  -> ScrollReveal global sr
  -> reveal .home-data and .home-img
```

## 21. Database

غير موجود في الملفات الحالية.

## 22. API

غير موجود في الملفات الحالية.

## 23. Authentication & Authorization

غير موجود في الملفات الحالية.

## 24. Security

جلسات أو تحقق غير موجودة. الصفحة تحمّل سكربتاً من unpkg. أيقونة تبويب غير موجودة.

## 25. Configuration

المدد 3000 و400 و600 مكتوبة في `Eid AL-Adha.js`. الألوان #182848 و#4B6CB7 في CSS. ملفات بيئة غير موجودة.

## 26. Integrations

Google Fonts. unpkg.com/scrollreveal. مسار محلي خارج المجلد: `../Files For Programing/scrollreveal.min.js`. صورة خارج المجلد: `../ProjectsVSCode/Gallery/Sheep.png`.

## 27. Scheduled Jobs

حركات CSS متكررة فقط. مهام مجدولة على خادم غير موجودة.

## 28. File Storage

الصورة مشار إليها بمسار نسبي خارج مجلد المشروع. مجلد uploads غير موجود.

## 29. Logging & Monitoring

معالجة أخطاء عند غياب `ScrollReveal` أو الصورة غير موجودة في الملفات الحالية.

## 30. Installation

افتح `Eid AL-Adha.html`. لظهور الصورة ضع الملف في المسار النسبي المذكور أو عدّل المسار. لعمل ScrollReveal يكفي نسخة unpkg عند وجود شبكة، أو الملف المحلي إن وُجد بجانب المجلد الأب.

## 31. Development Guide

النص في `Eid AL-Adha.html`. الحركة في CSS. توقيت الظهور في `Eid AL-Adha.js` على الأصناف `.home-data` و`.home-img`.

## 32. Deployment

غير موجود في الملفات الحالية.

## 33. Backup & Recovery

غير موجود في الملفات الحالية.

## 34. Troubleshooting

| العرض | السبب في الملفات |
| --- | --- |
| مربع صورة مكسور | Sheep.png خارج المجلد |
| ظهور فوري بلا حركة دخول | ScrollReveal غير معرّف |
| اسم الصنف containner | الهجاء مكتوب هكذا في HTML وCSS |

## 35. Dependencies

ScrollReveal عبر unpkg بلا رقم إصدار في الرابط، ونسخة محلية مسارها `../Files For Programing/scrollreveal.min.js` ووجودها بجانب هذا المجلد غير موثق من داخل مجلد العيد. Google Fonts IBM Plex Sans Arabic.

## 36. Known Limitations

الصورة والسكربت المحلي خارج المجلد. استعلامات CSS تشير إلى أصناف صفحة أخرى (home-img بعرض 400px) بينما عنصر الصورة بلا أبعاد ثابتة في النمط الأساسي. أيقونة تبويب غير موجودة. `zoom` على الشاشات العريضة جداً.

## 37. Current System State

| الحالة | التفصيل |
| --- | --- |
| موجود | نص التهنئة وحركة CSS وسكربت ScrollReveal |
| يعتمد على مسار خارجي | صورة الخروف |
| غير موثق | مالك الصفحة وسنة المناسبة |

## 38. Architecture Decisions

استنتاج من الكود: الحركة الزخرفية في CSS، والدخول في ScrollReveal، والصفحة قسم واحد `section.home`.

## 39. سجل التغييرات

سجل إصدارات غير موجود في الملفات الحالية.

## System Overview

```
الزائر
  -> Eid AL-Adha.html
  -> CSS (تدرج + حركة خروف)
  -> ScrollReveal
  -> صورة Sheep.png خارج المجلد
```

## Quick Reference

| الجزء | التقنية | الموقع | الوظيفة |
| --- | --- | --- | --- |
| الصفحة | HTML | Eid AL-Adha.html | نص التهنئة والصورة |
| الحركة | CSS | Eid AL-Adha.css | تدرج وظل وتحريك |
| الظهور | JavaScript | Eid AL-Adha.js | ScrollReveal |

## Quick Start

افتح `Eid AL-Adha.html` في المتصفح.

## For Non-Technical Users

صفحة تهنئة بعيد الأضحى للمبرمجين، مع صورة خروف متحركة.

## For Developers

ثلاثة ملفات. الصورة والسكربت المحلي مساراتهما تخرج من المجلد.
