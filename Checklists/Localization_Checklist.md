# 🌍 Localization Checklist

This checklist ensures your application provides a consistent, culturally appropriate experience across regions, languages, and formats. It's designed for manual testing of internationalization readiness and localization accuracy for both Web and Mobile platforms.

## 🗺 Regional Formats & Symbols

- [ ] Date formats adapt to locale (e.g. DD/MM/YYYY vs MM/DD/YYYY)  
- [ ] Time formats reflect 12h or 24h systems correctly  
- [ ] Currency formats match language and region (symbols, separators)  
- [ ] Number formats use appropriate decimal/thousand separators  
- [ ] Phone numbers follow local dialing conventions  
- [ ] Measurements reflect metric/imperial units where applicable

## 🗣 Language Accuracy & Consistency

- [ ] Translations are complete and grammatically correct  
- [ ] Placeholder variables render correctly in all languages  
- [ ] Automated translations are reviewed for clarity  
- [ ] Contextual wording matches platform tone and audience  
- [ ] In-app messages and notifications translate accurately  
- [ ] Errors and validation messages are culturally appropriate

## 🧩 Layout & UI Adaptability

- [ ] Translated strings do not overflow or break layout  
- [ ] UI components resize based on text expansion/contraction  
- [ ] Line spacing and alignment remain readable in all languages  
- [ ] Icons and symbols are meaningful across regions  
- [ ] Bidirectional text (e.g. Arabic, Hebrew) displays correctly  
- [ ] Fonts support special characters and diacritics

## 🌐 Navigation & Locale Switching

- [ ] Language switcher is visible and easy to use  
- [ ] Language preference persists across sessions  
- [ ] Correct language loads based on browser/device settings  
- [ ] URLs or routing reflect locale where needed  
- [ ] Pages don’t revert to default language unexpectedly

## 🛑 Localization Errors & Edge Cases

- [ ] Missing translations fall back gracefully  
- [ ] No untranslated "string placeholders" visible in UI  
- [ ] Variables and plural forms render correctly  
- [ ] Emojis or special characters display consistently  
- [ ] Formatting preserves logic when switching locales mid-session

---

> 🧠 Use this checklist during localization QA cycles, release readiness reviews, or multilingual audits. Combine with native language reviewers or tools like Crowdin, Lokalise, and pseudo-localization techniques to catch subtle issues.