# ✨ Phase 5 — Animations & Motion (الحركة والأنيميشن)

---

## الهدف
إضافة الحياة للتصميم الثابت — بذكاء وخفة دون تثقيل أو إزعاج.

---

## الخطوة 1 — قرار الأنيميشن (To Animate or Not?)

```
قبل أي أنيميشن، اسأل نفسك:
  1. هل يضيف قيمة للمستخدم؟
  2. هل المشروع يحتمله (Creative Portfolio vs. Corporate)?
  3. هل حجم المكتبة مبرر بما تضيفه؟

✅ CSS يكفي إذا:
  • Hover effects بسيطة
  • Fade-in/slide-up للعناصر
  • الأداء أولوية قصوى
  • أجهزة ضعيفة في الجمهور المستهدف

✅ مكتبة مبررة إذا:
  • Timeline animations معقدة
  • Scroll-scrubbing (parallax تقدمي)
  • Page transitions سلسة
  • المشروع Creative/Portfolio حيث الجماليات أساسية
```

---

## الخطوة 2 — اختيار مكتبة الأنيميشن (بالبحث الحي)

```
الـ AI ← يبحث أولاً (لا من الذاكرة):
  search_web: "lightweight animation library web 2025 2026"
  search_web: "scroll animation no dependency vanilla js"

📊 الخيارات من الأخف للأثقل:

| الأداة | الحجم | الاستخدام |
|---|---|---|
| CSS @keyframes + Intersection Observer | 0KB ← الأفضل دائماً | Fade, Slide, Scale |
| Web Animations API (Native) | 0KB | Animation التحكم بـ JS |
| AOS (Animate on Scroll) | 6KB | Scroll animations سريعة |
| @motionone/dom | 15KB | Animations متقدمة بـ API بسيط |
| Framer Motion | 45KB | React فقط — Gestures + Layout |
| GSAP Core | 27KB | Timeline + ScrollTrigger معقد |

⚠️ GSAP: استخدم Core فقط — لا Plugins إلا إذا لزم
⚠️ Framer Motion: React/Next فقط
⚠️ لـ WordPress: AOS أو Vanilla JS فقط (خفيف)
⚠️ لـ Mobile: React Native Reanimated أو Flutter Animations النيتيف
```

---

## الخطوة 3 — تطبيق الأنيميشن

```
📋 أنواع الحركة حسب الأولوية:

1. Hover Micro-interactions (CSS دائماً):
   .btn:hover { transform: translateY(-2px); box-shadow: ...; }
   .card:hover { transform: translateY(-4px) scale(1.01); }

2. Entrance Animations (عند دخول العنصر للـ Viewport):
   • Fade-in + Slide-up للعناصر
   • Staggered للقوائم (كل عنصر بتأخير 100ms)

3. Scroll-triggered (عند التمرير):
   • Parallax للخلفيات والصور
   • Counter animation للأرقام
   • Progress bars

4. Page/Screen Transitions:
   • Smooth fade بين الصفحات
   • Slide للـ Mobile Navigation

5. Loading States:
   • Skeleton screens (لا Spinners للـ Content)
   • Pulse animation للـ Skeleton

قواعد الأداء الصارمة:
  ✅ استخدم فقط: transform, opacity (GPU-accelerated)
  ❌ ممنوع في animations: top, left, width, height, margin, padding
  ✅ Duration المثالي: 200ms-600ms
  ✅ Easing: cubic-bezier مخصص
     fast-out: cubic-bezier(0.4, 0, 1, 1)
     ease-in-out: cubic-bezier(0.4, 0, 0.2, 1)
     spring: cubic-bezier(0.34, 1.56, 0.64, 1)
  ✅ إجباري:
     @media (prefers-reduced-motion: reduce) {
       *, *::before, *::after {
         animation-duration: 0.01ms !important;
         transition-duration: 0.01ms !important;
       }
     }
```

---

## الخطوة 4 — التسليم حسب المنصة

```
WordPress:
  → كود JS يوضع في WPCode Plugin
  → أو في Footer via Appearance → Theme Editor → footer.php
  → أو Custom Plugin بسيط

برمجة خاصة:
  → مدمج مباشرة في Components

Mobile (React Native):
  → React Native Reanimated
  → لا Animated API القديم — Reanimated أسرع بكثير

Mobile (Flutter):
  → AnimatedWidget أو AnimationController
  → TweenAnimationBuilder للبساطة

Desktop:
  → CSS Transitions للـ Electron/Tauri (Web frontend)
  → Flutter Animations للـ Flutter Desktop
```

---

## 🛑 HARD GATE D — بوابة الأنيميشن

📋 قائمة التحقق:
```
□ الأنيميشن ناعم (60fps) — لا تقطيع
□ يستخدم transform/opacity فقط: "لا top/left/width في animations ✓"
□ Duration بين 200-600ms: "___ms ✓"
□ prefers-reduced-motion مُطبّق: "✓"
□ لا أنيميشن مبالغ يشتت الانتباه
□ يعمل على الموبايل بدون مشاكل
□ Bundle size مبررة: "___KB ✓"
□ WordPress: كود خفيف ولا يبطئ الموقع
□ العميل وافق → انتقل لـ phase_6_final.md
```
