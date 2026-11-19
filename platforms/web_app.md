# 💻 Web App Platform Guide
# (SaaS / Dashboard / Admin Panel)

---

## خصائص Web App عن الموقع العادي

```
الموقع العادي:         Web App (SaaS):
- Marketing pages      - Functional screens
- Content-focused      - Data-focused
- Visitors (Anonymous) - Users (Authenticated)
- SEO مهم             - Performance أهم
- Simple navigation    - Complex navigation (Sidebar, Tabs)
- Few interactions     - Heavy interactions (Forms, Tables, Modals)
```

---

## هيكل المشروع (Next.js SaaS)

```
src/
├── app/
│   ├── (marketing)/         ← Landing + Pricing + Blog
│   │   ├── page.tsx
│   │   └── layout.tsx
│   ├── (auth)/              ← Login + Register + Forgot Password
│   │   ├── login/
│   │   └── register/
│   └── (dashboard)/         ← Protected Routes
│       ├── layout.tsx        ← Sidebar + Header
│       ├── page.tsx          ← Dashboard Home
│       ├── settings/
│       └── [feature]/
├── components/
│   ├── ui/                  ← Base Components
│   ├── data/                ← Tables, Charts, Stats
│   ├── forms/               ← Form components + Validation
│   ├── feedback/            ← Toast, Alert, Modal, Dialog
│   └── navigation/          ← Sidebar, TopBar, Breadcrumb
└── styles/
    └── globals.css
```

---

## مكونات Web App الإضافية (فوق الـ Core Components)

```
إجبارية لأي Web App:
□ Sidebar Navigation (Collapsible)
□ Top Bar + User Menu
□ Data Table (Sort, Filter, Pagination)
□ Form Components (Select, Checkbox, Radio, Switch, DatePicker)
□ Modal / Dialog (Confirm, Form, Alert)
□ Toast Notifications (Success, Error, Warning, Info)
□ Loading States (Skeleton, Spinner, Progress Bar)
□ Empty States (No data, No results)
□ Error States (404, 500, Network error)
□ Breadcrumb Navigation
□ Pagination Component
□ Search Input + Results

اختيارية حسب المشروع:
□ Charts (Bar, Line, Pie, Donut)
□ Kanban Board
□ Calendar
□ File Upload (Drag & Drop)
□ Rich Text Editor
□ Code Editor
```

---

## UX Patterns خاصة بـ Web App

```
Navigation Pattern:
  • Sidebar مثبت (Sticky) للـ Desktop
  • Bottom Navigation للـ Mobile
  • Breadcrumb لكل الصفحات الداخلية

Forms Pattern:
  • Inline Validation (لا تنتظر Submit)
  • Success/Error states واضحة لكل Field
  • لا Form يزيد عن 7 حقول في شاشة واحدة
  • Multi-step للـ Forms الطويلة

Data Pattern:
  • Loading Skeleton بدلاً من Spinner للـ Tables
  • Optimistic Updates للـ UX السلس
  • Empty State مفيد ومحفز (لا "No data found" فقط)

Feedback Pattern:
  • Toast للأحداث السريعة (Saved, Deleted)
  • Modal للقرارات المهمة (Confirm Delete)
  • Inline Error للـ Forms
  • Banner للإشعارات المستمرة
```

---

## قواعد أداء Web App

```
⚠️ Web Apps تحتاج أداءً خاصاً:
  • Code Splitting إجباري (لا تحمّل كل شيء مرة واحدة)
  • React.lazy() + Suspense لكل صفحة Dashboard
  • Virtual Lists للـ Tables الكبيرة (react-virtual)
  • Debounce لـ Search Inputs (300ms)
  • Throttle لـ Scroll Events
  • Memoization للـ Heavy Components (React.memo, useMemo)

⚠️ Charts:
  • قارن الأحجام بقياس فعلي (bundlephobia / build output) — لا تكتب أرقاماً من الذاكرة
  • تجنب D3.js إلا إذا كانت Charts معقدة جداً
  • Lazy Load الـ Charts خارج الـ Viewport

⚠️ Tables:
  • Pagination إجبارية (لا تحمّل 1000 صف دفعة واحدة)
  • Virtual Scrolling لـ Tables كبيرة جداً
```

---

## Auth & Security UI

```
✅ Login Form:
  • Email + Password (بدون Username)
  • "Remember me" Checkbox
  • "Forgot Password" Link
  • Show/Hide Password Toggle
  • Loading State على Submit Button

✅ Error Messages:
  • "Invalid credentials" (لا تقل أيهما خاطئ لأسباب أمنية)
  • Rate Limiting Message عند المحاولات الكثيرة
  • Session Expired Toast

✅ Onboarding:
  • Progress Indicator للـ Multi-step
  • Skip Option للخطوات الاختيارية
  • محتوى "Getting Started" في أول Dashboard
```
