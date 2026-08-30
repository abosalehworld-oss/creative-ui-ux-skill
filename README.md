<div align="center">

# 🎨 Creative UI/UX Designer Skill
### Anti-Slop Edition — Bilingual (Arabic / English)

**An AI skill that fights generic design by forcing live research, strict gates, and performance-first thinking.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Works With: Any AI Agent](https://img.shields.io/badge/Works%20With-Any%20AI%20Agent-blue)]()
[![Language: Bilingual](https://img.shields.io/badge/Language-Arabic%20%2B%20English-green)]()
[![Platforms: 6](https://img.shields.io/badge/Platforms-6%20Supported-purple)]()

</div>

---

<div dir="rtl">

## 🇸🇦 بالعربية

### المشكلة التي تحلها هذه المهارة

كل مرة تطلب من الذكاء الاصطناعي تصميم موقع، يُنتج لك:
- تصميم Bootstrap مكرر رآه الجميع ألف مرة
- ألوان Tailwind افتراضية (blue-500, gray-200)
- خطوط مستهلكة (Roboto، Open Sans، Arial)
- Hero Section = "عنوان كبير + زر"
- مكتبات ثقيلة تُبطئ الموقع

**هذه المهارة تمنعه من كل ذلك.**

### كيف تعمل؟

بدلاً من الاعتماد على الذاكرة المحفوظة، المهارة تُجبر الـ AI على:

1. **البحث الحي** في GitHub والويب عن مكتبات حديثة وإلهام حقيقي
2. **البوابات الصارمة (Hard Gates)** — لا يكمل خطوة إلا بعد موافقتك
3. **قواعد الأداء** — لا مكتبة ثقيلة، لا Render-blocking، لا Layout Reflow
4. **مكتشف اللغة التلقائي** — يرد عربي أو إنجليزي حسب لغتك

### ما يدعمه
| المنصة | التفاصيل |
|---|---|
| 🌐 موقع ويب | React / Next.js / HTML+CSS+JS |
| 📝 WordPress | Additional CSS + Gutenberg |
| 🛍️ Shopify | Liquid + Sections + Dawn Theme |
| 📱 موبايل | React Native / Flutter |
| 💻 ويب أبلكيشن | SaaS / Dashboard / Admin Panel |
| 🖥️ ديسكتوب | Electron / Tauri / Flutter Desktop |

### الأوضاع الثلاثة

```
🎨 Mode C — هوية بصرية ولوجو فقط
🆕 Mode A — مشروع جديد من الصفر
🔍 Mode B — تقييم وتحسين مشروع موجود
```

### كيف تستخدمها؟

#### الطريقة 1 — نسخ الملف مباشرة
```
1. حمّل SKILL.md من هذا الريبو
2. اقرأه في بداية أي محادثة مع الـ AI
3. قل للـ AI: "اقرأ هذا الملف وطبّق تعليماته"
```

#### الطريقة 2 — Clone كامل
```bash
git clone https://github.com/abosalehworld-oss/creative-ui-ux-skill.git
```
ضع المجلد في مسار Skills الخاص بـ IDE — الـ AI يكتشفها تلقائياً.

#### الطريقة 3 — عبر Skills CLI
```bash
npx skills add abosalehworld-oss/creative-ui-ux-skill
```

### المتطلبات
- ✅ أي AI Agent يدعم Web Search وقراءة URLs
- ✅ لا مسارات ثابتة — يعمل على أي جهاز
- ✅ لا أدوات مدفوعة — كل المصادر مجانية

---

### 💬 كيف تتعامل مع المهارة؟ — محادثة حقيقية خطوة بخطوة

> **اللي بالخط العريض = أنت** | اللي بعده = الـ AI

---

#### 🆕 مثال 1 — مشروع جديد (Mode A)

**أنت:** `استخدم مهارة Creative UI Designer — عايز أعمل موقع لمتجر عطور فاخر`

**AI:** سيسألك:
```
نوع المشروع؟ (WordPress / Shopify / React...)
الجمهور المستهدف؟
هل عندك لوجو وألوان موجودة؟
مواقع تعجبك كمرجع؟
```

**أنت:** `Shopify — جمهور سيدات 25-45 — مفيش لوجو — يعجبني موقع byredo.com`

**AI:** سيبحث حياً في GitHub عن مكتبات UI حديثة ويعرض عليك:
```
وجدت 3 مكتبات مناسبة:
1. Magic UI (⭐ 12K) — تأثيرات بصرية فاخرة
2. Aceternity UI (⭐ 8K) — أنيميشن سينمائي
3. Park UI (⭐ 3K) — خفيف وأنيق
أيها تفضل؟
```

**أنت:** `Magic UI`

**AI:** سيقترح 3 هويات بصرية مختلفة مع ألوان وخطوط وبعدها **ينتظر موافقتك** (Gate A) قبل أي كود.

وهكذا في كل مرحلة — **الـ AI لا يكمل إلا بعد "موافق" منك.**

---

#### 🔍 مثال 2 — تقييم موقع موجود (Mode B)

**أنت:** `استخدم مهارة Creative UI Designer — Mode B — قيّم موقعي https://example.com`

**AI:** سيقرأ الكود ويرجعلك تقرير:
```
🔴 مشاكل حرجة:
  • JS يُحمَّل في <head> بدون defer — يبطئ الصفحة
  • الصور بصيغة JPG بدون lazy loading

🟡 مشاكل متوسطة:
  • خطوط بدون font-display: swap

✅ ما يعمل جيداً:
  • التصميم متجاوب على الموبايل

خطة الإصلاح المقترحة بالأولوية... هل توافق؟
```

**أنت:** `نعم ابدأ بالمشاكل الحرجة`

**AI:** يعطيك الكود المصحح مع شرح الأثر المتوقع — وينتظر تأكيدك بعد كل إصلاح.

---

#### 🎨 مثال 3 — هوية بصرية فقط (Mode C)

**أنت:** `استخدم مهارة Creative UI Designer — Mode C — محتاج لوجو لشركة تقنية اسمها NexaFlow`

**AI:** سيسألك 10 أسئلة سريعة عن الشخصية والجمهور والمنافسين، ثم:
```
اقترح 3 مفاهيم مختلفة:
1. Lettermark "NF" — حروف هندسية حادة
2. Abstract Mark — شكل يوحي بالتدفق
3. Wordmark — اسم بخط تقني مميز
أيها يعجبك؟
```

**أنت:** `رقم 2`

**AI:** يولد لك SVG كامل + 7 تنويعات (فاتح/داكن/أيقونة) + دليل الهوية كاملاً.

---

> **⚡ القاعدة الذهبية:** الـ AI يسأل ← أنت تجيب ← هو ينفذ ← أنت توافق ← ينتقل للخطوة التالية.
> **لا كود يُكتب بدون موافقتك الصريحة.**

</div>

---

## 🇬🇧 In English

### The Problem This Skill Solves

Every time you ask an AI to design a website, it gives you:
- A Bootstrap clone everyone's seen a thousand times
- Default Tailwind colors (blue-500, gray-200)
- Overused fonts (Roboto, Open Sans, Arial)
- Hero Section = big headline + button
- Heavy libraries that slow your site down

**This skill prevents all of that.**

### How It Works

Instead of relying on memorized training data, this skill forces the AI to:

1. **Live Research** on GitHub and the web for modern libraries and real inspiration
2. **Hard Gates** — it cannot proceed without your explicit approval at each stage
3. **Performance-First Rules** — no heavy libraries, no render-blocking, no layout reflow
4. **Bilingual Auto-Detect** — responds in Arabic or English based on your language

### Supported Platforms
| Platform | Details |
|---|---|
| 🌐 Custom Website | React / Next.js / HTML+CSS+JS |
| 📝 WordPress | Additional CSS + Gutenberg Blocks |
| 🛍️ Shopify | Liquid Sections + Dawn Theme |
| 📱 Mobile App | React Native / Flutter |
| 💻 Web App | SaaS / Dashboard / Admin Panel |
| 🖥️ Desktop App | Electron / Tauri / Flutter Desktop |

### Three Modes

```
🎨 Mode C — Brand Identity & Logo only
🆕 Mode A — New project from scratch
🔍 Mode B — Audit & improve existing project
```

### How to Use

#### Method 1 — Copy the file directly
```
1. Download SKILL.md from this repo
2. Read it at the start of any AI conversation
3. Tell the AI: "Read this file and follow its instructions"
```

#### Method 2 — Clone the full repo
```bash
git clone https://github.com/abosalehworld-oss/creative-ui-ux-skill.git
```
Place the folder in your IDE's Skills directory — the AI auto-discovers it.

#### Method 3 — Via Skills CLI
```bash
npx skills add abosalehworld-oss/creative-ui-ux-skill
```

### Requirements
- ✅ Any AI Agent that supports Web Search and URL reading
- ✅ No hardcoded paths — works on any machine
- ✅ No paid tools — all sources are free and open-source

---

### 💬 How to Interact — Real Conversation Walkthrough

> **Bold = You** | Regular = What the AI does

---

#### 🆕 Example 1 — New Project (Mode A)

**You:** `Use the Creative UI Designer skill — I want to build a website for a luxury perfume brand`

**AI:** Will ask you:
```
What's your platform? (WordPress / Shopify / React / Mobile...)
Who's your target audience?
Do you have an existing logo or colors?
Any websites you like as visual references?
```

**You:** `Shopify — women aged 25-45 — no logo yet — I love byredo.com`

**AI:** Searches GitHub live and presents:
```
Found 3 suitable libraries:
1. Magic UI (⭐ 12K) — stunning visual effects
2. Aceternity UI (⭐ 8K) — cinematic animations
3. Park UI (⭐ 3K) — lightweight and elegant
Which do you prefer?
```

**You:** `Magic UI`

**AI:** Proposes 3 completely different visual identities with colors, fonts, and a signature element — then **waits for your approval (Gate A) before writing a single line of code.**

This continues at every stage — **the AI never moves forward without your explicit "approved".**

---

#### 🔍 Example 2 — Audit Existing Project (Mode B)

**You:** `Use the Creative UI Designer skill — Mode B — audit my site https://example.com`

**AI:** Reads the code and returns a report:
```
🔴 Critical Issues:
  • JS loaded in <head> without defer — blocking page render
  • Images using JPG with no lazy loading

🟡 Medium Issues:
  • Fonts missing font-display: swap

✅ What's Working Well (we won't touch this):
  • Mobile responsiveness is solid

Proposed fix plan in priority order... Do you approve?
```

**You:** `Yes, start with the critical issues`

**AI:** Gives you the fixed code with expected impact explained — and waits for your confirmation after each fix.

---

#### 🎨 Example 3 — Brand Identity Only (Mode C)

**You:** `Use the Creative UI Designer skill — Mode C — I need a logo for a tech company called NexaFlow`

**AI:** Asks 10 quick questions about personality, audience, and competitors, then:
```
Here are 3 completely different concepts:
1. Lettermark "NF" — sharp geometric letters
2. Abstract Mark — a shape suggesting flow and motion
3. Wordmark — the name in a distinctive tech typeface
Which direction speaks to you?
```

**You:** `Number 2`

**AI:** Generates a complete SVG + 7 variations (light/dark/icon-only) + a full Brand Guide document.

---

> **⚡ Golden Rule:** AI asks → You answer → AI executes → You approve → AI moves on.
> **No code is written without your explicit approval.**

---

## 📁 Repository Structure

```
creative-ui-ux-skill/
│
├── SKILL.md                              ← Master Index — Start here
├── README.md                             ← This file
│
├── core/
│   ├── 00_critical_rules.md             ← 8 Critical Rules (Anti-Slop + Performance + Bilingual)
│   ├── 01_mode_selection.md             ← Mode selection + setup questions
│   └── 02_delivery_table.md             ← Delivery per platform
│
├── brand-identity/
│   ├── phase_1_brand_discovery.md       ← Brand personality questionnaire
│   ├── phase_2_logo_concepts.md         ← 3 logo concepts + SVG generation
│   ├── phase_3_color_system.md          ← Full color palette + contrast check
│   ├── phase_4_typography.md            ← Font pairing + type scale
│   └── phase_5_brand_guide.md           ← Complete brand kit
│
├── platforms/
│   ├── wordpress.md                     ← WordPress delivery guide
│   ├── shopify.md                       ← Shopify Liquid + Sections guide
│   ├── custom_code.md                   ← React/Next.js/HTML guide
│   ├── mobile_app.md                    ← React Native + Flutter guide
│   ├── web_app.md                       ← SaaS/Dashboard patterns
│   └── desktop_app.md                   ← Electron/Tauri/Flutter Desktop
│
├── phases/
│   ├── phase_audit.md                   ← Audit existing projects (Mode B)
│   ├── phase_0_setup.md                 ← Project setup questionnaire
│   ├── phase_1_research.md              ← Live research strategy
│   ├── phase_2_identity.md              ← Visual identity + Gate A
│   ├── phase_3_design_system.md         ← Core components + Gate B
│   ├── phase_4_pages.md                 ← Page/screen construction + Gate C
│   ├── phase_5_animations.md            ← Motion + performance + Gate D
│   └── phase_6_final.md                 ← Final audit + delivery package
│
└── references/
    ├── banned_libraries.md              ← The blacklist
    ├── approved_fonts.md                ← Curated font list (EN + AR)
    ├── performance_checklist.md         ← Complete performance checklist
    ├── rtl_layout.md                    ← RTL layout guide (Arabic projects)
    └── free_assets.md                   ← Free photos, icons, illustrations
```

---

## 🚪 The Gate System

| Gate | What's Checked | Who Approves |
|---|---|---|
| **Gate 0** | Mode + Project Type + Platform | Client answers |
| **Gate A** | Visual Identity (colors, fonts, library, signature) | Client approves |
| **Gate B** | Design System (components + preview) | Client approves |
| **Gate C** | Every page/screen individually | Client approves |
| **Gate D** | Animations (performance + smoothness) | Client approves |
| **Final** | Complete audit + delivery package | Client approves |

---

## 🚨 The 8 Critical Rules

| # | Rule | What It Does |
|---|---|---|
| 1 | Anti-Memory | No memorized libraries or colors — live search only |
| 2 | Banned Libraries | Bootstrap, MUI, Ant Design forbidden by default |
| 3 | No Skipping | Every gate requires explicit approval before continuing |
| 4 | Mandatory Re-Read | Re-reads skill file every 15 messages |
| 5 | Proof-by-Quote | Every checklist item requires quoted code evidence |
| 6 | Universal & Portable | No hardcoded paths, no external dependencies |
| 7 | Performance-First | No heavy code, protect Core Web Vitals |
| 8 | Bilingual Auto-Detect | Responds in user's language automatically |

---

## 📄 License

MIT License — free for personal and commercial use.
Fork it, modify it, make it yours.

---

<div align="center">

**Made with ❤️ for designers and developers who refuse to settle for mediocre AI output.**

*If this saved you time, give it a ⭐ — it helps others find it.*

</div>

---

## 👤 Author / المؤلف

<div align="center">

**Mohamed Saleh**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/mr-mohamed-saleh/)

*For collaboration, questions, or consulting — reach out on LinkedIn.*
*للتواصل والاستشارات والتعاون — تواصل عبر LinkedIn.*

</div>

---

## ©️ Copyright / حقوق الملكية

```
© 2026 Mohamed Saleh — All Rights Reserved
https://www.linkedin.com/in/mr-mohamed-saleh/
```

هذا العمل محمي بموجب رخصة MIT.
يُسمح باستخدامه وتعديله وتوزيعه **مع الإبقاء على اسم المؤلف الأصلي في كل نسخة مشتقة.**

This work is licensed under the MIT License.
You may use, modify, and distribute it **provided the original author's name is retained in all derivative works.**


