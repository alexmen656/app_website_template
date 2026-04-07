# App Website Template

A reusable website template for app landing pages. All content is driven by a single config file — no source code changes needed.

## Getting started

**Edit only the files in `config/` — everything else is source code and should not be touched.**

```
config/                  ← YOU EDIT THESE
  config.json            ← App name, links, texts, features, reviews, support articles, blog posts
  privacy-policy.html    ← Your privacy policy (plain HTML)
  terms-of-use.html      ← Your terms of use (plain HTML)

public/assets/           ← YOUR IMAGES (replace these)
  logo.svg               ← App logo (used in header & footer)
  256.png                ← App icon
  iphone.png             ← iPhone mockup / app screenshot(s)

public/assets/branding/  ← INTERNAL (don't touch)
  app_store.svg          ← App Store download badge
  google_play.svg        ← Google Play download badge

src/                     ← DON'T TOUCH (source code)
public/
  favicon.ico            ← Replace with your favicon
```

### config.json — complete field reference

All website content is controlled by `config/config.json`. Fields that accept HTML are marked with "(HTML)".

#### Global / Branding

| Field              | Type   | Description                                                               |
| ------------------ | ------ | ------------------------------------------------------------------------- |
| `appName`          | string | App name displayed in header, footer, page title, and throughout the site |
| `appIcon`          | string | Filename of the app icon in `public/assets/` (e.g. `"256.png"`)           |
| `copyrightCompany` | string | Company name shown in the footer copyright line                           |

#### Hero Section (Homepage top)

| Field           | Type          | Description                                                 |
| --------------- | ------------- | ----------------------------------------------------------- |
| `headline`      | string (HTML) | Large hero title. Use `<br />` for line breaks              |
| `description`   | string (HTML) | Subtitle text below the headline                            |
| `ctaButtonText` | string        | Label on the main call-to-action button (e.g. `"Download"`) |

#### Links & Store URLs

| Field            | Type   | Description                                                                                                            |
| ---------------- | ------ | ---------------------------------------------------------------------------------------------------------------------- |
| `iosLink`        | string | URL for the iOS App Store listing                                                                                      |
| `androidLink`    | string | URL for the Google Play Store listing                                                                                  |
| `appStoreLink`   | string | App Store badge link (download section)                                                                                |
| `googlePlayLink` | string | Google Play badge link (download section)                                                                              |
| `links`          | array  | Navigation links in the header. Each: `{ "name": string, "href": string }`                                             |
| `socialLinks`    | array  | Social media icons in the footer. Each: `{ "platform": "instagram" \| "facebook" \| "tiktok" \| "x", "link": string }` |

#### Feature Cards (floating cards around iPhone mockup)

Decorative notification-style cards shown left and right of the iPhone on desktop. Always exactly 5 per side. Each card has:

| Sub-field   | Type          | Description                                                                                                                                                                               |
| ----------- | ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `icon`      | string        | Emoji or short text shown inside the icon circle                                                                                                                                          |
| `iconClass` | string        | CSS class for icon background color. Available: `icon-avatar`, `icon-blue`, `icon-coral`, `icon-green`, `icon-yellow`, `icon-brown`, `icon-yellow-soft`, `icon-orange`, `icon-gray-light` |
| `title`     | string (HTML) | Card title. Wrap in `<strong>` for bold                                                                                                                                                   |
| `subtitle`  | string        | Secondary text below the title                                                                                                                                                            |

| Field               | Type            | Description                                      |
| ------------------- | --------------- | ------------------------------------------------ |
| `featureCardsLeft`  | array (5 items) | Cards floating to the left of the iPhone mockup  |
| `featureCardsRight` | array (5 items) | Cards floating to the right of the iPhone mockup |

#### Feature Showcase (scrollable carousel)

| Field            | Type   | Description                                                                                            |
| ---------------- | ------ | ------------------------------------------------------------------------------------------------------ |
| `showcase_title` | string | Section heading above the carousel                                                                     |
| `feature_list`   | array  | Carousel cards. Each: `{ "icon": string (image path), "title": string, "description": string (HTML) }` |

#### Feature Detail & Highlight (mid-page sections)

| Field                           | Type          | Description                              |
| ------------------------------- | ------------- | ---------------------------------------- |
| `feature_detail.title`          | string (HTML) | Heading for the detail section           |
| `feature_detail.description`    | string        | Paragraph text for the detail section    |
| `feature_highlight.title`       | string        | Heading for the highlight section        |
| `feature_highlight.description` | string        | Paragraph text for the highlight section |
| `feature_highlight.image1`      | string        | Path to first phone image (back)         |
| `feature_highlight.image2`      | string        | Path to second phone image (front)       |

#### Reviews Section

| Field             | Type   | Description                                                            |
| ----------------- | ------ | ---------------------------------------------------------------------- |
| `reviews.title`   | string | Section heading (e.g. `"What our users say."`)                         |
| `reviews.reviews` | array  | Mixed review cards. Each has a `type` field that determines its shape: |

Review types:

| `type`          | Required fields                                                                |
| --------------- | ------------------------------------------------------------------------------ |
| `"tweet"`       | `avatar`, `name`, `handle`, `text` or `texts` (array for multi-paragraph)      |
| `"testimonial"` | `avatar`, `name`, `handle` (used as subtitle), `date`, `text`                  |
| `"appstore"`    | `title`, `date`, `stars` (1-5), `text`                                         |
| `"social"`      | `avatar`, `name`, `handle`, `videoCaption`, `socialStat`, `viewMoreBtn` (bool) |

#### Support Page

| Field                      | Type   | Description                                                                                                                                                                                                     |
| -------------------------- | ------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `supportTitle`             | string | Hero heading on the support page                                                                                                                                                                                |
| `supportEmail`             | string | Email address for the "Contact Support" button (mailto link)                                                                                                                                                    |
| `supportSearchPlaceholder` | string | Placeholder text in the search input                                                                                                                                                                            |
| `supportSectionTitle`      | string | Heading above the category cards                                                                                                                                                                                |
| `supportCards`             | array  | Quick-link cards. Each: `{ "title": string, "icon": string (SVG HTML) }`                                                                                                                                        |
| `supportCategories2`       | array  | Category cards on support landing page. Each: `{ "id": string, "title": string, "description": string, "icon": string (SVG HTML) }`                                                                             |
| `supportCategories`        | array  | Full support content tree. Each category contains `id`, `title`, and `articles[]`. Each article has `id`, `title`, `description`, `intro`, and `sections[]` (each with `heading`, `content`, optional `list[]`) |
| `popularArticles`          | array  | Featured articles on support page. Each: `{ "id": string, "categoryId": string, "category": string, "title": string }`                                                                                          |

#### Blog Page (`blogView`)

| Field                           | Type   | Description                                                                                                  |
| ------------------------------- | ------ | ------------------------------------------------------------------------------------------------------------ |
| `blogView.hero.title`           | string | Page heading                                                                                                 |
| `blogView.hero.description`     | string | Subtitle                                                                                                     |
| `blogView.featuredPost`         | object | Large featured post at top: `image`, `category`, `date`, `readTime`, `title`, `excerpt`, `link`              |
| `blogView.posts`                | array  | Blog post cards. Each: `image`, `category`, `date`, `readTime`, `title`, `excerpt`, `link` or `readMoreLink` |
| `blogView.sidebar.categories`   | object | Category filter. `title` + `items[]` with `name`, `count`, `link`                                            |
| `blogView.sidebar.newsletter`   | object | Newsletter signup: `title`, `description`, `placeholder`                                                     |
| `blogView.sidebar.popularPosts` | object | Popular articles list: `title` + `posts[]` with `number`, `title`, `link`                                    |
| `blogView.sidebar.cta`          | object | Sidebar call-to-action: `title`, `description`, `buttonText`                                                 |
| `blogView.loadMore.buttonText`  | string | "Load more" button label                                                                                     |

#### Updates / Changelog Page (`updatesView`)

| Field                             | Type   | Description                                                                                                                                                                                                                                            |
| --------------------------------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `updatesView.hero.title`          | string | Page heading                                                                                                                                                                                                                                           |
| `updatesView.hero.description`    | string | Subtitle                                                                                                                                                                                                                                               |
| `updatesView.releases`            | array  | Release entries. Each has: `isLatest` (bool), `version`, `date`, `title`, `description`. Latest release also has `badge` and `features[]` (with `icon`, `title`, `description`) + `imageUrl`. Older releases have `changelog[]` (string array) instead |
| `updatesView.sidebar.newsletter`  | object | Newsletter signup: `title`, `description`, `placeholder`                                                                                                                                                                                               |
| `updatesView.sidebar.quickAccess` | object | Version jump links: `title` + `links[]` with `version`                                                                                                                                                                                                 |
| `updatesView.sidebar.cta`         | object | Sidebar CTA: `title`, `description`, `buttonText`                                                                                                                                                                                                      |

#### Footer

| Field             | Type   | Description                                                   |
| ----------------- | ------ | ------------------------------------------------------------- |
| `footer.section1` | object | First footer column: `title` + `links[]` with `name`, `href`  |
| `footer.section3` | object | Second footer column: `title` + `links[]` with `name`, `href` |

#### Legal Pages

| Field                        | Type   | Description                           |
| ---------------------------- | ------ | ------------------------------------- |
| `privacyPolicyEffectiveDate` | string | Date shown on the privacy policy page |
| `termsOfUseEffectiveDate`    | string | Date shown on the terms of use page   |

The actual privacy policy and terms of use content lives in `config/privacy-policy.html` and `config/terms-of-use.html` (plain HTML).

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
