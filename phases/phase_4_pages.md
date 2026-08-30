# 📄 Phase 4 — Pages / Screens (بناء الصفحات والشاشات)

---

## الهدف
بناء كل صفحة/شاشة واحدة بعد الأخرى باستخدام المكونات من Gate B فقط.

---

## الخطوة 1 — خريطة الصفحات (Sitemap & UX Flow)

```
قبل بناء أي صفحة:

الـ AI ← يعرض على العميل قائمة الصفحات المقترحة حسب المشروع:

🌐 موقع ويب / WordPress / Shopify:
  □ الرئيسية (Home)
  □ صفحة المنتج / المقال
  □ المتجر / المدونة
  □ من نحن (About)
  □ تواصل معنا (Contact)
  □ [صفحات إضافية حسب المجال]

💻 Web App / SaaS:
  □ Landing Page
  □ Login / Register
  □ Dashboard (Home)
  □ Settings / Profile
  □ [صفحات الميزات الأساسية]

📱 Mobile App:
  □ Onboarding (2-3 شاشات)
  □ Login / Register
  □ Home Screen
  □ Profile Screen
  □ [شاشات الميزات]

🖥️ Desktop App:
  □ Main Window
  □ Settings Window
  □ [شاشات إضافية]

الـ AI ← يرسم User Flow بسيط:
  "المستخدم يدخل → يرى X → يضغط Y → ينتقل لـ Z"

⛔ العميل يوافق على قائمة الصفحات قبل البناء
```

---

## الخطوة 2 — بناء كل صفحة/شاشة

```
لكل صفحة/شاشة:

1. هيكل الأقسام (Sections):
   حدد الأقسام بالترتيب قبل كتابة الكود
   مثال للـ Home: Hero → Features → Testimonials → FAQ → CTA → Footer

2. المحتوى:
   • محتوى حقيقي (لا Lorem Ipsum)
   • مستوحى من مجال العميل الفعلي
   • نبرة تتناسب مع الشخصية المعتمدة من Phase 0

3. الكود:
   • استخدم المكونات من Gate B فقط
   • الألوان من Gate A (عبر CSS Variables)
   • الخطوط من Gate A

4. التجاوب (Responsive):
   Desktop → Tablet → Mobile
   لا Horizontal Overflow
   لا عناصر تتكسر على الموبايل

5. الأداء (Performance):
   • الصور: WebP + lazy loading + width + height
   • Critical CSS للـ above-the-fold
   • لا JS يعيق الـ rendering

Anti-Slop للصفحات:
  ❌ Hero = عنوان كبير + زر فقط
  ✅ Hero = عنصر بصري مميز يعكس روح المشروع
  ❌ كل الأقسام بنفس البنية البصرية
  ✅ كل قسم له طابع بصري مختلف (تنوع في التخطيط)
  ❌ مسافات ضيقة بين العناصر
  ✅ Whitespace سخي يمنح التنفس
```

---

## 🛑 HARD GATE C — بوابة كل صفحة/شاشة

⛔ **تتكرر لكل صفحة/شاشة على حدة.**
⛔ لا تبني الصفحة التالية قبل موافقة العميل على الحالية.

📋 قائمة التحقق مع الأدلة:
```
□ الهيكل يتبع قائمة الصفحات المتفق عليها
□ المكونات من Gate B فقط: "[اسم المكون] ✓"
□ الألوان من Gate A: "var(--primary) لا #3b82f6 ✓"
□ Desktop + Tablet + Mobile يعملون
□ لا Horizontal Overflow
□ المحتوى حقيقي وليس Lorem Ipsum
□ Hero section مميز: "[وصف العنصر المميز] ✓"
□ الصور: WebP + lazy + width + height
□ العميل قال "موافق" ← انتقل للصفحة التالية
```

**بعد اكتمال كل الصفحات → انتقل لـ phase_5_animations.md**
