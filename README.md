
# Modenza — E-Commerce Website

> **Style • Comfort • You**

Modenza is a modern fashion e-commerce platform offering curated collections across Men, Women, Kids, Home & Living, and Beauty categories. Built for a seamless, delightful shopping experience.

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Pages & Components](#pages--components)
- [Shopping Cart & Checkout](#shopping-cart--checkout)
- [Environment Variables](#environment-variables)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

Modenza is a full-featured fashion retail platform inspired by leading e-commerce sites. It supports product browsing, wishlist management, a shopping bag/cart system, and a streamlined checkout flow. The platform highlights exclusive brand collections (e.g., Adidas, Nike) and features a unique **Studio** section for curated fashion content.

---

## Features

- 🛍️ **Multi-category Navigation** — Men, Women, Kids, Home & Living, Beauty, Studio
- 🔍 **Smart Search** — Search across products, brands, and more
- 👤 **User Profile** — Account management, order history, and preferences
- ❤️ **Wishlist** — Save favourite items for later
- 🛒 **Shopping Bag** — Real-time cart with item count badge
- 💰 **Price Breakdown** — MRP, discounts, convenience fee, and total amount
- 📦 **Delivery Info** — Expected delivery dates per item
- 🔄 **Return Policy** — 14-day return window displayed per product
- ✅ **Order Placement** — One-click Place Order CTA
- 🏷️ **Discount Display** — Discount percentage and savings shown clearly
- 📱 **Responsive Design** — Optimised for desktop, tablet, and mobile
- 🆕 **Studio (NEW)** — Highlighted new feature section

---

## Tech Stack

| Layer        | Technology                          |
|--------------|-------------------------------------|
| Frontend     | React.js / Next.js                  |
| Styling      | Tailwind CSS / CSS Modules          |
| State Mgmt   | Redux Toolkit / Context API         |
| Backend      | Node.js + Express (or Next.js API)  |
| Database     | MongoDB / PostgreSQL                |
| Auth         | JWT / OAuth 2.0                     |
| Payments     | Razorpay / Stripe                   |
| Image Hosting| Cloudinary / AWS S3                 |
| Deployment   | Vercel / AWS                        |

---

## Project Structure

```
modenza/
├── public/
│   ├── assets/
│   │   ├── logo.svg
│   │   └── icons/
│   └── favicon.ico
├── src/
│   ├── components/
│   │   ├── Navbar/
│   │   │   ├── Navbar.jsx
│   │   │   ├── SearchBar.jsx
│   │   │   └── NavLinks.jsx
│   │   ├── Cart/
│   │   │   ├── CartItem.jsx
│   │   │   ├── CartSummary.jsx
│   │   │   └── PriceDetails.jsx
│   │   ├── Product/
│   │   │   ├── ProductCard.jsx
│   │   │   ├── ProductGrid.jsx
│   │   │   └── ProductDetail.jsx
│   │   ├── Wishlist/
│   │   │   └── WishlistIcon.jsx
│   │   └── Footer/
│   │       └── Footer.jsx
│   ├── pages/
│   │   ├── index.jsx           # Homepage
│   │   ├── men.jsx
│   │   ├── women.jsx
│   │   ├── kids.jsx
│   │   ├── home-living.jsx
│   │   ├── beauty.jsx
│   │   ├── studio.jsx
│   │   ├── cart.jsx            # Shopping Bag
│   │   ├── wishlist.jsx
│   │   ├── profile.jsx
│   │   └── checkout.jsx
│   ├── store/
│   │   ├── cartSlice.js
│   │   ├── wishlistSlice.js
│   │   └── userSlice.js
│   ├── hooks/
│   │   ├── useCart.js
│   │   └── useAuth.js
│   ├── utils/
│   │   ├── formatCurrency.js
│   │   └── api.js
│   └── styles/
│       ├── globals.css
│       └── variables.css
├── .env.local
├── .gitignore
├── package.json
├── next.config.js
└── README.md
```

---

## Getting Started

### Prerequisites

- Node.js >= 18.x
- npm >= 9.x or yarn >= 1.22.x

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/your-org/modenza.git

# 2. Navigate into the project
cd modenza

# 3. Install dependencies
npm install
# or
yarn install

# 4. Set up environment variables
cp .env.example .env.local
# Fill in required values (see Environment Variables section)

# 5. Run the development server
npm run dev
# or
yarn dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

---

## Pages & Components

### Navbar
- **Logo** — Modenza brand mark with tagline
- **Category Links** — Men, Women, Kids, Home & Living, Beauty, Studio (NEW badge)
- **Search Bar** — Placeholder: *"Search for products, brands and more"*
- **Profile** — User account access
- **Wishlist** — Saved items icon
- **Bag** — Cart icon with item count badge (e.g., `2`)

### Shopping Bag (`/cart`)
Displays all items added to the cart with:
- Product image thumbnail
- Brand name & product title
- Price (MRP and discounted price)
- Discount percentage
- Return policy duration
- Expected delivery date
- Remove item (✕) button

### Price Details Panel
| Field              | Description                          |
|--------------------|--------------------------------------|
| Total MRP          | Sum of all item MRPs                 |
| Discount on MRP    | Total discount applied               |
| Convenience Fee    | Platform fee (e.g., ₹99)            |
| **Total Amount**   | Final payable amount                 |

**Place Order** — Primary CTA button (pink/red, full-width)

### Footer
Three-column layout with links for:
- Men, Women, Kids, Home & Living, Beauty, Gift Card, Myntra Insider

---

## Shopping Cart & Checkout

1. **Add to Cart** from any product page or listing
2. **View Bag** — See all items, quantities, and price breakdown
3. **Apply Coupons** *(if applicable)*
4. **Place Order** — Proceeds to address selection and payment
5. **Payment** — Integrated with Razorpay/Stripe
6. **Order Confirmation** — Email + in-app notification

---

## Environment Variables

Create a `.env.local` file at the root with the following:

```env
# App
NEXT_PUBLIC_APP_NAME=Modenza
NEXT_PUBLIC_BASE_URL=http://localhost:3000

# API
NEXT_PUBLIC_API_URL=https://api.modenza.com/v1

# Auth
NEXTAUTH_SECRET=your_secret_here
NEXTAUTH_URL=http://localhost:3000

# Payment Gateway
RAZORPAY_KEY_ID=your_razorpay_key
RAZORPAY_KEY_SECRET=your_razorpay_secret

# Cloudinary (Image Hosting)
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret

# Database
DATABASE_URL=mongodb+srv://user:password@cluster.mongodb.net/modenza
```

---

## Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature-name`
3. Commit your changes: `git commit -m "feat: add your feature"`
4. Push to the branch: `git push origin feature/your-feature-name`
5. Open a Pull Request

Please follow the [Conventional Commits](https://www.conventionalcommits.org/) standard for commit messages.

---

## License

© 2024 Modenza. All rights reserved.

This project is proprietary software. Unauthorized copying, distribution, or modification is strictly prohibited without prior written permission from Modenza.

---

*Built with ❤️ — Style • Comfort • You*
