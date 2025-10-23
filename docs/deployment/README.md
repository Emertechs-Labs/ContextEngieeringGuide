# Hedera dApp Deployment Guide for Africa Hackathon

## Overview
This guide covers deploying your Hedera-based decentralized application (dApp) for the Africa Hackathon. We'll focus on free/freemium tools to keep costs low, with an emphasis on Hedera Token Service (HTS) for token operations and smart contracts only when absolutely necessary for complex logic. As a non-coder, you'll use AI agents to handle code generation and deployment steps.

## Overview
This guide covers deploying your Hedera-based decentralized application (dApp) for the Africa Hackathon. We'll focus on free/freemium tools to keep costs low, with an emphasis on Hedera Token Service (HTS) for token operations and smart contracts only when absolutely necessary for complex logic. As a non-coder, you'll use AI agents to handle code generation and deployment steps.

### What Deployment Means
Making your prototype live on the internet so judges can see it work. It's like publishing a website, but for blockchain apps.

## Prerequisites
- Completed development phase with a working prototype
- Hedera testnet account with HBAR (free from [Hedera Developer Portal](https://portal.hedera.com/dashboard))
- GitHub repository with your project code
- Node.js installed locally
- Beginner Link: [GitHub Repo Setup](https://docs.github.com/en/get-started/quickstart/create-a-repo)

## Deployment Tools Overview

### Vercel (Frontend Deployment)
**Free Tier**: 100GB bandwidth/month, custom domains, automatic HTTPS
**Best For**: React/Next.js frontends, static sites
- Beginner Link: [Vercel for Beginners](https://vercel.com/docs/getting-started-with-vercel)

### Render (Backend Deployment)
**Free Tier**: 750 hours/month, auto-scaling, managed databases
**Best For**: Node.js APIs, Express servers, AI agent backends
- Beginner Link: [Render Docs](https://docs.render.com/)

### IPFS (Decentralized Data Storage)
**Free Options**: Pinata, Infura, or Fleek
**Best For**: Storing large files, NFT metadata, decentralized data
- Beginner Link: [IPFS Guide](https://docs.ipfs.io/how-to/)

## Frontend Deployment with Vercel

### Step-by-Step Guide
1. **Prepare Your Frontend Code**
   - Ensure your React/Next.js app is in a GitHub repo
   - Add a `vercel.json` for configuration:
   ```json
   {
     "version": 2,
     "builds": [
       {
         "src": "package.json",
         "use": "@vercel/next"
       }
     ],
     "routes": [
       {
         "src": "/(.*)",
         "dest": "/$1"
       }
     ]
   }
   ```
   - Beginner Tip: Use Copilot to generate this file.

2. **Connect to Vercel**
   - Go to [vercel.com](https://vercel.com) and sign up (free)
   - Import your GitHub repo
   - Vercel will auto-detect Next.js and deploy
   - Beginner Link: [Import GitHub Repo](https://vercel.com/docs/getting-started-with-vercel/import)

3. **Environment Variables**
   - In Vercel dashboard, add environment variables:
     - `HEDERA_ACCOUNT_ID`
     - `HEDERA_PRIVATE_KEY`
     - Any AI API keys
   - Beginner Link: [Environment Variables](https://vercel.com/docs/concepts/projects/environment-variables)

4. **Deploy**
   - Push to GitHub main branch to trigger auto-deployment
   - Your dApp will be live at `your-project.vercel.app`
   - Beginner Link: [Deploying](https://vercel.com/docs/deployments/overview)

### AI Agent Integration
Use GitHub Copilot to generate the `vercel.json`:
```
Generate a vercel.json configuration for a Next.js Hedera dApp
```

## Backend Deployment with Render

### Step-by-Step Guide
1. **Prepare Your Backend Code**
   - Create an Express server in your repo:
   ```javascript
   const express = require('express');
   const { Client } = require('@hashgraph/sdk');
   require('dotenv').config();

   const app = express();
   app.use(express.json());

   // Hedera client setup
   const client = Client.forTestnet().setOperator(
     process.env.HEDERA_ACCOUNT_ID,
     process.env.HEDERA_PRIVATE_KEY
   );

   app.get('/api/balance', async (req, res) => {
     // Add balance checking logic
   });

   const PORT = process.env.PORT || 3001;
   app.listen(PORT, () => console.log(`Server running on port ${PORT}`));
   ```

2. **Connect to Render**
   - Go to [render.com](https://render.com) and sign up (free)
   - Create a new "Web Service" from your GitHub repo
   - Select Node.js environment

3. **Configuration**
   - Build Command: `npm install`
   - Start Command: `node server.js`
   - Add environment variables in Render dashboard

4. **Deploy**
   - Render will build and deploy automatically
   - Your API will be available at `your-service.onrender.com`

### AI Agent Integration
Prompt Copilot for Express server code:
```
Create an Express.js server for Hedera balance queries with proper error handling
```

## IPFS for Data Storage

### When to Use IPFS
- Storing NFT metadata
- Large files (images, videos)
- Decentralized data that shouldn't rely on centralized servers

### Free IPFS Setup with Pinata
1. **Sign Up**: Create account at [pinata.cloud](https://pinata.cloud) (free tier: 1GB storage)
2. **Upload Files**: Use Pinata dashboard or API
3. **Integration Code**:
   ```javascript
   const pinataSDK = require('@pinata/sdk');
   const pinata = new pinataSDK(process.env.PINATA_API_KEY, process.env.PINATA_SECRET_KEY);

   async function uploadToIPFS(fileBuffer, fileName) {
     const result = await pinata.pinFileToIPFS(fileBuffer, {
       pinataMetadata: { name: fileName }
     });
     return `https://gateway.pinata.cloud/ipfs/${result.IpfsHash}`;
   }
   ```

### AI Agent Integration
Use Copilot to generate IPFS upload functions:
```
Write a function to upload NFT metadata to IPFS using Pinata SDK
```

## Smart Contract Deployment on Hedera

### When to Use Smart Contracts vs HTS
- **Use HTS (Recommended)**: For most token operations, fungible/non-fungible tokens, simple transfers
- **Use Smart Contracts**: Only for complex logic like custom business rules, multi-step transactions, or advanced DeFi features

### HTS Deployment (Preferred Method)
1. **Use Hedera SDK**:
   ```javascript
   const { TokenCreateTransaction, TokenType } = require('@hashgraph/sdk');

   async function createHTSToken(name, symbol, supply) {
     const transaction = new TokenCreateTransaction()
       .setTokenName(name)
       .setTokenSymbol(symbol)
       .setTokenType(TokenType.FungibleCommon)
       .setInitialSupply(supply)
       .setTreasuryAccountId(client.operatorAccountId);

     const txResponse = await transaction.execute(client);
     const receipt = await txResponse.getReceipt(client);
     return receipt.tokenId;
   }
   ```

2. **No Deployment Needed**: HTS tokens are created via API calls, not deployed like Ethereum contracts

### Smart Contract Deployment (For Complex Cases)
1. **Write Solidity Contract** (use AI for generation):
   ```solidity
   // SPDX-License-Identifier: MIT
   pragma solidity ^0.8.0;

   contract SimpleLending {
       // Complex lending logic here
   }
   ```

2. **Compile and Deploy**:
   ```javascript
   const { ContractCreateFlow } = require('@hashgraph/sdk');
   const fs = require('fs');

   async function deployContract() {
     const bytecode = fs.readFileSync('SimpleLending.bin');
     
     const transaction = new ContractCreateFlow()
       .setBytecode(bytecode)
       .setGas(100000);

     const txResponse = await transaction.execute(client);
     const receipt = await txResponse.getReceipt(client);
     return receipt.contractId;
   }
   ```

3. **Verification**: Use Hedera's contract verification tool or Sourcify for transparency

### AI Agent Integration
Prompt Copilot for contract code:
```
Generate a Solidity smart contract for a simple lending pool on Hedera
```

## Track-Specific Deployment Considerations
Tailor deployment to your track:

- **Onchain Finance & Real-World Assets (RWA):** Use IPFS for asset metadata/documents. Deploy HTS tokens for tokenized assets. Ensure secure storage for sensitive data.
- **DLT for Operations:** Focus on consensus topics for data integrity. Deploy backend on Render for API endpoints handling supply chain/healthcare updates.
- **Immersive Experiences (Gaming & NFTs):** Use IPFS for NFT media/metadata. Deploy frontend on Vercel for interactive games. HTS for in-game tokens.
- **AI & DePIN:** Integrate AI agents in backend. Use Render for AI processing servers. HTS for network incentives/tokens.

## Testing and Verification

### Testnet Testing
- Deploy to Hedera testnet first
- Use [Hedera Explorer](https://hashscan.io/) to verify transactions
- Test with small amounts of test HBAR

### Contract Verification
- For smart contracts, verify source code on Hedera's verification service
- Ensures transparency and trust for hackathon judges

## Cost Optimization Tips
- Use free tiers of Vercel/Render/IPFS
- Minimize smart contract complexity to reduce gas fees
- Leverage HTS to avoid contract deployment costs
- Monitor usage in dashboard to stay within free limits

## Security Best Practices
- Never commit private keys to GitHub
- Use environment variables for sensitive data
- Implement proper error handling
- Test thoroughly on testnet before mainnet

## Troubleshooting
- **Vercel Issues**: Check build logs in dashboard
- **Render Issues**: Monitor logs and restart if needed
- **Hedera Errors**: Verify account balance and network status
- **IPFS Issues**: Check gateway availability

## Next Steps
Once deployed, create a demo video and prepare your submission for the hackathon. Test your live dApp thoroughly and gather feedback from the Hedera community.

## Resources
- [Hedera Developer Documentation](https://docs.hedera.com/)
- [Vercel Documentation](https://vercel.com/docs)
- [Render Documentation](https://docs.render.com/)
- [IPFS Documentation](https://docs.ipfs.io/)
- [Hedera Token Service Guide](https://docs.hedera.com/guides/sdks/token-services)

Remember, as a non-coder, focus on describing what you want to AI tools like Copilot - they'll handle the technical implementation!