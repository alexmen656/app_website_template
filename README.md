# App Website Template

A reusable website template for app landing pages. All content is driven by a single config file — no source code changes needed.

## Getting started

**Edit only the files in `config/` — everything else is source code and should not be touched.**

```
config/                  ← YOU EDIT THESE
  config.json            ← App name, links, texts, features, reviews, support articles, blog posts
  privacy-policy.html    ← Your privacy policy (plain HTML)
  terms-of-use.html      ← Your terms of use (plain HTML)

public/assets/           ← YOUR IMAGES
  logo.svg               ← App logo (used in header & footer)
  256.png                ← App icon
  iphone.png             ← Hero/feature screenshot(s)
  app_store.svg          ← Keep as-is or replace with your badge

src/                     ← DON'T TOUCH (source code)
public/
  favicon.ico            ← Replace with your favicon
```

### config.json — key fields

| Field                                                    | Description                        |
| -------------------------------------------------------- | ---------------------------------- |
| `appName`                                                | Displayed in header, footer, title |
| `headline` / `description`                               | Hero section text (HTML allowed)   |
| `iosLink` / `androidLink`                                | App Store / Google Play URLs       |
| `socialLinks`                                            | Instagram, X, TikTok, Facebook     |
| `feature_list`                                           | Feature cards on homepage          |
| `supportCategories`                                      | Support page structure & articles  |
| `blogView`                                               | Blog posts                         |
| `updatesView`                                            | Changelog / update entries         |
| `privacyPolicyEffectiveDate` / `termsOfUseEffectiveDate` | Shown on legal pages               |

## Credits

Parts of the site are inspired by following sites:
https://pasteapp.io
https://flighty.com

This template should help get you started developing with Vue 3 in Vite.

## Recommended IDE Setup

[VS Code](https://code.visualstudio.com/) + [Vue (Official)](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur).

## Recommended Browser Setup

- Chromium-based browsers (Chrome, Edge, Brave, etc.):
  - [Vue.js devtools](https://chromewebstore.google.com/detail/vuejs-devtools/nhdogjmejiglipccpnnnanhbledajbpd)
  - [Turn on Custom Object Formatter in Chrome DevTools](http://bit.ly/object-formatters)
- Firefox:
  - [Vue.js devtools](https://addons.mozilla.org/en-US/firefox/addon/vue-js-devtools/)
  - [Turn on Custom Object Formatter in Firefox DevTools](https://fxdx.dev/firefox-devtools-custom-object-formatters/)

## Type Support for `.vue` Imports in TS

TypeScript cannot handle type information for `.vue` imports by default, so we replace the `tsc` CLI with `vue-tsc` for type checking. In editors, we need [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) to make the TypeScript language service aware of `.vue` types.

## Customize configuration

See [Vite Configuration Reference](https://vite.dev/config/).

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Type-Check, Compile and Minify for Production

```sh
npm run build
```

### Lint with [ESLint](https://eslint.org/)

```sh
npm run lint
```
