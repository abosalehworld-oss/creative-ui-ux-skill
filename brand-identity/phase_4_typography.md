# 🔤 Phase 4 — Typography (الخطوط والتدرج الطباعي)

---

## الهدف
اختيار خطوط ذات شخصية حقيقية — ليست "آمنة وممّلة" — وبناء تدرج طباعي (Type Scale) متسق على كل المنصات.

---

## الخطوة 1 — قواعد اختيار الخطوط (Anti-Slop Rules)

```
❌ ممنوع منعاً باتاً:
  • Roboto
  • Arial / Helvetica
  • Open Sans
  • Lato
  • Source Sans Pro
  • أي خط "آمن وتقليدي"

✅ مطلوب:
  خطوط ذات شخصية تعكس الـ Personality Card من Phase 1
```

---

## الخطوة 2 — البحث عن خطوط (Live Font Research)

```
الـ AI ← يبحث عن خطوط مناسبة:
  search_web: "best modern fonts 2025 2026 [الشخصية المطلوبة]"
  search_web: "google fonts [الكلمات المفتاحية] pairing"
  تصفح: https://fonts.google.com/
  تصفح: https://fontshare.com/ (خطوط مجانية ممتازة)
  تصفح: https://www.fontsquirrel.com/

للمشاريع العربية:
  تصفح: https://fonts.google.com/?subset=arabic
  خطوط موصى بها: IBM Plex Arabic, Noto Kufi Arabic,
                 Readex Pro, Cairo Play, Tajawal
```

---

## الخطوة 3 — Font Pairing (الثنائي الطباعي)

```
يجب اختيار خطين متناسقين:

خط العناوين (Display Font):
  الاسم: ___________
  المصدر: ___________
  الاستخدام: H1, H2, Hero text, العناوين الكبيرة
  الوزن المستخدم: 700 / 800 / 900

خط النصوص (Body Font):
  الاسم: ___________
  المصدر: ___________
  الاستخدام: P, H3-H6, UI text, Captions
  الوزن المستخدم: 400 / 500 / 600

خط الأرقام / البيانات (Mono Font) — اختياري:
  الاسم: ___________
  الاستخدام: Prices, Stats, Code, Tables

قواعد الـ Pairing:
  • لا تستخدم خطين من نفس العائلة (Serif + Serif = ممل)
  • الأفضل: Display decorative + Body neutral
  • أو: Serif display + Sans-serif body
  • أو: Geometric sans + Humanist sans
```

---

## الخطوة 4 — Type Scale (التدرج الطباعي)

```css
/* Type Scale — مبني على نسبة 1.25 أو 1.333 */

:root {
  /* Font Families */
  --font-display: 'اسم خط العناوين', sans-serif;
  --font-body: 'اسم خط النصوص', sans-serif;
  --font-mono: 'اسم الخط الرقمي', monospace;

  /* Font Sizes */
  --text-xs:   0.75rem;   /* 12px — Captions, Labels */
  --text-sm:   0.875rem;  /* 14px — Small text, Metadata */
  --text-base: 1rem;      /* 16px — Body text */
  --text-lg:   1.125rem;  /* 18px — Lead text */
  --text-xl:   1.25rem;   /* 20px — H4 */
  --text-2xl:  1.5rem;    /* 24px — H3 */
  --text-3xl:  1.875rem;  /* 30px — H2 */
  --text-4xl:  2.25rem;   /* 36px — H1 (mobile) */
  --text-5xl:  3rem;      /* 48px — H1 (desktop) */
  --text-6xl:  3.75rem;   /* 60px — Hero Display */
  --text-7xl:  4.5rem;    /* 72px — Hero Display XL */

  /* Line Heights */
  --leading-tight:  1.25;  /* Headlines */
  --leading-normal: 1.5;   /* Body text */
  --leading-relaxed: 1.75; /* Long-form content */

  /* Letter Spacing */
  --tracking-tight:  -0.025em; /* Headlines */
  --tracking-normal: 0;
  --tracking-wide:   0.05em;   /* Captions, Labels */
  --tracking-widest: 0.1em;    /* ALL CAPS text */

  /* Font Weights */
  --font-normal:    400;
  --font-medium:    500;
  --font-semibold:  600;
  --font-bold:      700;
  --font-extrabold: 800;
  --font-black:     900;
}
```

---

## الخطوة 5 — تحميل الخطوط بكفاءة

```html
<!-- Google Fonts — مثال -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=اسم+الخط:wght@400;500;600;700;800&display=swap" rel="stylesheet">

<!-- قواعد الأداء: -->
<!-- 1. preconnect إجباري -->
<!-- 2. display=swap إجباري -->
<!-- 3. حمّل الأوزان المطلوبة فقط -->
<!-- 4. لا تحمّل أكثر من خطين من Google Fonts -->
```

---

## 🛑 GATE — بوابة الخطوط

⛔ لا تنتقل لـ Phase 5 قبل:
□ Font Pairing محدد (Display + Body)
□ Type Scale مكتوب كـ CSS Variables
□ طريقة التحميل محددة
□ للمشاريع العربية: خط عربي مناسب مختار
□ العميل وافق على الخطوط
