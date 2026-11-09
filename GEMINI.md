# Tokyo Charter Bus

Tools from the `tokyocharterbus` MCP server (https://tokyocharterbus.com/mcp):

| The user wants | Tool |
|---|---|
| Which vehicle fits a group and its suitcases, and the fixed package prices | `list_charter_bus_options` |
| Which areas and routes are served | `get_service_areas_and_routes` |
| A reference estimate for a trip | `estimate_charter_bus_price` |
| Send a quote request (only after explicit confirmation) | `create_quote_request` |
| Status of a quote request already sent | `get_quote_status` |

Rules:
- Use the read-only tools to explain vehicle options, served areas and the fare structure.
- Quote the fixed package prices from `list_charter_bus_options` exactly. A price from `estimate_charter_bus_price` is an estimate only when the tool returns status 'estimate'; otherwise say a written quote is required. Never present a price as confirmed.
- Call `create_quote_request` only after the user has reviewed the details, explicitly confirmed sending them and agreed to the privacy policy (set `user_confirmed` and `privacy_consent` to true).
- A quote request is never a booking. Staff reply with a written quotation; do not say a vehicle is reserved or available.
- Supported locales: en, ja, zh-CN, zh-TW, ko, th, id, fr, de, es, it.
- Contact: helo@tokyocharterbus.com.
