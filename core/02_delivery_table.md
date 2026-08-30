# 📦 جدول التسليم حسب المنصة (Delivery Table)

> هذا الجدول يحدد بالضبط ماذا يستلم العميل وكيف يطبقه على كل منصة.

---

## جدول التسليم الكامل

| المنصة | ماذا يستلم العميل | أين يضعه | ملف التفاصيل |
|---|---|---|---|
| 🌐 **WordPress** | CSS مركزي + HTML لكل قسم | CSS → Additional CSS / HTML → Custom HTML Block | `platforms/wordpress.md` |
| 🛍️ **Shopify** | تعديلات theme.liquid + sections + assets/theme.css | Shopify Theme Editor + Code Editor | `platforms/shopify.md` |
| ⚛️ **برمجة خاصة (React/Next)** | ملفات Components + Pages + globals.css | مباشرة في مجلدات المشروع | `platforms/custom_code.md` |
| 📱 **Mobile (RN/Flutter)** | Screens + Components + theme file | مباشرة في المشروع | `platforms/mobile_app.md` |
| 💻 **Web App / SaaS** | Design System + Pages + Layouts | مباشرة في المشروع | `platforms/web_app.md` |
| 🖥️ **Desktop App** | Components + theme + Window configs | مباشرة في المشروع | `platforms/desktop_app.md` |

---

## قواعد التسليم العامة (تنطبق على كل المنصات)

### ✅ الكود يجب أن يكون:
- **نظيفاً:** بدون كود غير مستخدم أو تعليقات زائدة
- **منظماً:** كل ملف له وظيفة واحدة واضحة
- **قابلاً للصيانة:** أسماء Variables و Classes واضحة ومنطقية
- **موثقاً:** تعليق قصير على كل Section رئيسي

### ✅ مع كل تسليم يجب إرفاق:
1. **تقرير التسليم:** ملخص ما تم بناؤه
2. **جدول الهوية المعتمدة:** ألوان + خطوط + مكتبات
3. **تعليمات التطبيق:** خطوات واضحة حسب المنصة
4. **قائمة الفحص النهائي:** مع الأدلة المقتبسة (Proof-by-Quote)

### ✅ ترتيب التسليم الإجباري:
```
1. Foundation File (CSS Variables / Theme) أولاً
2. Core Components ثانياً
3. Pages بالترتيب المتفق عليه
4. Animations أخيراً
5. تقرير التسليم النهائي
```

---

## ⚠️ تحذيرات حسب المنصة

| المنصة | تحذير مهم |
|---|---|
| **WordPress** | لا تعديل على ملفات الـ Theme مباشرة — كل التعديلات في Additional CSS |
| **Shopify** | لا تعديل على Dawn Theme Files مباشرة — استخدم Sections و Override فقط |
| **React/Next** | لا inline styles — كل شيء في CSS Modules أو globals.css |
| **Mobile** | لا hardcoded colors — كل الألوان من theme.ts فقط |
| **Desktop** | راعِ OS conventions (Windows vs macOS vs Linux) في كل شاشة |
