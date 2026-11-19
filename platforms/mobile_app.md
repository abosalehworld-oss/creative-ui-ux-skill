# 📱 Mobile App Platform Guide
# (React Native / Flutter)

---

## طريقة التسليم
الـ AI يكتب مباشرة في ملفات المشروع.
كل الألوان والخطوط من ملف Theme مركزي واحد.

---

## React Native — هيكل المشروع

```
src/
├── theme/
│   ├── index.ts          ← Theme exports (الملف الرئيسي)
│   ├── colors.ts         ← Color tokens
│   ├── typography.ts     ← Font families, sizes, weights
│   ├── spacing.ts        ← Spacing scale
│   └── shadows.ts        ← Shadow definitions
├── components/
│   ├── ui/               ← Button, Card, Input, Badge...
│   └── layout/           ← Header, BottomTab, SafeArea...
├── screens/              ← الشاشات الكاملة
│   ├── Home/
│   ├── Auth/
│   └── [ScreenName]/
├── navigation/           ← React Navigation setup
└── assets/
    └── fonts/            ← Self-hosted fonts
```

---

## React Native — ملف Theme

```typescript
// src/theme/colors.ts
export const colors = {
  primary: {
    100: '#______',
    500: '#______',  // الأساسي
    900: '#______',
  },
  secondary: {
    100: '#______',
    500: '#______',
    900: '#______',
  },
  accent: '#______',

  background: {
    light: '#______',
    dark: '#______',
  },
  surface: {
    light: '#______',
    dark: '#______',
  },
  text: {
    primary: '#______',
    secondary: '#______',
    disabled: '#______',
  },
  border: '#______',
  success: '#______',
  warning: '#______',
  error: '#______',
} as const

// src/theme/typography.ts
import { Platform } from 'react-native'

export const typography = {
  fontFamily: {
    display: Platform.select({
      ios: 'FontName-Bold',
      android: 'FontName-Bold',
    }),
    body: Platform.select({
      ios: 'FontName-Regular',
      android: 'FontName-Regular',
    }),
  },
  fontSize: {
    xs:   12,
    sm:   14,
    base: 16,
    lg:   18,
    xl:   20,
    '2xl': 24,
    '3xl': 30,
    '4xl': 36,
    '5xl': 48,
  },
  lineHeight: {
    tight:  1.25,
    normal: 1.5,
    relaxed: 1.75,
  },
} as const

// src/theme/spacing.ts
export const spacing = {
  1:  4,
  2:  8,
  3:  12,
  4:  16,
  5:  20,
  6:  24,
  8:  32,
  10: 40,
  12: 48,
  16: 64,
  20: 80,
} as const

// src/theme/index.ts
export * from './colors'
export * from './typography'
export * from './spacing'
```

---

## Flutter — هيكل المشروع

```
lib/
├── core/
│   └── theme/
│       ├── app_theme.dart      ← ThemeData الرئيسي
│       ├── app_colors.dart     ← Color constants
│       ├── app_typography.dart ← TextTheme
│       └── app_spacing.dart    ← Spacing constants
├── features/                   ← Feature-based architecture
│   └── [feature]/
│       ├── presentation/
│       │   ├── screens/
│       │   └── widgets/
│       └── ...
└── shared/
    └── widgets/               ← Shared UI Components
```

---

## قواعد Mobile الصارمة

```
✅ كل الألوان من theme/colors.ts فقط
✅ كل الأبعاد مضروبة في 1 (لا px hardcoded)
✅ Responsive: استخدم useWindowDimensions() (يتحدث مع الدوران وتقسيم الشاشة) بدلاً من Dimensions.get
✅ Accessibility: هدف لمس ≥ 44×44pt (iOS) و ≥ 48×48dp (Android)
✅ Safe Areas: استخدم SafeAreaView دائماً

❌ ممنوع hardcoded colors في Screens أو Components
❌ ممنوع hardcoded font sizes (استخدم typography scale)
❌ ممنوع animations تستهلك battery (60fps max)
```

---

## Animations في Mobile

```typescript
// React Native — Reanimated مفضل على Animated API
import Animated, {
  useSharedValue,
  useAnimatedStyle,
  withTiming,
  withSpring,
  Easing,
} from 'react-native-reanimated'

// ✅ Entrance Animation
const opacity = useSharedValue(0)
const translateY = useSharedValue(20)

const animatedStyle = useAnimatedStyle(() => ({
  opacity: opacity.value,
  transform: [{ translateY: translateY.value }],
}))

// Trigger:
opacity.value = withTiming(1, { duration: 400 })
translateY.value = withTiming(0, { duration: 400 })

// ⚠️ قواعد الأداء:
// - لا Animations على Lists كبيرة
// - استخدم useNativeDriver: true دائماً (Animated API)
// - Reanimated يعمل على UI Thread → أسرع بكثير
```

---

## OS-Specific Considerations

```
iOS:
  • Haptic Feedback للـ Buttons المهمة
  • Bottom Sheet بدلاً من Dialog
  • Large Title في Navigation (iOS 11+)
  • iOS 26+: Liquid Glass للتنقل وأشرطة التبويب — لا تغطِّ عناصر النظام بخلفيات مصمتة مخصصة دون سبب
  • Safe Area: Top (notch) + Bottom (home indicator)

Android:
  • Material You / Material 3 Expressive (Dynamic Color من Android 12+)
  • Edge-to-edge إجباري عند استهداف API 35+ — صمّم خلف شريط الحالة والتنقل
  • Ripple Effect على Touchables
  • Back Button behavior
  • Status Bar color يجب أن يتطابق مع Header
```
