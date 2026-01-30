# BrickLink Skill

Helper CLI for the BrickLink Store API (OAuth 1.0). Covers orders, store inventory, and catalog item endpoints.

## Setup
1. Create a BrickLink API consumer key/secret.
2. Create a config file (see `bricklink/config.json.example` in repo root) with keys:
   - `consumer_key`, `consumer_secret`, `token_value`, `token_secret`
3. Run the CLI with `--config` pointing at that file (optional if `~/clawd/bricklink/config.json` exists).

## Usage
```bash
python3 scripts/bricklink.py --config ~/clawd/bricklink/config.json get-orders
python3 scripts/bricklink.py --config ~/clawd/bricklink/config.json get-order 123456
python3 scripts/bricklink.py --config ~/clawd/bricklink/config.json get-notifications
python3 scripts/bricklink.py --config ~/clawd/bricklink/config.json get-categories
python3 scripts/bricklink.py --config ~/clawd/bricklink/config.json get-category 5
python3 scripts/bricklink.py --config ~/clawd/bricklink/config.json get-inventories
python3 scripts/bricklink.py --config ~/clawd/bricklink/config.json get-inventory 987654

# Catalog
python3 scripts/bricklink.py --config ~/clawd/bricklink/config.json get-item part 3001
python3 scripts/bricklink.py --config ~/clawd/bricklink/config.json get-subsets set 7644-1 --instruction true
python3 scripts/bricklink.py --config ~/clawd/bricklink/config.json get-price-guide part 3001 --guide-type stock --new-or-used N --country-code AT
```

## Notes
- Reference docs in `references/`
- `SKILL.md` contains agent usage guidance
