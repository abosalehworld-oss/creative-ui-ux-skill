# 🔄 RTL Layout Guide — دليل التخطيط من اليمين لليسار

> هذا الدليل إجباري لأي مشروع عربي أو يدعم اللغة العربية.
> الـ AI يقرأه تلقائياً عندما تكون لغة المشروع عربية.

---

## القواعد الأساسية

### 1. HTML Direction

```html
<!-- مشروع عربي بالكامل -->
<html lang="ar" dir="rtl">

<!-- مشروع ثنائي اللغة -->
<html lang="ar" dir="rtl">
  <!-- محتوى إنجليزي داخل صفحة عربية -->
  <p dir="ltr">This is English text inside an Arabic page</p>
```

---

### 2. CSS Logical Properties (الطريقة الحديثة)

```css
/* ❌ القديم — يتكسر مع RTL */
.card {
  margin-left: 1rem;
  padding-right: 2rem;
  text-align: left;
  float: left;
}

/* ✅ الحديث — يعمل مع LTR و RTL تلقائياً */
.card {
  margin-inline-start: 1rem;
  padding-inline-end: 2rem;
  text-align: start;
  float: inline-start;
}

/* ✅ Logical Properties الشائعة */
/*
  margin-left    → margin-inline-start
  margin-right   → margin-inline-end
  padding-left   → padding-inline-start
  padding-right  → padding-inline-end
  text-align: left  → text-align: start
  text-align: right → text-align: end
  left: 0        → inset-inline-start: 0
  right: 0       → inset-inline-end: 0
  border-left    → border-inline-start
  border-right   → border-inline-end
*/
```

---

### 3. Flexbox و Grid في RTL

```css
/* Flexbox يعكس تلقائياً مع dir="rtl" */
.nav {
  display: flex;
  gap: var(--space-4);
  /* لا تحتاج flex-direction: row-reverse في RTL */
  /* المتصفح يعكسها تلقائياً عندما dir="rtl" */
}

/* ⚠️ الاستثناء — إذا أردت ترتيباً ثابتاً بغض النظر عن الاتجاه */
.ltr-always {
  direction: ltr; /* يبقى من اليسار لليمين دائماً */
}
```

---

### 4. الأيقونات في RTL

```css
/* أيقونات تحتاج انعكاس في RTL */
.icon-arrow,
.icon-chevron,
.icon-back,
.icon-forward,
.icon-reply,
.icon-redo,
.icon-undo,
.icon-external-link,
.icon-logout {
  [dir="rtl"] & {
    transform: scaleX(-1);
  }
}

/* ❌ أيقونات لا تُعكس أبداً */
/* علامة الصح ✓، X، القلب، النجمة، الساعة */
/* الأرقام، أيقونات السوشيال ميديا */
```

---

### 5. الأرقام في المحتوى العربي

```css
/* العربي يستخدم الأرقام الهندية أو العربية */

/* إجبار الأرقام العربية (0-9) */
.price, .stats, .phone {
  font-feature-settings: "tnum";
  direction: ltr; /* الأرقام وأرقام الهاتف دائماً LTR */
  unicode-bidi: embed;
}

/* مثال: رقم الهاتف */
/* ✅ +966 50 123 4567 */
/* ❌ 4567 123 50 966+ (لو ما حطيت direction: ltr) */
```

---

### 6. Scrollbar في RTL

```css
/* Scrollbar يكون على اليسار في RTL تلقائياً */
/* لكن بعض المتصفحات القديمة تحتاج: */
html[dir="rtl"] {
  scrollbar-gutter: stable;
}
```

---

### 7. قائمة التحقق للمشاريع العربية

```
□ <html dir="rtl" lang="ar"> في كل صفحة
□ CSS Logical Properties بدلاً من left/right
□ الأيقونات الاتجاهية معكوسة (arrows, chevrons)
□ أرقام الهاتف والأسعار: direction: ltr
□ خط عربي من brand-identity/phase_4_typography.md
□ المحتوى العربي مقروء وطبيعي (ليس مترجم بـ Google)
□ التجاوب يعمل: Desktop + Tablet + Mobile
□ لا كسر في التخطيط عند خلط عربي وإنجليزي
□ Form placeholders بالعربي
□ Error messages بالعربي
□ Breadcrumb معكوس (الرئيسية > القسم > الصفحة)
```

---

### 8. WordPress RTL

```css
/* WordPress يحتوي على rtl.css تلقائياً */
/* لكن Additional CSS الخاص بك يجب أن يراعي RTL */

/* استخدم body.rtl كـ selector */
body.rtl .custom-component {
  text-align: right;
}

/* أو الأفضل: Logical Properties تعمل في الاتجاهين */
```

### 9. Shopify RTL

```liquid
<!-- في theme.liquid -->
<html lang="{{ request.locale.iso_code }}"
      dir="{{ request.locale.iso_code | slice: 0, 2 | replace: 'ar', 'rtl' | replace: 'he', 'rtl' | default: 'ltr' }}">
```

### 10. React / Next.js RTL

```tsx
// app/layout.tsx
export default function RootLayout({ children, params }) {
  const isRTL = params.locale === 'ar'
  return (
    <html lang={params.locale} dir={isRTL ? 'rtl' : 'ltr'}>
      <body>{children}</body>
    </html>
  )
}
```
