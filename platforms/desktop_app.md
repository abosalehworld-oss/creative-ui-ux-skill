# 🖥️ Desktop App Platform Guide
# (Electron / Tauri / Flutter Desktop / .NET MAUI)

---

## الفرق الجوهري عن Web & Mobile

```
Web/Mobile:              Desktop:
- Browser viewport       - Native window (resizable)
- Touch/Click            - Keyboard-first + Mouse precision
- Limited OS access      - Full OS access
- No system tray         - System Tray / Menu Bar
- Simple window          - Multi-window possible
- Browser handles chrome - You handle title bar, window controls
```

---

## Frameworks المدعومة

### Electron (JavaScript/TypeScript)
```
المميزات: ويب تقنيات مباشرة، مجتمع ضخم
العيوب: حجم كبير (80-150MB)، RAM أعلى
الأفضل لـ: Apps معقدة، تكامل ويب مطلوب
```

### Tauri (Rust + Web Frontend)
```
المميزات: خفيف جداً (3-10MB)، أسرع، أكثر أماناً
العيوب: يتطلب Rust، بعض Web APIs غير متوفرة
الأفضل لـ: Apps التي تحتاج أداء وحجم صغير
```

### Flutter Desktop
```
المميزات: نفس كود Mobile، أداء ممتاز
العيوب: Widgets لا تبدو Native دائماً
الأفضل لـ: عندك Flutter Mobile App وتريد Desktop
```

---

## Window & Layout Patterns

```
التخطيطات الشائعة للـ Desktop:

1. Three-Pane Layout (مثل VS Code, Finder):
   [Sidebar] | [Main Content] | [Detail Panel]

2. Two-Pane Layout (مثل Mail, Notes):
   [List] | [Detail View]

3. Single Window (مثل Calculator, Media Players):
   [Single View]

4. MDI - Multiple Document Interface (مثل Photoshop):
   [Tabs أو Floating Windows]
```

---

## OS Conventions (مهم جداً)

```
Windows:
  • Title bar: أعلى اليسار → Icon + Title
  • Window controls: أعلى اليمين → Min, Max, Close
  • Right-click Context Menu
  • System Tray (bottom right)
  • Accent color من Windows settings
  • Mica/Acrylic material (Windows 11)

macOS:
  • Traffic lights: أعلى اليسار → Close, Minimize, Zoom
  • Menu Bar App (بدل System Tray)
  • Vibrancy/Translucency effects
  • Native-looking Sidebars (NSTableView style)
  • Trackpad gestures support

Linux:
  • متنوع حسب Desktop Environment
  • التزم بـ Design Minimal يعمل على الكل
  • GTK/Qt conventions حسب التطبيق
```

---

## قواعد Desktop UI الصارمة

```
✅ Keyboard Shortcuts إجبارية:
  • Ctrl/Cmd + S → Save
  • Ctrl/Cmd + Z → Undo
  • Ctrl/Cmd + Shift + Z → Redo
  • Ctrl/Cmd + W → Close
  • F11 / Ctrl+Cmd+F → Fullscreen
  • Escape → Cancel/Close Modal

✅ Window Management:
  • حافظ على الـ Window Size بين الجلسات
  • حافظ على الـ Window Position بين الجلسات
  • Minimum window size محدد (لا تكسر الـ Layout)

✅ Performance Desktop:
  • No blocking the main thread (استخدم Web Workers / Isolates)
  • تذكر: Desktop يمكن أن يكون على شاشات 4K
  • Scale UI properly للـ High DPI displays

❌ ممنوع:
  • لا تتجاهل OS Dark Mode — اتبعه تلقائياً
  • لا تعطّل Keyboard navigation
  • لا تفرض حجم نافذة ثابت (Resizable دائماً)
```

---

## Electron — هيكل المشروع

```
src/
├── main/               ← Main Process (Node.js)
│   ├── index.ts        ← App entry point
│   ├── window.ts       ← BrowserWindow setup
│   └── ipc/            ← IPC handlers
├── renderer/           ← Renderer Process (React/Vue/HTML)
│   ├── components/
│   ├── screens/
│   └── styles/
│       └── globals.css ← نفس CSS Variables كالعادة
└── preload/            ← Preload scripts (Bridge)
```

---

## Tauri — هيكل المشروع

```
src/                    ← Frontend (React/Vue/HTML)
│   ├── components/
│   ├── screens/
│   └── styles/
src-tauri/              ← Rust Backend
│   ├── src/
│   │   └── main.rs
│   └── tauri.conf.json ← App config (window size, permissions)
```

---

## Custom Title Bar (Electron/Tauri)

```css
/* Custom Title Bar للـ Frameless Window */
.title-bar {
  height: 32px; /* Windows: 32px | macOS: 28px */
  background: var(--surface);
  display: flex;
  align-items: center;
  padding: 0 var(--space-3);
  -webkit-app-region: drag; /* يسمح بسحب النافذة */
  user-select: none;
}

.title-bar__controls {
  -webkit-app-region: no-drag; /* الأزرار لا تسحب */
  margin-left: auto;
  display: flex;
  gap: var(--space-1);
}
```
