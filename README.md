# bricklink-skill

🧱 BrickLink Store API helper/CLI with OAuth 1.0 request signing. Covers orders, store inventory (read + write), catalog, categories, colors, feedback, push notifications, and invoice generation.

An [OpenClaw](https://openclaw.ai) skill.

## Quick Start

```bash
# Set environment variables (or use ~/clawd/bricklink/config.json)
export BRICKLINK_CONSUMER_KEY="..."
export BRICKLINK_CONSUMER_SECRET="..."
export BRICKLINK_TOKEN_VALUE="..."
export BRICKLINK_TOKEN_SECRET="..."

# List recent orders
python3 scripts/bricklink.py get-orders

# Get order details
python3 scripts/bricklink.py get-order 12345678

# Search catalog
python3 scripts/bricklink.py get-item PART 3001
python3 scripts/bricklink.py get-price-guide PART 3001 --color-id 11
```

See [SKILL.md](SKILL.md) for full documentation and all commands.

## Links

- **GitHub**: https://github.com/odrobnik/bricklink-skill
- **ClawHub**: https://www.clawhub.com/skills/bricklink
