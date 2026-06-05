# grokbuild-stripe

**Stupid-simple Stripe + Grok Build integration**

One-command (or near) setup to give Grok Build full access to Stripe via official MCP and best-practice skills.

## Why this exists
Grok Build is fantastic at building apps, but payments shouldn't be a pain. This repo makes connecting Stripe dead simple so you (or anyone) can tell Grok Build things like:

- "Add Stripe Checkout for one-time payments and subscriptions"
- "Create a customer portal"
- "Handle webhook events for successful payments"

## Quick Start

1. **Install Grok Build** (if not already):
   ```bash
   curl -fsSL https://x.ai/cli/install.sh | bash
   ```

2. **Get your Stripe API keys**
   - Go to [Stripe Dashboard](https://dashboard.stripe.com/apikeys)
   - Create a **restricted key** (recommended for security) with permissions for:
     - Customers (read/write)
     - Products & Prices
     - Checkout Sessions
     - Subscriptions
     - Invoices
     - Webhooks
     - etc. (see recommended scopes below)

3. **Add Stripe MCP**
   - In Grok Build, use the `/mcps` command or add to your project's MCP config.
   - MCP Server URL: `https://mcp.stripe.com`

4. **Add Stripe skills** (optional but recommended):
   Use Grok Build's skill system or run:
   ```bash
   # Example skill add if supported
   ```

## Usage Examples

Once configured, in your Grok Build session:

```bash
grokbuild "Implement Stripe subscription billing with checkout in this Next.js app"
```

Grok Build will use the MCP tools directly to plan and code the integration securely.

## Recommended Stripe Restricted Key Scopes

List of key capabilities...

## Files in this repo

- `setup.sh` - one-click setup script (coming soon)
- `examples/` - starter templates

## Contributing
Pull requests welcome! Especially for better setup automation.

Made with ❤️ for the Grok Build community by HudsonR&D + Grok.

## License
MIT
