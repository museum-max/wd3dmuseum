# WorldCore — Virtual 3D Gallery

A modern React + Vite web prototype featuring a Three.js walkable gallery, artwork collection/search/filter UI, artwork details, a browser-session admin manager, and optional EVM wallet connection via ethers v6.

## Requirements
- Node.js 20 or newer (Node.js 18.18+ may also work with current Vite)
- npm
- Optional: MetaMask or another EIP-1193-compatible wallet for the wallet connection demo

## Run locally
1. Extract this folder.
2. Open a terminal in `worldcore-gallery`.
3. Install dependencies:
   ```bash
   npm install
   ```
4. Start the development server:
   ```bash
   npm run dev
   ```
5. Open the local URL printed by Vite (normally `http://localhost:5173`).
6. Create a production build with `npm run build`; preview it with `npm run preview`.

## Features
- Three.js 3D exhibition room, artwork panels, central sculpture, gallery lighting and clickable artwork.
- Use **W/A/S/D** or arrow keys to move. Hold **Shift** to move faster. Double-click inside the 3D scene to enable mouse look; click artwork to inspect it. Press Escape to release pointer lock.
- Search and category filters for artworks.
- Artwork details modal and demo listing prices.
- Admin manager can add artwork (title, artist, price, color, optional image URL and description) and remove artwork from the current in-memory session.
- Wallet button requests account access from an injected EVM wallet and displays address/network. It does not sign or send transactions.
- Responsive layout for mobile and desktop.

## Important production notes
This is a frontend prototype, not a production NFT marketplace. Prices and artwork records are demo data. Admin changes live only in React state and reset on refresh. There is no real minting, marketplace purchase, payment processing, server authentication, persistent database, or permanent decentralized storage.

Before public launch:
1. Add server-side authentication and authorization for admins; do not rely on a hidden frontend panel.
2. Store uploaded assets in a secure object store or decentralized storage service and validate file types/sizes.
3. Add a backend/database and API for gallery records.
4. For NFTs, deploy or integrate an audited ERC-721/ERC-1155 contract, configure the intended chain, and implement metadata URI handling.
5. Build purchase/mint flows with explicit transaction previews, error handling, and security review. Never store wallet private keys or seed phrases in this app.
6. Configure environment variables and deployment hosting; serve over HTTPS.

## Project layout
```
worldcore-gallery/
  index.html
  package.json
  README.md
  src/
    main.jsx
    style.css
```
