# Deployment Phase Quick Guide

## Overview
Deploy your Hedera dApp using free/freemium tools. Focus on Vercel for frontend, Render for backend, IPFS for data, and HTS for tokens. Use AI agents for deployment code generation.

### What Deployment Means
Making your prototype live on the internet for judges to test.

## Key Tools
- **Vercel**: Free frontend hosting (React/Next.js)
- **Render**: Free backend hosting (Node.js APIs)
- **IPFS/Pinata**: Decentralized file storage (NFTs, large data)
- **Hedera HTS**: Token operations without smart contracts

### Quick Deployment Steps
1. **Frontend**: Push Next.js code to GitHub, import to Vercel - auto-deploys
2. **Backend**: Create Express server, deploy to Render with env vars
3. **Data**: Upload to Pinata IPFS for decentralized storage
4. **Tokens**: Use HTS SDK calls - no deployment needed

### HTS vs Smart Contracts
- **HTS (Recommended)**: For tokens, transfers, simple operations
- **Smart Contracts**: Only for complex logic (use Solidity, deploy via SDK)

### Track-Specific Tips
- **RWA**: IPFS for asset docs, HTS for tokenized assets
- **Operations**: Render backend for APIs, consensus topics
- **Gaming/NFTs**: IPFS for media, Vercel for frontend
- **AI/DePIN**: Render for AI processing, HTS for incentives

### Testing
- Deploy to testnet first
- Verify on Hashscan
- Test with small amounts

## Tips for Non-Coders
- Use AI to generate deployment configs and scripts
- Start with free tiers; monitor usage
- Never commit private keys

## Next Steps
After deployment, prepare [Submission](../submission/) materials.

For the complete deployment guide with detailed steps, code examples, and troubleshooting, see the [main README](../../README.md).