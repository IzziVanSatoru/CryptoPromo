# CryptoPromo

CryptoPromo is a modern, responsive single-page application (SPA) built with **Svelte 5 + Vite**. It displays information about the top 10 cryptocurrencies using a dynamic UI and smooth routing.

## 🚀 Features

- Modern UI with Svelte 5
- Vite for lightning-fast development
- Page routing using `svelte-routing`
- Dynamic token data from `crypto.json`
- 3D hover effects and animated navigation
- Mobile-first, responsive layout

## 📁 Project Structure

```
crypto-promo-website/
├── public/
│   └── crypto.json          # Dummy token data
│
├── src/
│   ├── lib/
│   │   ├── components/      # UI components (Navbar, Footer, TokenCard)
│   │   └── stores/          # Svelte store for token state
│   │
│   ├── pages/               # Page views (Home, Tokens, About)
│   ├── App.svelte           # Root app with router
│   └── main.js              # Mount entry point
│
├── index.html
├── package.json
├── vite.config.js
└── README.md
```

## 📦 Installation

```bash
git clone https://github.com/your-username/crypto-promo-website
cd crypto-promo-website
npm install
npm run dev
```

## 🔄 Data Source

Token data is fetched from `public/crypto.json` and stored in a writable store using Svelte.

```json
[
  { "id": 1, "name": "Bitcoin", "symbol": "BTC", "price": 67000 },
  { "id": 2, "name": "Ethereum", "symbol": "ETH", "price": 3400 },
  ...
]
```

## 🛠 Tech Stack

- **Svelte 5**
- **Vite**
- **svelte-routing** for SPA navigation
- **CSS-only styling** (no framework, minimal custom styles)

## 📄 Pages

- `/` – Home with welcome message and CTA
- `/tokens` – List of 10 crypto tokens with prices
- `/about` – Information about the app and stack

## ✨ To-Do / Ideas

- [ ] Live data integration with CoinGecko API
- [ ] Theme switcher (dark/light)
- [ ] Add search and filter for tokens

## 📜 License

MIT © 2025 CryptoPromo
