# Tokyo Charter Bus

Chartered group transport with a driver in and from Tokyo: charter coaches, minibuses and, where published, private cars. Use it to compare vehicles, see the areas served, understand the fare structure and send a quote request on [tokyocharterbus.com](https://tokyocharterbus.com).

This package contains configuration only. It connects your assistant to the public MCP server at `https://tokyocharterbus.com/mcp` (Streamable HTTP, no sign-in, no API key). The server exposes 5 tools:

| Tool | What it does |
|---|---|
| `list_charter_bus_options` | Bus and coach types, the 7-seat private car with driver and add-on cars: seats, luggage, verification status, fixed package prices, and an optional vehicle recommendation for a passenger and suitcase count. |
| `get_service_areas_and_routes` | Areas served from Tokyo with typical facts, approximate distance and drive time, and the page for each. |
| `estimate_charter_bus_price` | Fare structure under Japan's time + distance fare system; a yen reference estimate only when the rate table is verified and all inputs are present, otherwise status 'quote_required'. Never a confirmed price. |
| `create_quote_request` | Sends a quote request to Tokyo Charter Bus staff and returns a request reference. Not a booking; staff reply with a written quotation. |
| `get_quote_status` | Status of an existing quote request; needs the request reference and the e-mail address used for it. |

Four tools are read-only. `create_quote_request` sends a quote request to staff and is called only after the user has reviewed the details, explicitly confirmed sending them and agreed to the privacy policy. Nothing is booked or reserved.

## Install

| Client | Command |
|---|---|
| Claude Code | `/plugin marketplace add dang13021993/tokyocharterbus-plugin` then `/plugin install tokyocharterbus@tokyocharterbus` |
| Gemini CLI | `gemini extensions install https://github.com/dang13021993/tokyocharterbus-plugin` |
| Qwen Code | `qwen extensions install dang13021993/tokyocharterbus-plugin` |
| Kimi Code | `/plugins install https://github.com/dang13021993/tokyocharterbus-plugin` |
| DeepSeek Harness | `dsh plugin --profile <profile> add github:dang13021993/tokyocharterbus-plugin` |
| Any MCP client | Streamable HTTP URL `https://tokyocharterbus.com/mcp` |

## Example prompts

- "We are 30 people with 30 suitcases arriving at Narita. Which bus fits us?"
- "How much is a day trip from Tokyo to Mt. Fuji by charter bus?"
- "Send a quote request for a coach from Haneda to Hakone on 3 April."

## Contact

helo@tokyocharterbus.com · https://tokyocharterbus.com · License: MIT.
