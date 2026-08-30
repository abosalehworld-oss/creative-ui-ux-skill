# ⚡ Performance Checklist — قائمة فحص الأداء الشاملة

> استخدم هذه القائمة في Gate B, C, D, والـ Final Gate.
> كل ❌ = يجب الإصلاح قبل التسليم.

---

## 🌐 الويب (Web Performance)

### HTML
```
□ Semantic HTML: header, main, section, article, aside, footer
□ لا div-soup — كل عنصر له معنى
□ lang attribute صحيح: <html lang="ar"> أو <html lang="en">
□ Meta viewport: <meta name="viewport" content="width=device-width, initial-scale=1">
□ Title + Meta Description موجودان
```

### CSS
```
□ لا CSS في <body> — كل CSS في <head>
□ Critical CSS inline للـ above-the-fold
□ لا @import في CSS الإنتاج (يبطئ التحميل)
□ CSS Variables بدلاً من تكرار القيم
□ لا !important إلا في حالات موثقة
□ Minified في البيئة الإنتاجية
```

### JavaScript
```
□ لا <script> في <head> بدون defer أو async
□ defer للسكريبتات غير الحرجة
□ async للسكريبتات المستقلة
□ لا jQuery — Vanilla JS كافٍ
□ لا مكتبات غير مستخدمة (Tree Shaking إجباري)
□ Bundle Size معقول (< 200KB للـ First Load)
□ Code Splitting للـ SPAs (React.lazy, dynamic imports)
```

### الصور
```
□ تنسيق WebP أو AVIF (لا JPG/PNG للمحتوى الجديد)
□ loading="lazy" لكل صورة خارج الـ Viewport الأول
□ width و height محددان (يمنع CLS)
□ alt text لكل صورة (وصف حقيقي لا "image1")
□ srcset للصور التجاوبية (مقاسات متعددة)
□ الصورة البطل (Hero): لا lazy loading — preload بدلاً
□ حجم الصورة مناسب للـ Container (لا 4K image لـ 300px container)
```

### الخطوط
```
□ preconnect قبل Google Fonts:
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
□ font-display: swap في @font-face
□ تحميل الأوزان المطلوبة فقط (لا تحمّل 9 أوزان تستخدم 3)
□ لا أكثر من خطين من مصدر خارجي
```

### الأنيميشن (Core Web Vitals)
```
□ animations تستخدم transform و opacity فقط (GPU)
□ لا animations على top, left, width, height, margin
□ will-change: transform على العناصر المتحركة فقط
□ requestAnimationFrame للـ JS animations
□ prefers-reduced-motion مُطبّق
□ لا CLS (Cumulative Layout Shift) > 0.1
```

---

## 📱 الموبايل (Mobile Performance)

```
□ Animations على UI Thread (Reanimated) لا JS Thread
□ FlatList: getItemLayout + keyExtractor + initialNumToRender
□ Images: FastImage أو مكتبة Caching
□ لا Anonymous functions في JSX (تسبب re-renders)
□ React.memo للـ Components الثقيلة
□ useMemo/useCallback للـ Heavy computations
□ InteractionManager.runAfterInteractions للـ Heavy tasks
□ Bundle Size: < 10MB للـ App الكامل
□ Startup Time: < 2s على أجهزة متوسطة
```

---

## 🖥️ الديسكتوب (Desktop Performance)

```
□ لا Main Thread blocking operations
□ Web Workers للـ Heavy computations (Electron/Tauri)
□ IPC calls أقل ما يمكن (Electron)
□ Lazy Load للـ Windows غير الأساسية
□ Memory Leaks: إلغاء Event Listeners عند unmount
□ High DPI: devicePixelRatio للـ Canvas elements
```

---

## ♿ الوصولية (Accessibility)

```
□ Contrast Ratio ≥ 4.5:1 للنص العادي (WCAG AA)
□ Contrast Ratio ≥ 3:1 للنص الكبير (18px+)
□ Contrast Ratio ≥ 3:1 للـ UI Components
□ :focus-visible واضح على كل العناصر التفاعلية
□ Keyboard Navigation كامل (Tab, Enter, Escape, Arrow Keys)
□ ARIA labels للـ Icons بدون نص
□ Role attributes صحيحة للـ Custom Components
□ Form Inputs: كل input له label مرتبط
□ Error Messages: واضحة ومحددة
□ لا إزالة outline بدون بديل: outline: none ممنوع بدون :focus-visible
```

---

## 🎯 معايير النجاح النهائية

```
Web Core Web Vitals (هدف):
  LCP (Largest Contentful Paint): < 2.5s
  FID (First Input Delay): < 100ms
  CLS (Cumulative Layout Shift): < 0.1
  TTFB (Time to First Byte): < 800ms

Mobile:
  App Size: < 10MB
  Startup: < 2s
  60fps في كل الـ Animations

Desktop:
  Launch Time: < 3s
  Memory: < 200MB في حالة الاستخدام العادي
  60fps في الـ UI
```
