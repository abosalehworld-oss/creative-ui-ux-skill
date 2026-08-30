# ⚙️ Phase 3 — Design System (نظام التصميم)

---

## الهدف
بناء مكتبة المكونات الأساسية بناءً على الهوية المعتمدة في Gate A.
هذه المكونات هي اللبنات الأساسية لكل الصفحات والشاشات.

---

## الخطوة 1 — ملف الأساسيات (Foundation File)

```
الـ AI ← يبني أولاً ملف CSS/Theme مركزي يحتوي على:

1. استيراد الخطوط
2. CSS Variables (الألوان + الخطوط + المسافات + الظلال + الانتقالات)
3. CSS Reset بسيط
4. Base Typography Styles

⚠️ CSS Variables يجب أن تكون مطابقة 100% لجدول Gate A
⚠️ لا ألوان hardcoded خارج :root
⚠️ Dark Mode Variables إذا كان المشروع يدعمه
```

---

## الخطوة 2 — بناء المكونات (Core Components)

```
بناءً على:
  • المكتبة المعتمدة (Gate A) → اقرأ الوثائق التي قرأتها في Phase 1
  • الهوية البصرية (Gate A) → طبّق الألوان والخطوط المعتمدة

📋 المكونات الإجبارية (كحد أدنى):

1. Button
   • Variants: Primary, Secondary, Ghost, Outline, Destructive
   • Sizes: sm, md, lg
   • States: Default, Hover, Focus, Disabled, Loading
   • ⚠️ Hover: استخدم transform/scale/opacity فقط (لا Reflow)

2. Card
   • ⚠️ يجب لمسة فنية واحدة على الأقل:
     Glassmorphism / Soft Shadow / Gradient Border / Glow
   • Hover: lift effect (transform: translateY(-4px))

3. Input / TextField
   • States: Default, Focus, Error, Disabled
   • Focus: ring مميز يستخدم --accent color
   • Error: border + text + icon بلون --error

4. Navigation / Header
   • Desktop: Horizontal Nav
   • Mobile: Hamburger Menu أو Bottom Nav (حسب المشروع)

5. Footer

6. Badge / Tag
   • Variants: Default, Primary, Success, Warning, Error

7. Modal / Dialog (إذا كان المشروع يحتاجه)

اختيارية حسب نوع المشروع:
  • Alert / Toast Notification
  • Dropdown / Select
  • Checkbox / Radio / Switch
  • Avatar / User Profile
  • Skeleton Loading
```

---

## الخطوة 3 — Anti-Slop Component Rules

```
كل مكون يجب أن يجتاز هذه المعايير:

□ Hover Effect مميز (ليس مجرد تغيير لون)
  ✅ transform: translateY(-2px) + box-shadow
  ✅ background gradient يتكشف
  ✅ border يضيء (glow)
  ❌ مجرد opacity: 0.8

□ Padding سخي
  ✅ Buttons: padding: 0.75rem 1.5rem+ (لا 8px 16px)
  ✅ Cards: padding: 1.5rem+ (لا 12px)

□ Border Radius مناسب للـ Vibe
  فاخر: 2px-4px (Sharp)
  حديث: 8px-12px (Rounded)
  ودود: 16px-24px (Pill-ish)

□ Focus Visible للـ Accessibility
  :focus-visible { outline: 2px solid var(--accent); outline-offset: 2px }
```

---

## 🛑 HARD GATE B — بوابة نظام التصميم

⛔ الـ AI يعرض المكونات كـ Preview:
  • IDE يدعم Generative UI → ملف HTML تفاعلي
  • بيئة عادية → كود كامل مع وصف تفصيلي

📋 قائمة التحقق (مع الدليل المقتبس):
  □ الألوان من Gate A: "--primary: #______ ✓"
  □ الخطوط من Gate A: "font-family: '______' ✓"
  □ لا مكتبات من القائمة السوداء: "[اسم المكتبة] ✓"
  □ Hover Effects بدون Reflow: "transform only ✓"
  □ كل زر له Focus Visible: ":focus-visible ✓"
  □ كل Card لها لمسة فنية: "[اسم التأثير] ✓"
  □ Padding سخي على كل المكونات: "padding: Xrem ✓"

  للـ WordPress: العميل يضع CSS في Additional CSS ويؤكد أنه يعمل.
  للـ Mobile: العميل يشغّل المشروع ويؤكد.

⛔ فقط بعد "موافق" صريحة → انتقل لـ phase_4_pages.md
