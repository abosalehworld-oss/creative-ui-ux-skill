# 🚫 Banned Libraries — القائمة السوداء الكاملة

> هذه المكتبات ممنوع استخدامها كمكوّن رئيسي للتصميم.
> السبب: كثرة الاستخدام → تصاميم مكررة → AI Slop.

---

## ❌ CSS Frameworks المحظورة

| المكتبة | السبب |
|---|---|
| Bootstrap (v4, v5) | أكثر framework مستخدم في العالم = أكثر تصميم مكرر |
| Foundation | نفس مشكلة Bootstrap |
| Bulma | واجهات متطابقة وممّلة |
| Skeleton CSS | قديم جداً |
| Materialize CSS | Material Design مكرر |

---

## ❌ UI Component Libraries المحظورة (بالإعدادات الافتراضية)

| المكتبة | السبب | هل يُسمح بتعديل؟ |
|---|---|---|
| Material UI / MUI | Google Material Style = مكرر | فقط مع تخصيص كامل للـ Theme |
| Ant Design | Enterprise look مكرر | فقط مع تخصيص كامل |
| Chakra UI (default) | نمط موحد جداً | فقط مع تخصيص كامل |
| Semantic UI | قديم ومكرر | لا |
| Blueprint.js | Enterprise مكرر | لا |
| Mantine (default colors) | ألوان افتراضية واضحة | مع تخصيص ألوان كاملة |

---

## ❌ JavaScript Libraries المحظورة

| المكتبة | البديل المفضل |
|---|---|
| jQuery | Vanilla JS |
| Lodash (كاملة) | Native JS (map, filter, reduce) أو Lodash-es مع Tree Shaking |
| Moment.js | Day.js (2KB) أو date-fns |
| Underscore.js | Vanilla JS |
| Prototype.js | Vanilla JS |

---

## ❌ CSS Animation Libraries المحظورة (بالإعدادات الافتراضية)

| المكتبة | السبب | البديل |
|---|---|---|
| Animate.css (default) | تأثيرات مكررة جداً | CSS custom @keyframes |
| Hover.css | تأثيرات قديمة ومستهلكة | CSS custom |
| Magic CSS | مبالغة في التأثيرات | استخدمها بتقنين شديد |

---

## ✅ ماذا نستخدم بدلاً؟

```
البحث الحي في GitHub عن:
  • مكتبات حديثة (2024-2026)
  • نجوم GitHub: > 500
  • آخر تحديث: < سنة
  • حجم مناسب للمشروع

أمثلة لما يُكتشف عادةً:
  • Aceternity UI — تأثيرات بصرية مبهرة
  • Magic UI — React components حديثة
  • Shadcn/ui — قابل للتخصيص 100%
  • Park UI — Radix + Tailwind
  • NextUI v2 — شكل حديث
  • Tamagui — Cross-platform
  ... وغيرها مما يظهر في البحث الحي

ملاحظة: هذه القائمة ستشيخ — ابحث دائماً عن الأحدث
```

---

## ⚠️ استثناءات مسموح بها

```
يُسمح باستخدام المكتبات المحظورة فقط إذا:
1. طلب العميل صراحةً مكتبة معينة بالاسم
2. المشروع لديه قيود تقنية تمنع البدائل
3. تم تخصيص المكتبة تخصيصاً كاملاً بحيث لا تشبه الإعدادات الافتراضية

في هذه الحالة: وثّق الاستثناء في تقرير التسليم.
```
