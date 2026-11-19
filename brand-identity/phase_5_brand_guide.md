# 📖 Phase 5 — Brand Guide (دليل الهوية الكاملة)

---

## الهدف
توثيق كل عناصر الهوية البصرية في دليل واحد واضح يمكن مشاركته مع أي مصمم أو مطور لاحقاً.

---

## محتويات دليل الهوية

### 1. 🏷️ ملخص العلامة التجارية

```
الاسم: ___________
الشعار (Tagline): ___________
المجال: ___________
الجمهور: ___________
الشخصية: [3 كلمات]
نبرة الصوت: ___________
```

---

### 2. 🖼️ اللوجو

```
الملفات المتوفرة:
⚠️ أنشئ PNG/ICO فقط إن كانت لديك أداة تحويل فعلية — وإلا سلّم SVG + خطوات التصدير (Inkscape / Figma / realfavicongenerator)
□ Full Logo (أفقي) — SVG (+ PNG إن أمكن إنشاؤه فعلاً)
□ Stacked Logo (عمودي) — SVG + PNG
□ Icon Only — SVG + PNG + ICO (للـ Favicon)
□ Wordmark Only — SVG + PNG
□ Dark Version — SVG + PNG
□ Light Version — SVG + PNG
□ Monochrome — SVG + PNG

قواعد الاستخدام:
✅ الحجم الأدنى: [X]px عرضاً
✅ المسافة الواجبة حول اللوجو (Clear Space): [X]px من كل جهة
❌ ممنوع: تغيير النسب
❌ ممنوع: تغيير الألوان خارج الـ Palette
❌ ممنوع: إضافة تأثيرات (ظل، توهج، تدرج غير مقصود)
❌ ممنوع: وضع على خلفية تقلل التباين
```

---

### 3. 🎨 نظام الألوان

```
[استيراد من Phase 3 — نسخ الجدول الكامل هنا]

Primary: #______ — الاستخدام: ___________
Secondary: #______ — الاستخدام: ___________
Accent: #______ — الاستخدام: ___________
Background Light: #______
Background Dark: #______
Text Primary: #______
Text Secondary: #______

CSS Variables: [رابط أو كود الملف]
```

---

### 4. 🔤 الخطوط

```
[استيراد من Phase 4 — نسخ الخلاصة هنا]

خط العناوين: ___________  |  الأوزان: 700, 800
خط النصوص: ___________    |  الأوزان: 400, 500, 600
خط الأرقام: ___________   |  الأوزان: 400, 700

Type Scale: [رابط أو كود CSS Variables]
```

---

### 5. 📐 Spacing & Layout

```css
/* نظام المسافات — مبني على 4px Base */
:root {
  --space-1:  0.25rem;  /* 4px */
  --space-2:  0.5rem;   /* 8px */
  --space-3:  0.75rem;  /* 12px */
  --space-4:  1rem;     /* 16px */
  --space-5:  1.25rem;  /* 20px */
  --space-6:  1.5rem;   /* 24px */
  --space-8:  2rem;     /* 32px */
  --space-10: 2.5rem;   /* 40px */
  --space-12: 3rem;     /* 48px */
  --space-16: 4rem;     /* 64px */
  --space-20: 5rem;     /* 80px */
  --space-24: 6rem;     /* 96px */
  --space-32: 8rem;     /* 128px */

  /* Border Radius */
  --radius-sm:   0.25rem;  /* 4px */
  --radius-md:   0.5rem;   /* 8px */
  --radius-lg:   0.75rem;  /* 12px */
  --radius-xl:   1rem;     /* 16px */
  --radius-2xl:  1.5rem;   /* 24px */
  --radius-full: 9999px;   /* Circle/Pill */

  /* Shadows */
  --shadow-sm:  0 1px 2px 0 rgb(0 0 0 / 0.05);
  --shadow-md:  0 4px 6px -1px rgb(0 0 0 / 0.1);
  --shadow-lg:  0 10px 15px -3px rgb(0 0 0 / 0.1);
  --shadow-xl:  0 20px 25px -5px rgb(0 0 0 / 0.1);
  --shadow-2xl: 0 25px 50px -12px rgb(0 0 0 / 0.25);

  /* Transitions */
  --transition-fast:   150ms cubic-bezier(0.4, 0, 0.2, 1);
  --transition-normal: 300ms cubic-bezier(0.4, 0, 0.2, 1);
  --transition-slow:   500ms cubic-bezier(0.4, 0, 0.2, 1);
}
```

---

### 6. 📸 نمط الصور (Image Style)

```
أسلوب الصور المفضل:
□ Photography واقعية
□ Illustrations
□ Icons + Graphics
□ مزيج

إرشادات الصور:
• نسبة الألوان في الصور يجب أن تتناسب مع الـ Palette
• الفلتر المقترح: ___________
• ما يجب تجنبه: ___________
```

---

### 7. 🚫 قواعد "لا تفعل" (Don'ts)

```
❌ لا تغيير ألوان اللوجو
❌ لا تمديد أو ضغط اللوجو
❌ لا استخدام خطوط خارج الـ Brand Fonts
❌ لا ألوان خارج الـ Palette المعتمد
❌ لا تأثيرات بصرية غير مقصودة (Glows, Drops, Gradients)
❌ لا وضع اللوجو على خلفية منخفضة التباين
```

---

## 🛑 GATE FINAL — بوابة دليل الهوية

⛔ دليل الهوية مكتمل عندما:
□ كل الأقسام السبعة مكتملة
□ ملفات SVG للوجو كلها جاهزة
□ CSS Variables الكاملة (ألوان + خطوط + مسافات + ظلال) مكتوبة
□ العميل وافق على كل شيء

✅ بعد اعتماد الدليل:
→ إذا Mode C فقط: التسليم اكتمل
→ إذا Mode A: انتقل لـ phases/phase_1_research.md
   مع إرفاق دليل الهوية كمرجع في Gate A
