# 📅 Freshness Registry — Facts That Expire

> **Purpose:** AI models confidently repeat outdated facts. This registry lists facts used by this
> skill that change over time, with the date they were last checked by the maintainer.
>
> **Last maintainer review:** 2026-11-19
>
> **How to use (mandatory):**
> 1. Compute `age = review date − "As of"` (see Agent Integrity Protocol §2 for the review date).
> 2. If age > 6 months, or the row says **VERIFY**, re-check it with a live web search against the
>    **official source** before relying on it, and cite the URL + access date in your report.
> 3. If live search is unavailable, use the row but label it `⚠️ UNVERIFIED — as of <date>`.
> 4. If you discover a row is wrong, tell the user and suggest updating this file.

---

## 🧭 Standards & Security Taxonomies

| Fact | Value (as of) | Official source to verify |
|------|---------------|---------------------------|
| OWASP Top 10 (web) | 2021 edition long-standing; **2025 edition published** — use the newest final edition (2025-11, VERIFY final status) | owasp.org/Top10 |
| OWASP API Security Top 10 | 2023 edition is current (2026-11) | owasp.org/API-Security |
| OWASP Mobile Top 10 | 2024 final edition (M1 Improper Credential Usage … M10 Insufficient Cryptography) (2026-11) | owasp.org/www-project-mobile-top-10 |
| OWASP Top 10 for LLM / GenAI Apps | 2025 edition (LLM01 Prompt Injection …) (2026-11, VERIFY newer) | genai.owasp.org |
| OWASP MASVS / MASTG | MASVS v2.x — use for mobile verification levels (2026-11) | mas.owasp.org |
| WCAG | **2.2** is the current W3C Recommendation (Oct 2023); WCAG 3 is still a draft (2026-11) | w3.org/TR/WCAG22 |
| CVSS | **v4.0** is current (Nov 2023); many feeds still show v3.1 — state which (2026-11) | first.org/cvss |
| CISA KEV | Known Exploited Vulnerabilities catalog — prioritize KEV-listed CVEs (living list) | cisa.gov/known-exploited-vulnerabilities-catalog |
| European Accessibility Act | Applies to many consumer products/services since **2025-06-28** (2026-11) | ec.europa.eu (EAA) |
| EU Cyber Resilience Act | In force; vulnerability-reporting obligations from **2026-09-11**, full application 2027-12-11 (2026-11, VERIFY) | digital-strategy.ec.europa.eu |
| NIST Post-Quantum | FIPS 203/204/205 (ML-KEM, ML-DSA, SLH-DSA) final since 2024-08 (2026-11) | csrc.nist.gov |

## 🌐 Web Platform

| Fact | Value (as of) | Source |
|------|---------------|--------|
| Core Web Vitals | **LCP ≤ 2.5s, INP ≤ 200ms, CLS ≤ 0.1** (75th percentile). **FID was retired 2024-03-12** — never report FID (2026-11) | web.dev/vitals |
| Lighthouse PWA category | **Removed in Lighthouse 12 (2024)** — do not ask for a "Lighthouse PWA audit"; check manifest/SW manually (2026-11) | developer.chrome.com |
| X-XSS-Protection | Deprecated; recommended value `0` or omit; rely on CSP (2026-11) | MDN |
| Third-party cookies (Chrome) | Google abandoned full deprecation plans (2024–2025); still design for SameSite + partitioned cookies (CHIPS) (2026-11, VERIFY) | privacysandbox.com |
| Social cards | X (Twitter) still reads `twitter:*` meta tags; Open Graph `og:image` 1200×630 recommended (2026-11) | developer.x.com, ogp.me |

## 📱 Mobile Stores & Platforms

| Fact | Value (as of) | Source |
|------|---------------|--------|
| Google Play target API | New apps & updates had to target **API 35 (Android 15)** from 2025-08-31; the yearly bump to **API 36 (Android 16)** is expected for 2026-08-31 — VERIFY the current deadline | support.google.com/googleplay/android-developer (target API requirements) |
| Google Play 16 KB page size | Apps targeting Android 15+ with native code must support **16 KB memory pages** (enforced for new apps/updates from 2025-11-01) (2026-11, VERIFY) | developer.android.com/guide/practices/page-sizes |
| Android 16 behavior | Edge-to-edge opt-out removed when targeting API 36; orientation/resizability restrictions ignored on large screens (≥600dp) (2026-11) | developer.android.com/about/versions/16 |
| Google Play billing (US) | Post *Epic v. Google* changes allow alternative billing/external links in the US under conditions (late 2025) — region-specific, VERIFY | support.google.com/googleplay/android-developer |
| Apple SDK requirement | Uploads must be built with the **latest required Xcode/SDK** (Apple announced Xcode 26 / iOS 26 SDK requirement from **April 2026**) — VERIFY | developer.apple.com/news/upcoming-requirements |
| Apple privacy manifest | `PrivacyInfo.xcprivacy` + Required Reason API declarations required since 2024-05 (2026-11) | developer.apple.com |
| Apple Bitcode | **Deprecated in Xcode 14 (2022); App Store no longer accepts bitcode.** Never recommend enabling it (2026-11) | Xcode 14 release notes |
| Apple external purchase links | US storefront allows external purchase links after the **2025-04-30** court ruling; EU has DMA-specific rules; elsewhere IAP rules apply — region-specific, VERIFY | developer.apple.com/app-store/review/guidelines |
| Apple design language | iOS/iPadOS/macOS 26 introduced **Liquid Glass** (2025-06) (2026-11) | developer.apple.com/design |
| Material Design | Material 3 + **Material 3 Expressive** (2025) (2026-11) | m3.material.io |
| CocoaPods | Trunk announced to become **read-only (planned Dec 2026)** — prefer Swift Package Manager for new deps (VERIFY) | blog.cocoapods.org |
| React Native | New Architecture is the default since RN 0.76 (2024-10); CLI flag is `--mode release` (not `--variant`) (2026-11) | reactnative.dev |

## 🖥️ Desktop

| Fact | Value (as of) | Source |
|------|---------------|--------|
| Windows 10 | End of support **2025-10-14**; consumer ESU through 2026-10-13 — test on Windows 11 first (2026-11) | learn.microsoft.com/lifecycle |
| Code-signing certificates | Private keys must live on HSM/hardware tokens (since 2023-06); CA/B Forum reduced max code-signing cert validity to **460 days** (from 2026-03) — VERIFY | cabforum.org |
| Windows SmartScreen | EV certificates no longer bypass SmartScreen reputation instantly (since 2024) — reputation builds over time; consider Azure Artifact/Trusted Signing (VERIFY name/availability) | learn.microsoft.com |
| macOS distribution | Outside the App Store requires Developer ID signing + **notarization** (`notarytool`; `altool` retired 2023-11) (2026-11) | developer.apple.com/documentation/security/notarizing |
| Electron support | Only the **latest 3 major versions** receive security fixes — check the app's Electron version against that window (2026-11) | electronjs.org/docs/latest/tutorial/electron-timelines |

## 🛠️ Security Tool Syntax (commands change between releases)

| Tool | Current syntax (as of 2026-11) | Outdated syntax to avoid |
|------|-------------------------------|--------------------------|
| Nuclei v3 | `nuclei -ut` (update templates); templates live under `http/cves/`, `http/exposures/`, `http/misconfiguration/`, `http/vulnerabilities/`, `http/default-logins/` | `-update-templates` (old alias), bare `cves/` paths |
| Trivy | `trivy fs --scanners vuln,secret,misconfig <dir>`; `trivy image …`; `trivy config …` | `--security-checks` (removed) |
| testssl.sh | `git clone --depth 1 https://github.com/testssl/testssl.sh.git` | `drwetter/testssl.sh` (moved) |
| OWASP ZAP | Docker `ghcr.io/zaproxy/zaproxy:stable`; `zap-baseline.py` (passive) vs `zap-full-scan.py` (ACTIVE — needs RoE) | `owasp/zap2docker-*` images (retired) |
| Safety (Python) | `safety scan` (3.x, needs account) or prefer `pip-audit` | `safety check` (deprecated) |
| kube-hunter | **Unmaintained/archived** — use `trivy k8s`, `kube-bench`, `kubescape` | kube-hunter |
| OSV-Scanner | `osv-scanner scan source -r <dir>` — multi-ecosystem (npm, pub, Gradle, CocoaPods, Go, Cargo, PyPI…) | — |
| MobSF | Run locally via Docker `opensecurity/mobile-security-framework-mobsf`; REST API needs header `Authorization: <API_KEY>` (shown at startup) | `pip install mobsf` (not a supported install path) |
| mobsfscan | `pip install mobsfscan` → `mobsfscan <src-dir>` (static source scan, no upload) | — |
| Sentry Node SDK (v8+) | `Sentry.init` in `instrument.js` loaded first (`node --import ./instrument.mjs`); Express: `Sentry.setupExpressErrorHandler(app)` | `Sentry.Handlers.errorHandler()` (removed in v8) |
| Sentry SvelteKit | `@sentry/sveltekit` (wizard: `npx @sentry/wizard@latest -i sveltekit`) | `@sentry/svelte` for SvelteKit |
| Sentry versions | **Never hardcode a version** — install via package manager to get the latest, or read the current version from the official docs | `sentry:latest`, `^8.0.0`, `7.0.0` pinned in docs |

## 🎨 Front-End Libraries (for UI work)

| Fact | Value (as of) | Source |
|------|---------------|--------|
| Framer Motion | Renamed **Motion** — package `motion`, import from `motion/react` (2024-11) | motion.dev |
| Motion One (`@motionone/dom`) | Deprecated — merged into `motion` | motion.dev |
| AOS (Animate On Scroll) | Effectively unmaintained (no major release since 2018) — prefer IntersectionObserver / CSS scroll-driven animations | github.com/michalsnik/aos |
| NextUI | Renamed **HeroUI** (2025-01) | heroui.com |
| React 19 | `ref` is a regular prop for function components; `forwardRef` no longer needed for new code (2024-12) | react.dev |
| Tailwind CSS | v4 (2025-01): CSS-first config (`@theme`), no `tailwind.config.js` required | tailwindcss.com |
| CSS scroll-driven animations | `animation-timeline: view()/scroll()` supported in Chromium & Safari 26; Firefox behind flag — VERIFY, provide fallback | caniuse.com |
| Google Fonts & GDPR | Loading fonts from Google's CDN transmits visitor IPs; a German court fined this (LG München 2022) — prefer self-hosting for EU audiences | — |

---

### Changelog of this registry
- 2026-11-19 — Initial registry created during the 2026 hardening pass.
