# ⚛️ Custom Code Platform Guide
# (React / Next.js / Vue / HTML+CSS+JS)

---

## طريقة التسليم
الـ AI يكتب مباشرة في ملفات المشروع في الـ IDE.
لا نسخ ولصق — كل شيء يُبنى في مكانه الصحيح.

---

## هيكل المشروع المقترح

### React / Next.js
```
src/
├── app/                    ← Next.js App Router
│   ├── layout.tsx          ← Root Layout
│   ├── page.tsx            ← Home Page
│   └── [pages]/
├── components/
│   ├── ui/                 ← Core UI Components (Button, Card, Input...)
│   ├── layout/             ← Header, Footer, Navigation
│   └── sections/           ← Page Sections (Hero, Features, CTA...)
├── styles/
│   ├── globals.css         ← CSS Variables + Reset + Typography
│   └── components.css      ← Component-specific styles (إذا لم Tailwind)
├── lib/
│   └── utils.ts            ← Utility functions
└── public/
    ├── fonts/              ← Self-hosted fonts (اختياري)
    └── images/
```

### HTML + CSS + JS (بدون Framework)
```
project/
├── index.html
├── css/
│   ├── variables.css       ← CSS Variables فقط
│   ├── reset.css           ← CSS Reset
│   ├── typography.css      ← Type styles
│   ├── components.css      ← Reusable components
│   └── pages/
│       ├── home.css
│       └── [page].css
├── js/
│   ├── main.js             ← Initialization
│   ├── animations.js       ← Animation logic
│   └── utils.js            ← Helper functions
└── assets/
    ├── fonts/
    └── images/
```

---

## قواعد برمجة خاصة

```
✅ CSS Variables في :root في globals.css
✅ Component-first architecture
✅ لا inline styles إلا للـ dynamic values
✅ لا !important إلا في حالات استثنائية موثقة
✅ Semantic HTML (header, main, section, article, aside, footer)
✅ All images: alt text + width + height + loading="lazy"

❌ ممنوع hardcoded colors في Components (استخدم Variables)
❌ ممنوع تكرار الكود — استخدم Components قابلة للإعادة
❌ ممنوع JS في <head> بدون defer أو async
```

---

## ترتيب البناء

```
الخطوة 1: globals.css
  → CSS Variables (ألوان + خطوط + مسافات + ظلال)
  → CSS Reset
  → Base Typography styles

الخطوة 2: Core UI Components
  → components/ui/Button.tsx
  → components/ui/Card.tsx
  → components/ui/Input.tsx
  → components/ui/Badge.tsx

الخطوة 3: Layout Components
  → components/layout/Header.tsx
  → components/layout/Footer.tsx
  → components/layout/Navigation.tsx

الخطوة 4: Page Sections
  → components/sections/Hero.tsx
  → components/sections/Features.tsx
  → components/sections/[etc].tsx

الخطوة 5: Pages (تجميع السيكشنات)
  → app/page.tsx
  → app/[page]/page.tsx

الخطوة 6: Animations
  → إضافة motion/animations لكل Component
```

---

## تثبيت المكتبات (npm)

```bash
# الـ AI ينفذ هذه الأوامر مباشرة في Terminal

# مثال مع Next.js
npx create-next-app@latest project-name --typescript --tailwind --app

# تثبيت مكتبة UI (بعد اكتشافها من البحث)
npm install [library-name]

# تثبيت مكتبة أنيميشن
npm install motion        # (Framer Motion سابقاً) — import { motion } from "motion/react"
# أو
npm install gsap
# أو (الأخف)
# (لا تستخدم @motionone/dom — أُدمج في motion) — الأخف: CSS + IntersectionObserver
```

---

## Component Template القياسي

```tsx
// components/ui/Button.tsx
// React 19+: ref is a normal prop — forwardRef is not needed for new code (React 18: keep forwardRef)
import { type ButtonHTMLAttributes, forwardRef } from 'react'

interface ButtonProps extends ButtonHTMLAttributes<HTMLButtonElement> {
  variant?: 'primary' | 'secondary' | 'ghost' | 'outline'
  size?: 'sm' | 'md' | 'lg'
}

export const Button = forwardRef<HTMLButtonElement, ButtonProps>(
  ({ variant = 'primary', size = 'md', className, children, ...props }, ref) => {
    return (
      <button
        ref={ref}
        className={`btn btn--${variant} btn--${size} ${className ?? ''}`}
        {...props}
      >
        {children}
      </button>
    )
  }
)
Button.displayName = 'Button'
```

```css
/* في globals.css */
.btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  font-family: var(--font-body);
  font-weight: var(--font-semibold);
  border-radius: var(--radius-md);
  transition: all var(--transition-normal);
  cursor: pointer;
  border: none;
}

.btn--primary {
  background: var(--primary);
  color: white;
}

.btn--primary:hover {
  transform: translateY(-2px);
  box-shadow: var(--shadow-lg);
}

/* No Layout Reflow — only transform & opacity */
```
