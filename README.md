# Solidity challenge

Edit `quote` in `contracts/contracts/skill/Quote.sol`. Do not change `RealEstateMarketplace.sol`.

The quote check reads the deployed vault, so start the chain, deploy, and the API from the project root. Leave the chain and the API running.

```bash
cd contracts
npm install
npx hardhat node
```

```bash
cd contracts
npx hardhat run scripts/deploy.js --network localhost
```

```bash
cd backend
npm install
npm run dev
```

The API listens on http://localhost:4000.

Run your result from the project root:

```bash
cd contracts
npx hardhat test test/Quote.test.js
```

Compare it with:

```bash
curl.exe "http://localhost:4000/api/properties/1/quote?shares=4"
```

task: "Return the exact integer wei cost of shares at sharePrice, and set canFill only when remaining shares cover the order."

pass if: "npx hardhat test test/Quote.test.js passes. That run calls http://localhost:4000/api/properties/1/quote?shares=4 and checks cost and canFill against it."
