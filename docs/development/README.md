# Development Phase for Hedera Africa Hackathon

## Overview
The development phase is where your researched ideas become functional prototypes. As a non-coder, leverage AI agents like the Hedera AI Agent Kit and MCP servers to build decentralized applications (dApps) on Hedera. These tools allow you to use natural language prompts to generate code, interact with Hedera services, and test on the testnet—AI handles the technical heavy lifting.

### What You'll Build
A simple prototype that shows your idea working on Hedera, like creating tokens, sending messages, or minting NFTs. No coding needed—just describe it to AI!

## Key Tools for Development
Focus on Hedera AI Agent Kit for AI-powered dApp building and MCP servers for seamless AI integration.

### Hedera AI Agent Kit
A toolkit for creating LLM-based agents that perform Hedera operations via natural language. Supports plugins for accounts, tokens, consensus, and queries. Ideal for non-coders: Describe your idea, and the agent builds/executes it.

#### Setup Steps
1. **Prerequisites:** Node.js v20+ (install from [https://nodejs.org](https://nodejs.org)). Get a Hedera testnet account at [https://portal.hedera.com/dashboard](https://portal.hedera.com/dashboard) for free HBAR.
   - Beginner Link: [Node.js Installation Guide](https://nodejs.org/en/download/).
2. **Create Project:**
   ```bash
   mkdir hedera-hackathon-prototype
   cd hedera-hackathon-prototype
   npm init -y
   ```
3. **Install Dependencies:**
   ```bash
   npm install hedera-agent-kit @langchain/core langchain @hashgraph/sdk dotenv
   # Add AI provider, e.g., npm install @langchain/groq (free alternative to OpenAI)
   ```
   - Beginner Link: [NPM Basics](https://docs.npmjs.com/getting-started).
4. **Configure Environment:** Create `.env` file:
   ```
   HEDERA_ACCOUNT_ID=0.0.xxxxx
   HEDERA_PRIVATE_KEY=0x...
   GROQ_API_KEY=your-key-here  # Or OPENAI_API_KEY
   ```
   - Beginner Link: [Hedera Testnet Setup](https://portal.hedera.com/dashboard).
5. **Initialize Agent:** Use code from [Hedera Agent Kit GitHub](https://github.com/hashgraph/hedera-agent-kit-js) to set up an agent executor.
   - Beginner Link: [Agent Kit Quick Start](https://docs.hedera.com/hedera/open-source-solutions/ai-studio-on-hedera/hedera-ai-agent-kit).

#### Examples for Hackathon Tracks
Prompt the agent in natural language; it generates/executes code. Examples for each track:

- **Onchain Finance & Real-World Assets (RWA):** For tokenized assets and financial tools.
  - Prompt: "Create a consensus topic for asset tracking called 'RWATracking'."
  - Follow-up: "Submit message 'Asset verified in Nairobi' to the topic." Or "Tokenize a farming asset using HTS."
  - Beginner Link: [Token Creation Tutorial](https://docs.hedera.com/guides/sdks/token-services/create-a-token).
- **DLT for Operations:** For supply chains or healthcare.
  - Prompt: "Create a topic for supply chain updates."
  - Follow-up: "Submit encrypted message for a healthcare record."
  - Beginner Link: [Consensus Service Tutorial](https://docs.hedera.com/guides/sdks/consensus-service/create-a-topic).
- **Immersive Experiences (Gaming & NFTs):** For games and collectibles.
  - Prompt: "Mint an NFT with metadata 'Rare Sword'."
  - Follow-up: "Create a token for in-game rewards."
  - Beginner Link: [NFT Minting Guide](https://docs.hedera.com/guides/sdks/token-services/mint-an-nft).
- **AI & DePIN:** For AI-powered networks.
  - Prompt: "Create a token called 'DePINPoints' with symbol 'DPN' for network incentives."
  - Follow-up: "Transfer 50 DPN tokens to node 0.0.67890."
  - Beginner Link: [AI Agent Kit Examples](https://github.com/hashgraph/hedera-agent-kit-js/tree/main/examples).

Use Copilot or Claude to refine prompts and debug.

### MCP Servers (Model Context Protocol)
Integrates Hedera tools into AI apps like Claude Desktop or Cursor IDEs. Allows AI to query balances, create tokens, etc., autonomously.

For an introduction to MCP, see [https://modelcontextprotocol.io/docs/getting-started/intro](https://modelcontextprotocol.io/docs/getting-started/intro).

#### Setup Steps
1. Clone the repo: `git clone https://github.com/hashgraph/hedera-agent-kit-js.git && cd hedera-agent-kit-js/modelcontextprotocol`.
2. Install: `npm install && npm run build`.
3. Set env vars: Export `HEDERA_OPERATOR_ID` and `HEDERA_OPERATOR_KEY` (from testnet account).
4. Run server: `node dist/index.js --ledger-id=testnet`.
5. Integrate with Claude Desktop: Add to `claude_desktop_config.json`:
   ```json
   {
     "mcpServers": {
       "hedera-mcp-server": {
         "command": "node",
         "args": ["/path/to/dist/index.js"],
         "env": { "HEDERA_OPERATOR_ID": "0.0.xxxx", "HEDERA_OPERATOR_KEY": "302e...." }
       }
     }
   }
   ```
6. For VS Code/Copilot: Use MCP-compatible extensions or Cursor for built-in support.

#### Using MCP for Development
- Ask AI: "Check my Hedera balance" or "Create a topic for updates."
- AI uses Hedera tools via MCP to perform actions or generate code snippets.
- Test in the AI app; iterate with prompts.

## Building and Testing Prototypes
- **Workflow:** Start with templates from [Hedera Agent Kit GitHub](https://github.com/hashgraph/hedera-agent-kit-js). Use `npx create-hedera-agent-kit-app my-app` for a quick start.
- **Code Generation:** Use Copilot/Claude: "Generate JavaScript code for a Hedera token transfer using the agent kit."
- **Testing on Testnet:** Run locally (`node index.js`), then deploy via Hedera Portal. Use free HBAR for transactions.
- **Debugging:** Prompt AI: "Fix this error in my Hedera agent code."
- **UI/Frontend:** For dApps, use Next.js templates; AI can generate React components.

## Tips for Non-Coders
- **Conversational Approach:** Treat AI as your developer—describe features in plain English.
- **Iterate:** Build incrementally; test small parts first.
- **Resources:** Join [Hedera Discord](https://discord.gg/hedera) for support. Use [Hedera Developer Portal](https://portal.hedera.com/) for docs and playground.
- **Free Tools:** Use Groq or Ollama for AI without costs.
- **Version Control:** Push code to GitHub for backup and collaboration.

## Complete Development Workflow

### Week 1: Foundation
**Days 1-2: Environment Setup**
- Install all prerequisites (Node.js, testnet account)
- Set up project structure
- Test basic Hedera connection
- Verify AI agent responds to prompts

**Days 3-5: Core Features**
- Implement 1 core feature using AI agents
- Test on testnet
- Document what works
- Iterate based on results

**Days 6-7: Integration**
- Connect frontend to backend (if applicable)
- Add error handling
- Improve user experience
- Prepare for Week 2

### Week 2-8: Iteration & Testing
- Add features incrementally
- Test each addition thoroughly
- Get community feedback weekly
- Document progress for submission

### Final Week: Polish & Deploy
- Bug fixes and optimization
- Deployment to testnet/mainnet
- Create demo video
- Prepare submission materials

## Detailed Code Examples

### Example 1: Creating a Fungible Token (RWA Track)

```javascript
// Install: npm install @hashgraph/sdk dotenv
require('dotenv').config();
const { Client, PrivateKey, TokenCreateTransaction, TokenType } = require('@hashgraph/sdk');

async function createToken() {
  // Connect to Hedera testnet
  const client = Client.forTestnet();
  client.setOperator(
    process.env.HEDERA_ACCOUNT_ID,
    PrivateKey.fromStringECDSA(process.env.HEDERA_PRIVATE_KEY)
  );

  // Create token representing farmland acres
  const tokenCreateTx = new TokenCreateTransaction()
    .setTokenName("Farmland Token")
    .setTokenSymbol("LAND")
    .setTokenType(TokenType.FungibleCommon)
    .setDecimals(2)  // 2 decimals for fractional acres
    .setInitialSupply(10000)  // 100 acres (10000 / 100)
    .setTreasuryAccountId(client.operatorAccountId)
    .setSupplyKey(client.operatorPublicKey)
    .setAdminKey(client.operatorPublicKey);

  try {
    // Submit transaction
    const txResponse = await tokenCreateTx.execute(client);
    const receipt = await txResponse.getReceipt(client);
    const tokenId = receipt.tokenId;
    
    console.log(`Token created! ID: ${tokenId}`);
    console.log(`View on Hashscan: https://hashscan.io/testnet/token/${tokenId}`);
    
    return tokenId;
  } catch (error) {
    console.error('Error creating token:', error);
    throw error;
  } finally {
    client.close();
  }
}

createToken();
```

**AI Prompt to Generate This:**
"Create a JavaScript function using Hedera SDK to create a fungible token representing farmland. Token name: 'Farmland Token', symbol: 'LAND', 2 decimals for fractional ownership, initial supply of 100 acres. Include error handling and Hashscan link."

### Example 2: Consensus Service for Supply Chain (DLT Operations Track)

```javascript
require('dotenv').config();
const { 
  Client, 
  PrivateKey, 
  TopicCreateTransaction,
  TopicMessageSubmitTransaction 
} = require('@hashgraph/sdk');

async function createSupplyChainTopic() {
  const client = Client.forTestnet();
  client.setOperator(
    process.env.HEDERA_ACCOUNT_ID,
    PrivateKey.fromStringECDSA(process.env.HEDERA_PRIVATE_KEY)
  );

  // Create topic for supply chain messages
  const topicCreateTx = new TopicCreateTransaction()
    .setTopicMemo("Coffee Supply Chain - Farm to Cup");

  const txResponse = await topicCreateTx.execute(client);
  const receipt = await txResponse.getReceipt(client);
  const topicId = receipt.topicId;

  console.log(`Topic created: ${topicId}`);

  // Submit first message
  await submitMessage(client, topicId, {
    stage: "Harvest",
    location: "Ethiopian Highland Farm",
    quantity: "500kg",
    timestamp: new Date().toISOString(),
    quality: "Grade A"
  });

  client.close();
  return topicId;
}

async function submitMessage(client, topicId, data) {
  const message = JSON.stringify(data);
  
  const messageTx = new TopicMessageSubmitTransaction()
    .setTopicId(topicId)
    .setMessage(message);

  const txResponse = await messageTx.execute(client);
  const receipt = await txResponse.getReceipt(client);
  
  console.log(`Message submitted to topic ${topicId}`);
  console.log(`Sequence number: ${receipt.topicSequenceNumber}`);
  console.log(`Data: ${message}`);
}

createSupplyChainTopic();
```

**AI Prompt to Generate This:**
"Create a Hedera Consensus Service topic for coffee supply chain tracking. Include function to submit JSON messages with fields: stage, location, quantity, timestamp, quality. Add example for harvest stage in Ethiopia."

### Example 3: NFT Minting (Immersive Experience Track)

```javascript
require('dotenv').config();
const {
  Client,
  PrivateKey,
  TokenCreateTransaction,
  TokenMintTransaction,
  TokenType,
  TokenSupplyType
} = require('@hashgraph/sdk');

async function createNFTCollection() {
  const client = Client.forTestnet();
  client.setOperator(
    process.env.HEDERA_ACCOUNT_ID,
    PrivateKey.fromStringECDSA(process.env.HEDERA_PRIVATE_KEY)
  );

  // Create NFT collection
  const nftCreateTx = new TokenCreateTransaction()
    .setTokenName("African Art Collection")
    .setTokenSymbol("AFROART")
    .setTokenType(TokenType.NonFungibleUnique)
    .setDecimals(0)
    .setInitialSupply(0)
    .setMaxSupply(10000)
    .setSupplyType(TokenSupplyType.Finite)
    .setTreasuryAccountId(client.operatorAccountId)
    .setSupplyKey(client.operatorPublicKey)
    .setAdminKey(client.operatorPublicKey);

  const txResponse = await nftCreateTx.execute(client);
  const receipt = await txResponse.getReceipt(client);
  const tokenId = receipt.tokenId;

  console.log(`NFT Collection created: ${tokenId}`);

  // Mint first NFT
  const metadata = {
    name: "Maasai Warrior #1",
    description: "Digital art representing Maasai culture",
    image: "ipfs://QmXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX",
    attributes: [
      { trait_type: "Culture", value: "Maasai" },
      { trait_type: "Rarity", value: "Legendary" }
    ]
  };

  const mintTx = new TokenMintTransaction()
    .setTokenId(tokenId)
    .setMetadata([Buffer.from(JSON.stringify(metadata))]);

  const mintResponse = await mintTx.execute(client);
  const mintReceipt = await mintResponse.getReceipt(client);

  console.log(`NFT minted! Serial number: ${mintReceipt.serials[0]}`);
  
  client.close();
  return { tokenId, serial: mintReceipt.serials[0] };
}

createNFTCollection();
```

**AI Prompt to Generate This:**
"Create a Hedera NFT collection called 'African Art Collection' with max supply 10,000. Include a function to mint the first NFT with metadata for a Maasai warrior artwork, including IPFS link and attributes. Use proper metadata format."

### Example 4: AI Agent Integration (AI & DePIN Track)

```javascript
require('dotenv').config();
const { HederaAgentKit } = require('hedera-agent-kit');
const { ChatGroq } = require('@langchain/groq');
const { AgentExecutor, createReactAgent } = require('langchain/agents');
const { PromptTemplate } = require('@langchain/core/prompts');

async function createAIAgent() {
  // Initialize Hedera agent kit
  const agent = new HederaAgentKit({
    accountId: process.env.HEDERA_ACCOUNT_ID,
    privateKey: process.env.HEDERA_PRIVATE_KEY,
    network: 'testnet'
  });

  // Initialize AI model (free Groq)
  const model = new ChatGroq({
    apiKey: process.env.GROQ_API_KEY,
    modelName: 'mixtral-8x7b-32768',
    temperature: 0
  });

  // Get Hedera tools
  const tools = agent.getTools();

  // Create agent prompt
  const prompt = PromptTemplate.fromTemplate(`
    You are a helpful AI assistant that can interact with the Hedera network.
    You have access to tools for creating tokens, checking balances, and more.
    
    Current conversation:
    {chat_history}
    
    Question: {input}
    {agent_scratchpad}
  `);

  // Create agent executor
  const reactAgent = await createReactAgent({
    llm: model,
    tools,
    prompt
  });

  const executor = new AgentExecutor({
    agent: reactAgent,
    tools,
    verbose: true
  }))
;

  return executor;
}

// Use the agent
async function main() {
  const executor = await createAIAgent();
  
  // Example: Create a DePIN token
  const result = await executor.invoke({
    input: "Create a token called 'SolarPoints' with symbol 'SOLAR' for rewarding solar panel network contributors. Initial supply: 1,000,000."
  });

  console.log('Agent response:', result.output);
}

main();
```

**AI Prompt to Generate This:**
"Create a Hedera AI agent using hedera-agent-kit and LangChain with Groq (free). Set up agent executor that can create tokens via natural language. Include example for creating a 'SolarPoints' token for DePIN solar network rewards."

## Debugging & Troubleshooting

### Common Errors & Solutions

#### 1. "INSUFFICIENT_TX_FEE"
**Cause:** Transaction fee too low  
**Solution:**
```javascript
// Add more HBAR to transaction
const tx = new TokenCreateTransaction()
  .setMaxTransactionFee(new Hbar(20));  // Increase from default
```

#### 2. "INVALID_SIGNATURE"
**Cause:** Wrong private key or key not set  
**Solution:**
```javascript
// Ensure key is in correct format
const privateKey = PrivateKey.fromStringECDSA(process.env.HEDERA_PRIVATE_KEY);
// For Ed25519 keys, use fromString() instead
```

#### 3. "ACCOUNT_ID_DOES_NOT_EXIST"
**Cause:** Using mainnet account on testnet or typo  
**Solution:**
- Verify account exists on [Hashscan Testnet](https://hashscan.io/testnet)
- Check `.env` file for typos
- Ensure format is 0.0.xxxxx

#### 4. AI Agent Not Responding
**Cause:** API key invalid or rate limit  
**Solution:**
```javascript
// Add error handling
try {
  const result = await executor.invoke({ input: prompt });
} catch (error) {
  if (error.message.includes('rate limit')) {
    console.log('Rate limited. Wait 60 seconds.');
    await new Promise(r => setTimeout(r, 60000));
    // Retry
  }
}
```

### Debugging Workflow

**Step 1: Check Basics**
```javascript
// Add at start of every file
console.log('Account ID:', process.env.HEDERA_ACCOUNT_ID);
console.log('Network:', client.network);
console.log('Operator:', client.operatorAccountId?.toString());
```

**Step 2: Add Try-Catch**
```javascript
try {
  const result = await transaction.execute(client);
  console.log('Success:', result);
} catch (error) {
  console.error('Error details:', {
    message: error.message,
    status: error.status,
    transactionId: error.transactionId?.toString()
  });
}
```

**Step 3: Use Hashscan**
- Every transaction has an ID
- Look it up on https://hashscan.io/testnet
- View exact error from network

**Step 4: Ask AI**
```
Prompt: "I'm getting this error: [paste error]. Here's my code: [paste code]. 
What's wrong and how do I fix it? I'm building for Hedera testnet."
```

## Testing Strategies

### Unit Testing with Jest

```javascript
// tests/token.test.js
const { createToken } = require('../src/token');

describe('Token Creation', () => {
  test('should create token successfully', async () => {
    const tokenId = await createToken();
    expect(tokenId).toBeDefined();
    expect(tokenId.toString()).toMatch(/^0\.0\.\d+$/);
  }, 30000);  // 30 second timeout for blockchain

  test('should handle errors gracefully', async () => {
    // Test with invalid data
    await expect(createToken({ invalidParam: true }))
      .rejects
      .toThrow();
  });
});
```

**Run tests:** `npm test`

### Integration Testing

1. **Test on testnet first** - Never test on mainnet
2. **Use small amounts** - Test with 1 HBAR, not 100
3. **Verify on Hashscan** - Check every transaction
4. **Test edge cases** - What if user inputs 0? Negative numbers?
5. **Get community feedback** - Share testnet link for others to try

## Performance Optimization

### Batch Transactions

```javascript
// Instead of multiple calls
for (let i = 0; i < 100; i++) {
  await submitMessage(topicId, message);  // Slow!
}

// Use batch
const promises = [];
for (let i = 0; i < 100; i++) {
  promises.push(submitMessage(topicId, message));
}
await Promise.all(promises);  // Much faster!
```

### Caching

```javascript
// Cache account balance to avoid repeated queries
let cachedBalance = null;
let cacheTime = 0;

async function getBalance(client) {
  const now = Date.now();
  if (cachedBalance && (now - cacheTime) < 60000) {  // 1 min cache
    return cachedBalance;
  }
  
  cachedBalance = await new AccountBalanceQuery()
    .setAccountId(client.operatorAccountId)
    .execute(client);
  cacheTime = now;
  
  return cachedBalance;
}
```

## Next Steps
Once you have a working prototype tested on testnet, move to [Deployment](../deployment/). Ensure your project:

1. ✅ Works reliably on Hedera testnet
2. ✅ Has error handling for all user inputs
3. ✅ Passes basic tests
4. ✅ Has clean, documented code
5. ✅ Provides good user experience

For full details, refer to [Hedera AI Agent Kit Docs](https://docs.hedera.com/hedera/open-source-solutions/ai-studio-on-hedera/hedera-ai-agent-kit).