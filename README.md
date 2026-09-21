# AgentAIBASE

A chat app where you talk to an AI agent that can act on the blockchain. You type a request in plain English, and the agent can check balances, move tokens, read prices, and more on **Base Sepolia** (a free test network).

It is built on Coinbase's [AgentKit](https://github.com/coinbase/agentkit) starter template, so it is a good base for your own on-chain agent.

## What the agent can do

- Use its own **CDP smart wallet** (created for you)
- Send and read **ERC-20** tokens, wrap ETH into **WETH**
- Read live prices from the **Pyth** oracle
- Call Coinbase Developer Platform (CDP) APIs, including the testnet faucet
- Pay for APIs with **x402**

## Tech stack

Next.js, TypeScript, Tailwind CSS, LangChain + LangGraph, OpenAI (`gpt-4o-mini`), Coinbase AgentKit, viem, wagmi

## Getting started

You need Node.js 18+, an [OpenAI API key](https://platform.openai.com/api-keys), and a [CDP API key](https://portal.cdp.coinbase.com/).

1. Install dependencies:

   ```sh
   npm install
   ```

2. Create a `.env` file in the project root:

   ```env
   OPENAI_API_KEY=your_openai_key
   CDP_API_KEY_ID=your_cdp_key_id
   CDP_API_KEY_SECRET=your_cdp_key_secret
   CDP_WALLET_SECRET=your_cdp_wallet_secret
   NETWORK_ID=base-sepolia
   ```

   `RPC_URL` and `PAYMASTER_URL` are optional.

3. Start the app and open http://localhost:3000:

   ```sh
   npm run dev
   ```

## Where to change things

| What | File |
| --- | --- |
| Wallet and actions the agent can use | `app/api/agent/prepare-agentkit.ts` |
| AI model and system prompt | `app/api/agent/create-agent.ts` |
| Chat API endpoint | `app/api/agent/route.ts` |
| Chat page | `app/page.tsx` |

## Learn more

- [AgentKit docs](https://docs.cdp.coinbase.com/agentkit/docs/welcome)
- [Next.js docs](https://nextjs.org/docs)
