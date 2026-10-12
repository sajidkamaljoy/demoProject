# demoProject

A Nuxt 3 storefront demo that shows products from a live nopCommerce store through its web API. It has a login flow, a product catalog with categories, a cart and a mock checkout.

## Features

- **Home page** with a manufacturer carousel loaded from the store API.
- **Products page:** browse by category, see old and current prices, adjust quantity, then "Buy Now" or "Add to cart".
- **Login** using the store's OTP sign-in endpoint (`verifysigninotp`), with the logged-in state shared across pages.
- **Mock checkout:** the app starts with a demo credit balance, deducts the total on purchase and shows success or failure with SweetAlert2 popups.
- Simple About Us page, shared header and footer, and a default layout.

## Tech stack

Nuxt 3, Vue 3 (Composition API with `<script setup>`), TypeScript, SweetAlert2. Data comes from the public nopCommerce demo API at `vitalac.nop-station.com`.

## Project structure

```
app.vue        shared state (credit, cart, auth) provided to all pages
pages/         index, products, buynow, login, logout, AboutUs
components/    AppHeader, AppFooter, CategoryList, HomeCarouselManufacturer
layouts/       default layout
types/         Product, Category, Carousel interfaces
assets/        styles
```

## Run it

```bash
npm install
npm run dev
```

Then open `http://localhost:3000`.

Other scripts: `npm run build` (production build), `npm run preview` (preview the build) and `npm run generate` (static generation).

## Notes

- The API base URL is written directly in the pages and components. To use your own nopCommerce store, replace `https://vitalac.nop-station.com` with its address.
- Checkout is a client-side demo. It uses a fake credit balance, and no real payment or order is created.
