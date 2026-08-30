# 🎨 Phase 3 — Color System (نظام الألوان)

---

## الهدف
بناء نظام ألوان كامل ومتسق يعمل على كل المنصات — ليس مجرد اختيار لون عشوائي.

---

## الخطوة 1 — البحث عن ألوان (Live Color Research)

```
الـ AI ← يبحث عن ألوان تناسب مجال العميل وشخصيته:
  search_web: "[مجال العميل] color palette 2025 2026"
  search_web: "[الكلمات المفتاحية] brand color psychology"

الـ AI ← يدرس علم نفس الألوان في السياق:
  • الأزرق: ثقة، احترافية، تقنية
  • الأخضر: طبيعة، صحة، نمو
  • الأحمر: طاقة، إلحاح، شغف
  • الذهبي/البيج: فخامة، راقٍ، كلاسيك
  • الأسود: قوة، رقي، بساطة

⚠️ الألوان يجب أن تعكس مجال العميل الفعلي — ليس ذوق الـ AI
```

---

## الخطوة 2 — بناء الـ Palette

### هيكل الـ Palette الإجباري (6 ألوان + تدرجات)

```
Primary (اللون الأساسي):
  • الدور: CTA, Buttons, Links, Highlights
  • عدد التدرجات: 9 (100 → 900)
  • HEX: #______

Secondary (الثانوي):
  • الدور: Sections backgrounds, Badges, Tags
  • عدد التدرجات: 5 (100 → 900)
  • HEX: #______

Accent (التمييز):
  • الدور: Hover states, Focus rings, Special elements
  • HEX: #______

Background (الخلفية):
  • Light mode: #______
  • Dark mode: #______

Surface (سطح المكونات):
  • Light mode: #______ (Cards, Inputs, Modals)
  • Dark mode: #______

Text:
  • Primary text: #______
  • Secondary text (muted): #______
  • Disabled: #______

Semantic Colors:
  • Success: #______ (green family)
  • Warning: #______ (amber family)
  • Error: #______ (red family)
  • Info: #______ (blue family)
```

---

## الخطوة 3 — التحقق من التباين (Contrast Verification)

⚠️ **إجباري** — لا ألوان بدون فحص التباين:

```
الـ AI ← يتحقق من:
  • نص على Primary color: ≥ 4.5:1 (WCAG AA)
  • نص رئيسي على Background: ≥ 7:1 (WCAG AAA مفضل)
  • نص ثانوي على Background: ≥ 4.5:1 (WCAG AA)
  • نص على Surface: ≥ 4.5:1

طريقة الحساب:
  نسبة التباين = (L1 + 0.05) / (L2 + 0.05)
  حيث L1 = اللون الأفتح، L2 = الأغمق

إذا فشل أي لون → غيّره حتى ينجح
```

---

## الخطوة 4 — CSS Variables

```css
/* Light Mode */
:root {
  /* Primary */
  --primary-100: #_____;
  --primary-500: #_____;  /* الأساسي */
  --primary-900: #_____;

  /* Secondary */
  --secondary-100: #_____;
  --secondary-500: #_____;
  --secondary-900: #_____;

  /* Accent */
  --accent: #_____;

  /* Surfaces */
  --background: #_____;
  --surface: #_____;
  --surface-raised: #_____;

  /* Text */
  --text-primary: #_____;
  --text-secondary: #_____;
  --text-disabled: #_____;

  /* Borders */
  --border: #_____;
  --border-focus: var(--primary-500);

  /* Semantic */
  --success: #_____;
  --warning: #_____;
  --error: #_____;
  --info: #_____;
}

/* Dark Mode */
@media (prefers-color-scheme: dark) {
  :root {
    --background: #_____;
    --surface: #_____;
    --text-primary: #_____;
    --text-secondary: #_____;
    --border: #_____;
  }
}
```

---

## 🛑 GATE — بوابة الألوان

⛔ لا تنتقل لـ Phase 4 قبل:
□ الـ Palette الكامل محدد بـ HEX Codes
□ كل الألوان اجتازت فحص التباين (≥ 4.5:1)
□ Dark Mode محدد
□ CSS Variables مكتوبة
□ العميل وافق على الألوان
