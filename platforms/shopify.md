# 🛍️ Shopify Platform Guide

---

## طريقة التسليم
- **CSS** → `assets/theme.css` أو `assets/custom.css`
- **Sections** → `sections/` كملفات `.liquid` جديدة
- **Theme Settings** → `config/settings_schema.json`
- **Layout** → تعديل `layout/theme.liquid` بحذر شديد

---

## فهم هيكل Shopify قبل البناء

```
Shopify Theme Structure:
├── assets/          ← CSS, JS, Images, Fonts
├── config/
│   ├── settings_schema.json   ← إعدادات Theme Editor
│   └── settings_data.json     ← القيم الفعلية
├── layout/
│   └── theme.liquid           ← الهيكل الأساسي (تعديل بحذر!)
├── sections/        ← أقسام الصفحة (Section = Block قابل للتحريك)
├── snippets/        ← مكونات صغيرة قابلة للإعادة
├── templates/       ← قوالب الصفحات
└── locales/         ← النصوص والترجمات
```

---

## ⚠️ قبل أي تعديل
```
✅ اعمل نسخة: Online Store → Themes → ⋯ → Duplicate — وعدّل على النسخة، ثم Preview قبل Publish
✅ تعديل ملفات الثيم يمنع التحديث التلقائي للثيم من المتجر — أخبر العميل بذلك صراحةً
```

## قواعد Shopify الصارمة

```
✅ أضف CSS في assets/custom.css (ملف جديد منفصل)
✅ أضف <link> لـ custom.css في layout/theme.liquid
✅ بناء Sections جديدة في sections/ (لا تعديل على Sections الموجودة)
✅ استخدام Liquid variables للألوان والإعدادات
✅ اختبار في Shopify Theme Editor قبل التسليم

❌ ممنوع تعديل Dawn Core Files مباشرة
❌ ممنوع إضافة JS خارجي ثقيل (Shopify صارم في الأداء)
❌ ممنوع استخدام CDN خارجي للمكتبات (استخدم assets/ فقط)
```

---

## ترتيب التطبيق على Shopify

```
الخطوة 1: إنشاء ملف CSS مخصص
  → Online Store → Themes → Edit Code
  → assets/ → Add new file: custom.css
  → الصق Foundation CSS هنا

الخطوة 2: ربط CSS بالـ Theme
  → layout/theme.liquid
  → أضف قبل </head>:
  {{ 'custom.css' | asset_url | stylesheet_tag }}

الخطوة 3: الخطوط
  → الأفضل: مكتبة خطوط Shopify عبر إعدادات الثيم و filter `font_face` / `font_url`،
    أو رفع ملفات الخط إلى assets/ واستخدام @font-face (بدون CDN خارجي — يتوافق مع قاعدة "لا CDN خارجي" أدناه)

الخطوة 4: إنشاء Sections
  → sections/ → Add new file: custom-hero.liquid
  → بنية Section القياسية:
  <div class="custom-hero">
    <!-- المحتوى -->
  </div>

  {% schema %}
  { "name": "Custom Hero", "settings": [...] }
  {% endschema %}

الخطوة 5: إضافة Section للصفحة
  → Theme Editor → Add Section → اختر السيكشن الجديد

الخطوة 6: JavaScript
  → assets/ → Add: custom.js
  → layout/theme.liquid قبل </body>:
  <script src="{{ 'custom.js' | asset_url }}" defer></script>
```

---

## هيكل Section القياسي (Liquid)

```liquid
<!-- sections/custom-section.liquid -->
<div class="custom-section" style="
  background: {{ section.settings.background_color }};
  padding: {{ section.settings.padding }}px 0;
">
  <div class="container">
    <h2 class="custom-section__title">
      {{ section.settings.title | escape }}
    </h2>
    <div class="custom-section__content">
      {{ section.settings.content }}
    </div>
  </div>
</div>

{% schema %}
{
  "name": "Custom Section",
  "settings": [
    {
      "type": "text",
      "id": "title",
      "label": "Title",
      "default": "Section Title"
    },
    {
      "type": "richtext",
      "id": "content",
      "label": "Content"
    },
    {
      "type": "color",
      "id": "background_color",
      "label": "Background Color",
      "default": "#ffffff"
    },
    {
      "type": "range",
      "id": "padding",
      "label": "Padding (px)",
      "min": 20,
      "max": 120,
      "step": 10,
      "default": 60
    }
  ],
  "presets": [
    { "name": "Custom Section" }
  ]
}
{% endschema %}
```

---

## ملاحظات Shopify المهمة

```
⚠️ Metafields:
  لإضافة بيانات إضافية للمنتجات → استخدم Metafields
  لا Hardcode للبيانات في الـ Liquid

⚠️ Liquid Filters:
  {{ variable | escape }}    ← دائماً للنصوص الخارجية
  {{ variable | asset_url }} ← لملفات assets/
  {{ variable | img_url }}   ← للصور (مع أبعاد محددة)

⚠️ Performance:
  • لا تحمّل JS في <head> — دائماً defer
  • الصور: استخدم {{ image | img_url: '800x' }} لتحديد الحجم
  • لا تحمّل كل وزن الخط — فقط ما تحتاجه

⚠️ Theme Versions:
  تأكد دائماً من إصدار Dawn المستخدم قبل البناء
  Dawn 9.0+ له تغييرات جوهرية في البنية
```
