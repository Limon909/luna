# VOIDMINT — Vercel-ready UI starter

A Ryfinite-inspired Next.js starter for a BNB Chain NFT gaming and passive-mining concept.

## Important scope note

This is a **frontend demo**, not a live token/mining protocol. Dashboard balances, NFT cards, quests, mining rates, and leaderboard rows are sample UI data. Pause/resume and quest buttons only change local demo state. No real tokens are issued or transferred. Wallet connection requests an account from an installed EVM wallet but does not send transactions.

Do not take paid mint payments or advertise live token rewards until the smart contracts are implemented, tested, reviewed, and deployed.

## Run locally

Requirements: Node.js 20.9+ and npm.

```bash
npm install
npm run dev
```

Open http://localhost:3000.

Build check:

```bash
npm run build
```

## Deploy using GitHub + Vercel

1. Extract this ZIP on your computer.
2. Create a new empty repository on GitHub, e.g. `voidmint`.
3. Upload the extracted project files/folders to the repository root. Make sure `package.json` is at the root, not inside an extra nested folder.
4. Commit the files to the `main` branch.
5. Sign in to Vercel using GitHub.
6. Select **Add New → Project**, import the `voidmint` repository.
7. Keep Framework Preset as **Next.js**. Keep the default build command `npm run build` and output settings; Vercel detects Next.js automatically.
8. Select **Deploy**.
9. When deployment finishes, open the generated `.vercel.app` URL and test it on desktop and mobile.
10. Every future push to the connected branch will trigger a new deployment.

## Alternative: upload from terminal

Install Git and Node.js, then in the extracted folder:

```bash
git init
git add .
git commit -m "Initial VOIDMINT UI"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/voidmint.git
git push -u origin main
```

Replace `YOUR-USERNAME` with your GitHub username.

## Next implementation phases

1. Add wagmi/viem and a tested BNB Chain connector.
2. Build and test NFT contract (ERC-721), reward token (BEP-20-compatible ERC-20), and mining/staking contract.
3. Deploy to BNB Chain Testnet first (chain ID 97).
4. Add contract addresses to public environment variables after deployment.
5. Add a server/database only where needed for profiles, quest progress and event indexing.
6. Test claims, ownership, reward limits, pause controls, and admin permissions.
7. Arrange an independent security review before any mainnet paid mint or real token reward launch.

## Environment variables

`.env.example` contains placeholders only. The UI demo does not need any environment variables. Never place private keys or seed phrases in `NEXT_PUBLIC_` variables or browser code.
