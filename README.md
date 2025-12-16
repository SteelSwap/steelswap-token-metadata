# SteelSwap Token Metadata

Community-maintained metadata for Cardano tokens listed on SteelSwap.

## Structure

```
tokens/
  {policyId}{hexName}.json
schema.json
```

Each token file is named using the concatenation of its policy ID and hex-encoded asset name.

## Token File Format

```json
{
  "policyId": "279c909f348e533da5808898f87f9a14bb2c3dfbbacccd631d927a3f",
  "hexName": "534e454b",
  "name": "Snek",
  "ticker": "SNEK",
  "description": "Project description (max 300 characters)",
  "website": "https://example.com",
  "socials": {
    "twitter": "https://twitter.com/...",
    "discord": "https://discord.gg/...",
    "telegram": "https://t.me/...",
    "github": null,
    "medium": null,
    "reddit": null,
    "youtube": null
  },
  "tags": ["meme", "community"],
  "icon": "data:image/png;base64,...",
  "verified": true
}
```

## Fields

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `policyId` | string | yes | 56-character hex policy ID |
| `hexName` | string | yes | Hex-encoded asset name |
| `name` | string | yes | Full token name |
| `ticker` | string | yes | Trading symbol |
| `description` | string | yes | Project description (max 300 chars) |
| `website` | string/null | no | Primary project URL |
| `socials` | object | no | Social media links (fixed schema) |
| `tags` | string[] | no | Category tags |
| `icon` | string | no | Base64 data URI (PNG/SVG) |
| `verified` | boolean | no | Omit if not verified |

## Available Tags

- `meme` - Meme tokens
- `defi` - DeFi protocols
- `nft` - NFT-related tokens
- `gaming` - Gaming tokens
- `stablecoin` - Stablecoins
- `governance` - Governance tokens
- `utility` - Utility tokens
- `community` - Community-driven projects
- `rwa` - Real world assets
- `ai` - AI-related projects

## Contributing

1. Fork this repository
2. Add your token file to the `tokens/` directory
3. Ensure your file passes schema validation
4. Submit a pull request

## Validation

Validate your token file against the schema:

```bash
npx ajv validate -s schema.json -d tokens/YOUR_TOKEN.json
```
