---
name: bricklink
description: BrickLink Store API (OAuth 1.0) helper. Use when calling BrickLink API endpoints for orders, store inventory, or catalog: list/fetch orders, order items/messages/feedback, list/fetch store inventories, fetch catalog items, subsets/supersets, price guide, and known colors (GET /orders..., GET /inventories..., GET /items/{type}/{no}...).
---

# BrickLink

Use `scripts/bricklink.py`.

## Auth config

### Option A (recommended): environment variables

- `BRICKLINK_CONSUMER_KEY`
- `BRICKLINK_CONSUMER_SECRET`
- `BRICKLINK_TOKEN_VALUE`
- `BRICKLINK_TOKEN_SECRET`

### Option B: local config JSON (recommended for convenience)

Create `~/clawd/bricklink/config.json` (example in `~/clawd/bricklink/config.json.example`) and run with:

- `bricklink.py --config ~/clawd/bricklink/config.json ...`

### Option C: parse the saved registration HTML

- `bricklink.py --creds-html "/Users/oliver/Downloads/BrickLink API Consumer Registration | BrickLink.html" ...`

## Commands

Read-only:
- `bricklink.py get-orders [--direction in|out] [--status ...] [--include-status ...] [--exclude-status ...] [--filed true|false]`
- `bricklink.py get-order <order_id>`
- `bricklink.py get-order-items <order_id>`
- `bricklink.py get-order-messages <order_id>`
- `bricklink.py get-order-feedback <order_id>`
- `bricklink.py get-notifications`
- `bricklink.py get-inventories [--item-type ...] [--status ...] [--category-id ...] [--color-id ...]`
- `bricklink.py get-inventory <inventory_id>`
- `bricklink.py get-item <type> <no>`
- `bricklink.py get-supersets <type> <no> [--color-id N]`
- `bricklink.py get-subsets <type> <no> [--color-id N] [--box true|false] [--instruction true|false] [--break-minifigs true|false] [--break-subsets true|false]`
- `bricklink.py get-price-guide <type> <no> [--color-id N] [--guide-type stock|sold] [--new-or-used N|U] [--country-code XX] [--region ...] [--currency-code XXX] [--vat N|Y|O]`
- `bricklink.py get-known-colors <type> <no>`

Mutating (require `--yes`):
- `bricklink.py update-order <order_id> --yes [--json body.json] [--remarks ...] [--is-filed true|false] [--shipping-...] [--cost-...]`
- `bricklink.py update-order-status <order_id> <status> --yes`
- `bricklink.py update-payment-status <order_id> <payment_status> --yes`
- `bricklink.py send-drive-thru <order_id> [--mail-me] --yes`

Utilities:
- `bricklink.py order-detail-html <order_id> [--out path] [--inline-images]`

## References

- Consumer registration HTML: `references/consumer-registration.html`
- API notes (orders): `references/orders-api.md`
- API notes (inventory): `references/inventory-api.md`
- API notes (catalog): `references/catalog-api.md`
