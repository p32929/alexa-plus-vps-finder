# Alexa+ VPS Concierge

A **simulated Alexa+ experience** built for the [Build, Ship, Shape: Amazon Developer Hackathon](https://amazonappdev2026.devpost.com/) (Alexa+ track).

Ask it for a server the way you'd ask a voice assistant — *"cheapest VPS with at least 4GB RAM"*, *"2 vCPU on Vultr"*, *"best value plan under $10"* — and it reasons over a **live-priced dataset of 120+ real VPS plans** (Vultr, Akamai/Linode, Scaleway, AWS Lightsail — via [VPS Price Index](https://p32929.github.io/vps-price-index/)) and answers back, out loud, exactly like an Alexa+ agentic skill would.

**Live demo:** https://p32929.github.io/alexa-plus-vps-finder/

## Why "simulated" and not an MCP server

The hackathon's Alexa+ track accepts either a self-hosted MCP server, **or** — the path this project takes — *"a simulated Alexa+ experience... built using any AI or agentic tool of their choice, no specific framework, SDK, or MCP-shaped surface required."* This is that: a small, honest, client-side agentic loop (intent parsing → live data lookup → spoken response) with zero backend, so anyone can run it by opening a static page.

## How it works

1. You type or speak a request.
2. A tiny NLU layer (`parseIntent` in `index.html`) pulls out RAM / vCPU / budget / provider constraints — the "agent reasoning" step.
3. It fetches the live plans dataset and filters/sorts to the best match.
4. It answers in the chat transcript **and speaks the answer out loud** via the Web Speech API — the same modality Alexa+ uses.

No build step, no dependencies, no server. Open `index.html` in any modern browser (Chrome/Edge get voice input too, via `SpeechRecognition`).

## Run it locally

```
git clone https://github.com/p32929/alexa-plus-vps-finder.git
cd alexa-plus-vps-finder
python3 -m http.server 8000
# open http://localhost:8000
```

## Data source

Live JSON: `https://p32929.github.io/vps-price-index/plans.json` — rebuilt daily from providers' own public pricing APIs. This project only reads it (CORS-open, no key needed).

## License

MIT — see [LICENSE](./LICENSE).
