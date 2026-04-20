# 🍲 Mama Cookin — Home-Cooked Food Delivery

> Authentic Ukrainian home cooking, delivered fresh to your door in Watford, UK.

[![Live Site](https://img.shields.io/badge/🌐%20Live%20Site-mamacookin.com-orange?style=for-the-badge)](https://mamacookin.com)

[![Stripe](https://img.shields.io/badge/payments-Stripe-635BFF?logo=stripe&logoColor=white)](https://stripe.com)
[![Languages](https://img.shields.io/badge/languages-EN%20%7C%20RU%20%7C%20UK-blue)](#multilanguage-support)
[![License](https://img.shields.io/badge/license-MIT-green)](#license)

---

## 🔗 [mamacookin.com](https://mamacookin.com)

---

## Overview

**Mama Cookin** is a single-page food delivery app for a home-cooking business based in Watford. Customers can browse 60+ authentic Ukrainian and European dishes, build their own custom meal boxes or choose from curated packages, select a delivery date and time, and pay securely via Stripe — all from a polished, mobile-first interface available in English, Russian, and Ukrainian.

---

## Features

### Ordering
- **3 Curated Meal Packages** — Daily Meal Box, 3-Day Family Meal, Extended Family Package
- **60+ À La Carte Items** — soups, mains, sides, breakfasts, salads, baked goods, drinks
- **Interactive Bundle Builder** — customise packages section by section with skip/discount options
- **Promo Code System** — `WELCOME` for 10% off first orders

### Checkout & Payments
- **Stripe Elements** — secure, PCI-compliant card payments in GBP
- **Delivery or Self-Pickup** — toggle between options at checkout, with different pricing
- **Smart Date Picker** — Mon–Fri only, next-day minimum, no past dates
- **4 Evening Time Slots** — 5 PM, 6 PM, 7 PM, 8 PM delivery windows
- **Email Confirmations** — automatic order receipts via EmailJS

### Shopping Cart
- Real-time quantity controls and subtotal calculation
- Free delivery over £55, fixed £3.99 below
- £20 minimum order enforcement
- Special instructions field for allergies and preferences

### UI & Accessibility
- **Fully Responsive** — mobile-first design with safe-area insets for notch devices
- **Multilanguage** — full UI and menu content in English, Russian, and Ukrainian
- **Customer Reviews** section
- **FAQ** with language-specific content

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Vanilla HTML / CSS / JavaScript (SPA, no framework) |
| Fonts | Google Fonts — Playfair Display & Jost |
| Payments | [Stripe.js v3](https://stripe.com/docs/js) + Netlify Function |
| Email | [EmailJS](https://www.emailjs.com/) (CDN) |
| Backend | Netlify Functions (serverless) |
| Hosting | [Namecheap](https://namecheap.com) |
| Package Manager | npm (minimal — only `stripe` v14) |

---

## Project Structure

```
mama-cookin-food-delivery-app/
├── index.html                        # Entire SPA — HTML, CSS, and JS in one file
├── netlify.toml                      # Build & redirect configuration
├── package.json                      # Dependencies (stripe@14)
├── netlify/
│   └── functions/
│       └── create-payment-intent.js  # Serverless Stripe backend
└── food-images/                      # 80+ WebP food photos
```

---

## Getting Started

### Prerequisites

- Node.js (any recent LTS)
- A [Stripe](https://stripe.com) account (for payments)
- An [EmailJS](https://www.emailjs.com) account (for order confirmation emails)

### Local Development

```bash
# Clone the repo
git clone https://github.com/your-username/mama-cookin-food-delivery-app.git
cd mama-cookin-food-delivery-app

# Install dependencies
npm install

# Open in browser — no build step required
open index.html
```

> For full payment functionality locally, use the [Netlify CLI](https://docs.netlify.com/cli/get-started/) to run Netlify Functions:
> ```bash
> npm install -g netlify-cli
> netlify dev
> ```

### Environment Variables

Set these in your hosting dashboard (or a local `.env` file for `netlify dev`):

| Variable | Description |
|---|---|
| `STRIPE_SECRET_KEY` | Your Stripe secret key (`sk_live_...` or `sk_test_...`) |

The EmailJS credentials are currently embedded in `index.html`. Update these constants before deploying:

```js
const EMAILJS_SERVICE  = 'your_service_id';
const EMAILJS_TEMPLATE = 'your_template_id';
const EMAILJS_KEY      = 'your_public_key';
```

---

## Multilanguage Support

The app includes full translations for:

| Code | Language |
|---|---|
| `en` | English |
| `ru` | Russian |
| `uk` | Ukrainian |

All menu items, descriptions, UI labels, and FAQ content are translated. Language preference is selectable via the navbar and persists for the session.

---

## Delivery Info

| Detail | Value |
|---|---|
| Delivery area | Watford, UK |
| Days | Monday – Friday |
| Time slots | 5 PM / 6 PM / 7 PM / 8 PM |
| Earliest | Next day |
| Min. order | £20 |
| Delivery fee | £3.99 (free over £55) |
| Self-pickup | Available (free) |

---

## Menu Categories

| Category | Items |
|---|---|
| Soups | 10 varieties — borsch, broths, cream soups, Tom Yam, goulash |
| Main Courses | 16 items — Chicken Kiev, Georgian turkey, stroganoff, meatballs |
| Sides | 5 items — potatoes, pasta, rice, steamed vegetables |
| Breakfasts | 17 items — pancakes, omelettes, syrniki, porridges |
| Salads | 4 items — coleslaw, caesar, vinaigrette |
| Baking & Desserts | 17 items — cookies, pies, cakes, cinnamon rolls |
| Drinks | 4 items — compotes, mors, lemonade |

---

## License

MIT © Mama Cookin
