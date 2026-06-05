# grokbuild-stripe

**Stupid-simple Stripe MCP connector for xAI Grok Build**

Makes it dead easy for Grok Build to work with Stripe payments (checkout, subscriptions, customers, webhooks, etc.) using Stripe's official MCP server.

## Quick Start

1. **Install Grok Build** (beta)
   ```bash
   curl -fsSL https://x.ai/cli/install.sh | bash
   ```

2. **Create Restricted Stripe API Key** (critical for security)
   - Go to [Stripe Dashboard → API keys](https://dashboard.stripe.com/apikeys)
   - Click **+ Create restricted key**
   - Select **"Authorizing an AI agent"** (perfect for MCP/Claude/Cursor/Grok Build)
   - Then configure the following **capabilities** (set to **Write** where needed, **Read** for others, **None** for the rest):

     **Recommended minimum set (enable these):**
     - **Customers** → Write
     - **Products** → Write
     - **Prices** → Write
     - **Checkout Sessions** → Write
     - **Subscriptions** → Write
     - **Invoices** → Write
     - **Payment Intents** → Write
     - **Webhooks** / **Events** → Read + Write (for webhook endpoints)
     - **Payment Methods** → Read/Write (as needed)

     Leave everything else on **None** unless your use case requires it (e.g. Payouts, Disputes, etc.).

3. **Add Stripe MCP to Grok Build**
   - Start Grok Build: `grokbuild` in your project
   - Use `/mcps` (or the MCP manager command) 
   - Add server:
     - **URL**: `https://mcp.stripe.com`
     - **Key**: Paste your new restricted `sk_test_` or `sk_live_` key

4. **(Optional) Add Stripe skills**
   Grok Build may auto-detect or you can add community skills if available.

## Typical Prompts for Grok Build

Once connected:
- `Set up Stripe Checkout for one-time payments and monthly subscriptions`
- `Implement a customer portal with subscription management`
- `Add webhook handling for payment succeeded/failed events`
- `Create a full SaaS billing flow with free trials`

Grok Build will use the MCP tools to generate secure, best-practice code.

## Security Notes
- Always use **restricted keys** scoped only to what you need
- Never commit API keys to Git
- Use `.env` files or your platform's secret manager
- Test thoroughly in Stripe test mode first

## What's next in this repo
- `setup.sh` for automated configuration
- Example apps (Next.js, etc.)
- Pre-packaged skills

Pull requests welcome to make setup even easier!

**Repo**: https://github.com/HudsonR-D/grokbuild-stripe

Made with ❤️ by HudsonR&D + Grok

## License
MIT