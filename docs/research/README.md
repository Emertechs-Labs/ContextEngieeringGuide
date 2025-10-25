# Research Phase for Hedera Africa Hackathon

## Overview
In the research phase, you'll validate and expand on your ideation ideas by gathering technical knowledge, resources, and tools. As a non-coder, focus on understanding Hedera's ecosystem, fetching relevant documentation and code examples to your local PC, and using AI tools like GitHub Copilot in VS Code to explore and learn. This phase builds a foundation for development without requiring deep coding skills - AI agents will handle implementation later.

## Overview
In the research phase, you'll validate and expand on your ideation ideas by gathering technical knowledge, resources, and tools. As a non-coder, focus on understanding Hedera's ecosystem, fetching relevant documentation and code examples to your local PC, and using AI tools like GitHub Copilot in VS Code to explore and learn. This phase builds a foundation for development without requiring deep coding skills - AI agents will handle implementation later.

### Why Research?
Research helps you understand if your idea is possible on Hedera. You'll learn about tokens, consensus, and AI tools, so you can explain your project clearly to AI builders later.

## Setting Up Essential Tools
Before researching, set up accounts and software. These tools enable collaboration, code exploration, and AI-assisted learning.

### 1. Create a GitHub Account
GitHub hosts open-source projects, including Hedera's code and docs. You'll use it to fetch repositories and collaborate.
- **Steps:**
  1. Go to [https://github.com](https://github.com) and click "Sign up".
  2. Enter your email, create a username (e.g., "HederaInnovator2025"), and set a password.
  3. Verify your email and complete the setup (optional: add a profile picture and bio).
  4. Join the Hedera community: Search for "hashgraph" or "hedera" repos and star/fork them.
- **Why?** Free account; needed for cloning repos and accessing hackathon resources.
- **Beginner Link:** [GitHub Hello World Guide](https://docs.github.com/en/get-started/quickstart/hello-world) for basics.

### 2. Install Git
Git is required for downloading GitHub repos.
- **Steps (Windows):**
  1. Download from [https://git-scm.com/downloads](https://git-scm.com/downloads).
  2. Run the installer; accept defaults.
  3. Open Command Prompt or PowerShell and type `git --version` to verify.
- **Alternatives:** Use GitHub Desktop (GUI) from [https://desktop.github.com](https://desktop.github.com) for easier cloning.
- **Beginner Link:** [Git Basics](https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F).

### 3. Install VS Code
Visual Studio Code (VS Code) is a free, powerful editor with built-in AI support.
- **Steps:**
  1. Download from [https://code.visualstudio.com](https://code.visualstudio.com).
  2. Run the installer; accept defaults.
  3. Open VS Code and install extensions: Search for "GitHub Copilot" in the Extensions sidebar (Ctrl+Shift+X).
- **Alternatives:**
  - **Cursor:** AI-first editor with built-in Copilot-like features; download from [https://cursor.sh](https://cursor.sh).
  - **VSCodium:** Open-source VS Code fork; from [https://vscodium.com](https://vscodium.com).
  - **Sublime Text or Atom:** Lightweight editors; install from their sites.
- **Beginner Link:** [VS Code Getting Started](https://code.visualstudio.com/docs/getstarted/getting-started).

### 4. Set Up GitHub Copilot
Copilot provides AI code suggestions and research help.
- **Steps in VS Code:**
  1. Install the "GitHub Copilot" extension.
  2. Sign in with your GitHub account (it may prompt for a free trial or subscription).
  3. Enable it in settings: Search "Copilot" and toggle on.
- **Alternatives:**
  - **GitHub Copilot Chat:** Extension for conversational AI in VS Code.
  - **Claude in Cursor:** Built-in AI for coding and research.
  - **Tabnine or CodeWhisperer:** Free AI code assistants; install as extensions.
- **Beginner Link:** [Copilot Setup Guide](https://docs.github.com/en/copilot/getting-started-with-github-copilot/getting-started-with-github-copilot-in-visual-studio-code).

## Fetching Data to Your Local Directory
Download Hedera docs, SDKs, and examples to your PC for offline research. Store them in a dedicated folder, e.g., `E:\HederaResearch`.

### General Steps for Downloading
- **From Websites:** Right-click on PDFs/docs and "Save as" to your folder.
- **From GitHub:** Clone repos using Git or GitHub Desktop.
  - Example: Open Command Prompt, navigate to your folder (`cd E:\HederaResearch`), and run `git clone https://github.com/hashgraph/hedera-agent-kit-js.git`.
- **Organize:** Create subfolders like `SDKs`, `AI-Kit`, `Docs`.

### Key Hedera Resources to Fetch
Focus on SDKs, AI Agent Kit, and MCP servers for hackathon relevance.

#### Hedera SDKs
- **Overview:** Libraries for interacting with Hedera (accounts, tokens, consensus). Use for understanding dApp building.
- **Fetch:**
  - Docs: Download from [https://docs.hedera.com/hedera/sdks-and-apis/sdks](https://docs.hedera.com/hedera/sdks-and-apis/sdks) (PDF or HTML).
  - JavaScript SDK: Clone [https://github.com/hashgraph/hedera-sdk-js](https://github.com/hashgraph/hedera-sdk-js).
  - Python SDK: Clone [https://github.com/hiero-ledger/hiero-sdk-python](https://github.com/hiero-ledger/hiero-sdk-python).
- **Setup for Research:** In VS Code, open the cloned folder. Use Copilot to explore code (e.g., ask "Explain this token creation function").

#### Hedera AI Agent Kit
- **Overview:** Toolkit for AI agents to use Hedera via natural language. Perfect for non-coders - agents handle transactions.
- **Fetch:**
  - Docs: Download from [https://docs.hedera.com/hedera/open-source-solutions/ai-studio-on-hedera/hedera-ai-agent-kit](https://docs.hedera.com/hedera/open-source-solutions/ai-studio-on-hedera/hedera-ai-agent-kit).
  - Repo: Clone [https://github.com/hashgraph/hedera-agent-kit-js](https://github.com/hashgraph/hedera-agent-kit-js).
  - Template: Clone [https://github.com/hedera-dev/template-hedera-agent-kit-nextjs](https://github.com/hedera-dev/template-hedera-agent-kit-nextjs) for examples.
- **Setup for Research:** Open in VS Code. Use Copilot to query: "How does this agent create a token?" or run examples locally (follow repo README).

#### MCP Servers
- **Overview:** Model Context Protocol for AI apps to interact with Hedera. Enables AI-assisted research and prototyping.
- **Fetch:**
  - Repo: Clone [https://github.com/hashgraph/hedera-agent-kit-js](https://github.com/hashgraph/hedera-agent-kit-js) (MCP in `modelcontextprotocol/` folder).
  - Docs: From [https://github.com/hashgraph/hedera-agent-kit-js/blob/main/docs/DEVEXAMPLES.md#option-d-try-out-the-mcp-server](https://github.com/hashgraph/hedera-agent-kit-js/blob/main/docs/DEVEXAMPLES.md#option-d-try-out-the-mcp-server).
- **Setup for Research:** Follow the concise guide in the subfolder. Integrate with Cursor or Claude Desktop for AI-driven Hedera queries.

### Track-Specific Research Tips
Tailor your research to your chosen track. Fetch relevant docs and use AI to explore:

- **Onchain Finance & Real-World Assets (RWA):** Research tokenization standards, lending protocols. Fetch HTS docs for asset tokenization. Prompt AI: "Explain how to tokenize real estate on Hedera."
  - Beginner Links: [Token Services Guide](https://docs.hedera.com/guides/sdks/token-services), [RWA Tokenization Example](https://docs.hedera.com/guides/sdks/token-services/tokenize-a-real-world-asset).
- **DLT for Operations:** Focus on consensus services for data integrity. Fetch supply chain examples. Prompt AI: "How can Hedera consensus improve healthcare data security?"
  - Beginner Links: [Consensus Service Guide](https://docs.hedera.com/guides/sdks/consensus-service), [Supply Chain Tutorial](https://docs.hedera.com/guides/sdks/consensus-service/submit-a-message).
- **Immersive Experiences (Gaming & NFTs):** Explore NFT minting, smart contracts for games. Fetch NFT tutorials. Prompt AI: "Generate ideas for Hedera-based NFT games."
  - Beginner Links: [NFT Minting Guide](https://docs.hedera.com/guides/sdks/token-services/mint-an-nft), [Gaming on Hedera](https://docs.hedera.com/guides/sdks/token-services/create-an-nft-collection).
- **AI & DePIN:** Research AI integration with DePIN. Fetch AI Agent Kit docs. Prompt AI: "How to build AI-powered energy networks on Hedera?"
  - Beginner Links: [AI Agent Kit Docs](https://docs.hedera.com/hedera/open-source-solutions/ai-studio-on-hedera/hedera-ai-agent-kit), [DePIN Overview](https://docs.hedera.com/hedera/open-source-solutions/ai-studio-on-hedera).

## Using Tools for Research
- **GitHub Copilot in VS Code:** Open fetched code/docs. Highlight code and ask Copilot (Ctrl+I) for explanations, e.g., "What does this Hedera consensus service do?" or "Generate a simple token example."
- **Alternatives:** In Cursor, use built-in AI for similar queries. For docs, use browser extensions like ChatGPT for summarizing PDFs.
- **Research Workflow:**
  1. Fetch resources to local.
  2. Open in VS Code/Cursor.
  3. Use AI to ask questions: "How to validate a Hedera idea?" or "Compare SDKs for my project."
  4. Note findings in a doc (e.g., `research_notes.md`).
- **Hedera-Specific Research:** Explore playground at [https://portal.hedera.com/playground](https://portal.hedera.com/playground) for no-code testing. Get a testnet account for free experiments.

## Tips for Non-Coders
- **Start Small:** Focus on one theme (e.g., RWA) and fetch related docs.
- **AI as Guide:** Prompt Copilot: "Research Hedera for [your idea] and suggest next steps."
- **Community:** Join Hedera Discord or forums for questions.
- **Backup:** Sync local folders to GitHub for version control.

## Advanced Research Workflows

### Research Sprint Method (1 Week Plan)

**Day 1-2: Foundation**
- Set up all tools (GitHub, Git, VS Code, Copilot)
- Create testnet account and get free HBAR
- Clone 3 key repos: Hedera SDK, AI Agent Kit, Example projects

**Day 3-4: Deep Dive**
- Read track-specific docs thoroughly
- Run 5+ code examples locally
- Use Copilot to explain every function
- Document 10 key concepts in your own words

**Day 5-6: Experimentation**
- Modify existing examples for your idea
- Test on Hedera testnet
- Break things intentionally to learn
- Ask AI: "What happens if I change X to Y?"

**Day 7: Synthesis**
- Create a technical specification document
- List all Hedera services you'll use
- Identify knowledge gaps
- Plan development phase

### Organizing Your Research Folder

```
E:\HederaResearch\
├── SDKs\
│   ├── hedera-sdk-js\         # JavaScript SDK
│   ├── hedera-sdk-python\     # Python SDK
│   └── examples\              # Your test code
├── AI-Agent-Kit\
│   ├── hedera-agent-kit-js\  # Main kit
│   ├── templates\             # Next.js templates
│   └── my-experiments\        # Your tests
├── Docs\
│   ├── official\              # Hedera docs (PDFs)
│   ├── tutorials\             # Community guides
│   └── notes.md              # Your research notes
├── Examples\
│   ├── tokens\                # HTS examples
│   ├── consensus\             # Consensus examples
│   └── smart-contracts\       # Solidity examples
└── MyProject\
    ├── research\              # Project-specific research
    ├── prototypes\            # Early tests
    └── final\                 # Working code
```

### Creating Effective Research Notes

**Template for `notes.md`:**

```markdown
# Hedera Research Notes

## Date: [Today's Date]

### Concept Learned
- **What**: Hedera Token Service (HTS)
- **Why**: Create tokens without smart contracts
- **How**: Use TokenCreateTransaction API
- **When to use**: For most token needs (cheaper than contracts)

### Code Snippet Tested
```javascript
// Paste working code here
```

### Questions for AI/Community
1. How does HTS handle token burning?
2. Can I batch token transfers?

### Resources Referenced
- [Link 1]
- [Link 2]

### Next Steps
- [ ] Test token transfer
- [ ] Read about NFT minting
```

## Troubleshooting Common Issues

### GitHub/Git Issues

**Problem:** "git: command not found"  
**Solution:** Reinstall Git from [https://git-scm.com/downloads](https://git-scm.com/downloads). Restart terminal after installation.

**Problem:** "Permission denied (publickey)"  
**Solution:** Use HTTPS instead of SSH for cloning. Use `git clone https://...` not `git clone git@...`

**Problem:** "Repository not found"  
**Solution:** Check repo URL. Ensure it's public. Try GitHub Desktop for easier cloning.

### VS Code Issues

**Problem:** Copilot not suggesting code  
**Solution:** 
1. Check Copilot subscription is active
2. Sign in to GitHub account in VS Code
3. Enable Copilot in Settings > Extensions > Copilot
4. Reload VS Code (Ctrl+Shift+P > "Reload Window")

**Problem:** Extensions not installing  
**Solution:** 
1. Check internet connection
2. Disable antivirus temporarily
3. Use "Install from VSIX" if marketplace fails

### Hedera Testnet Issues

**Problem:** "Insufficient funds" error  
**Solution:** Get more free test HBAR from [Hedera Portal](https://portal.hedera.com/dashboard). Limit: 10,000 test HBAR per account.

**Problem:** "Invalid account ID"  
**Solution:** 
1. Format must be 0.0.xxxxx (e.g., 0.0.12345)
2. Check for typos in `.env` file
3. Ensure account exists on testnet (not mainnet)

**Problem:** Transactions failing silently  
**Solution:** 
1. Add error handling: `try/catch` blocks
2. Check console logs
3. Use Hashscan testnet explorer: [https://hashscan.io/testnet](https://hashscan.io/testnet)
4. Verify account has HBAR balance

### Node.js/NPM Issues

**Problem:** "npm: command not found"  
**Solution:** Install Node.js v20+ from [https://nodejs.org](https://nodejs.org). Choose LTS version. Restart terminal.

**Problem:** "EACCES" permission errors  
**Solution:** 
- Windows: Run terminal as Administrator
- Never use `sudo npm` – fix permissions instead

**Problem:** Package installation fails  
**Solution:** 
1. Clear npm cache: `npm cache clean --force`
2. Delete `node_modules` and `package-lock.json`
3. Run `npm install` again
4. Check Node.js version: `node --version` (should be 20+)

## Advanced AI Research Techniques

### Multi-Model Approach
Don't rely on one AI tool - compare responses:

1. **Ask ChatGPT**: "Explain Hedera Consensus Service"
2. **Ask Claude**: Same question
3. **Ask Copilot**: In code context
4. **Compare answers**: Find common explanations
5. **Verify**: Check official Hedera docs

### Prompt Engineering for Research

**Basic Prompt:**
"What is Hedera Token Service?"

**Better Prompt:**
"Explain Hedera Token Service to a beginner. Include: 1) What it does, 2) When to use it vs smart contracts, 3) A simple JavaScript example for creating a fungible token. Assume I'm building for the Africa Hackathon RWA track."

**Best Prompt:**
"I'm a non-coder building a tokenized farmland platform for the Hedera Africa Hackathon. I need to understand Hedera Token Service deeply. Explain:
1. Core concepts in simple terms
2. Difference between HTS and ERC-20 tokens
3. Step-by-step guide to create a token representing 1 acre of farmland
4. How to handle fractional ownership
5. Code example with comments explaining each line
6. Common pitfalls and how to avoid them
Provide links to official docs for each point."

### Research Validation Checklist

☐ Verified information in official Hedera docs  
☐ Tested code examples locally  
☐ Understood at least 70% of technical concepts  
☐ Created personal notes in simple language  
☐ Identified 3+ relevant Hedera services for my project  
☐ Joined community and asked 1+ questions  
☐ Cloned and ran 2+ example projects  
☐ Ready to move to development phase  

## Track-Specific Deep Dive Resources

### For Onchain Finance & RWA Track
**Must-Read Docs:**
- [Token Service Complete Guide](https://docs.hedera.com/guides/sdks/token-services)
- [RWA Tokenization Example](https://docs.hedera.com/guides/sdks/token-services/tokenize-a-real-world-asset)
- [Account Management](https://docs.hedera.com/guides/sdks/accounts)

**Clone These Repos:**
```bash
git clone https://github.com/hashgraph/hedera-sdk-js.git
cd hedera-sdk-js/examples/token-service
```

**AI Research Prompts:**
- "Design a token structure for tokenizing African farmland"
- "How to implement fractional ownership with Hedera HTS?"
- "Create a lending protocol smart contract on Hedera"

### For DLT for Operations Track
**Must-Read Docs:**
- [Consensus Service Guide](https://docs.hedera.com/guides/sdks/consensus-service)
- [Supply Chain Examples](https://docs.hedera.com/guides/sdks/consensus-service/submit-a-message)
- [File Service for Documents](https://docs.hedera.com/guides/sdks/file-service)

**Clone These Repos:**
```bash
git clone https://github.com/hashgraph/hedera-sdk-js.git
cd hedera-sdk-js/examples/consensus-service
```

**AI Research Prompts:**
- "Design a supply chain tracking system using Hedera Consensus"
- "How to encrypt healthcare records on Hedera?"
- "Build a donation transparency platform with HCS"

### For Immersive Experience Track
**Must-Read Docs:**
- [NFT Creation Guide](https://docs.hedera.com/guides/sdks/token-services/create-an-nft-collection)
- [Minting NFTs](https://docs.hedera.com/guides/sdks/token-services/mint-an-nft)
- [NFT Metadata Standards](https://docs.hedera.com/guides/sdks/token-services/nft-metadata-standard)

**Clone These Repos:**
```bash
git clone https://github.com/hashgraph/hedera-sdk-js.git
cd hedera-sdk-js/examples/nft
```

**AI Research Prompts:**
- "Create an NFT game economy on Hedera"
- "How to implement play-to-earn mechanics with HTS?"
- "Design NFT metadata for African cultural art"

### For AI & DePIN Track
**Must-Read Docs:**
- [AI Agent Kit Complete Docs](https://docs.hedera.com/hedera/open-source-solutions/ai-studio-on-hedera/hedera-ai-agent-kit)
- [MCP Server Setup](https://github.com/hashgraph/hedera-agent-kit-js/blob/main/docs/DEVEXAMPLES.md)
- [Smart Contracts for Complex Logic](https://docs.hedera.com/guides/sdks/smart-contracts)

**Clone These Repos:**
```bash
git clone https://github.com/hashgraph/hedera-agent-kit-js.git
cd hedera-agent-kit-js/examples
```

**AI Research Prompts:**
- "Integrate AI with Hedera for energy grid management"
- "Design a DePIN network for decentralized internet access"
- "Build an AI-powered IoT device network on Hedera"

## Next Steps
With research complete and resources organized, move to [Development](../development/). Use fetched resources and notes to guide AI agents in building your prototype. Your research phase should give you:

1. ✅ Understanding of 3+ Hedera services
2. ✅ Working local development environment
3. ✅ Cloned repos and running examples
4. ✅ Technical specification for your project
5. ✅ Community connections for support

For full docs, refer to Hedera's site: [https://docs.hedera.com](https://docs.hedera.com).