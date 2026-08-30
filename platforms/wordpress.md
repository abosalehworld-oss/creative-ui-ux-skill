# 📝 WordPress Platform Guide

---

## طريقة التسليم
- **CSS المركزي** → Appearance → Customize → Additional CSS
- **HTML لكل صفحة** → Custom HTML Block في Gutenberg أو Elementor HTML Widget
- **JavaScript** → WPCode Plugin أو Functions.php (Header section)

---

## قواعد WordPress الصارمة

```
✅ كل التعديلات البصرية في Additional CSS فقط
✅ لا تعديل على ملفات الـ Theme مباشرة (Child Theme إذا لزم)
✅ CSS Variables في :root في Additional CSS
✅ JS خفيف فقط — لا مكتبات ضخمة تبطئ الموقع

❌ ممنوع تعديل style.css الأصلي للـ Theme
❌ ممنوع إضافة JS في <head> مباشرة
❌ ممنوع Plugins غير ضرورية للتصميم
```

---

## ترتيب التطبيق على WordPress

```
الخطوة 1: CSS المركزي (Foundation)
  → Appearance → Customize → Additional CSS
  → الصق كل CSS Variables + Typography + Spacing

الخطوة 2: خطوط Google Fonts
  → Appearance → Customize → Additional CSS
  → أضف @import في أول السطر
  → أو استخدم Plugin: Google Fonts Optimizer

الخطوة 3: JavaScript للأنيميشن
  → ثبّت WPCode Plugin
  → أضف الكود في: Header (Before </head>)
  → أو أضف في Footer (Before </body>)

الخطوة 4: HTML للصفحات
  → افتح الصفحة في Gutenberg
  → أضف Custom HTML Block
  → الصق الـ HTML Section بالـ Classes المعتمدة

الخطوة 5: اختبار
  → تحقق من الموبايل بـ Chrome DevTools
  → تحقق من تباين الألوان
  → تحقق من عدم وجود Horizontal Scroll
```

---

## هيكل CSS المُسلَّم لـ WordPress

```css
/* ==============================
   BRAND FOUNDATION
   ضعه أولاً في Additional CSS
   ============================== */

/* Google Fonts */
@import url('...');

/* CSS Variables */
:root {
  /* Colors */
  --primary: #______;
  --secondary: #______;
  --accent: #______;
  --background: #______;
  --surface: #______;
  --text-primary: #______;
  --text-secondary: #______;
  --border: #______;

  /* Typography */
  --font-display: 'Font Name', sans-serif;
  --font-body: 'Font Name', sans-serif;

  /* Spacing */
  --space-4: 1rem;
  --space-8: 2rem;
  /* ... */

  /* Radius */
  --radius-md: 0.5rem;
  --radius-lg: 0.75rem;

  /* Shadows */
  --shadow-md: 0 4px 6px -1px rgb(0 0 0 / 0.1);

  /* Transitions */
  --transition-normal: 300ms cubic-bezier(0.4, 0, 0.2, 1);
}

/* Reset لبعض WordPress defaults */
*, *::before, *::after { box-sizing: border-box; }
img { max-width: 100%; height: auto; }

/* ==============================
   COMPONENTS
   يأتي بعد Foundation
   ============================== */
/* ... كود المكونات هنا ... */
```

---

## ملاحظات خاصة بـ WordPress

```
⚠️ Gutenberg Specifics:
  • استخدم .wp-block-custom-html لـ Target المكونات
  • تجنب !important إلا عند الضرورة القصوى
  • بعض Themes تضيف specificity عالي — استخدم .entry-content .component

⚠️ WooCommerce (إذا وجد):
  • ملفي platform للتصميم منفصل تماماً
  • CSS المتجر يحتاج Override منفصل لـ WooCommerce defaults

⚠️ Page Builders:
  • Elementor: أضف CSS في Elementor → Site Settings → Custom CSS
  • Beaver Builder: Settings → Global CSS
  • لا تضع CSS في Widget Level — دائماً Global
```
