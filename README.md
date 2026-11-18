# Alexa+ VPS Concierge

Ask for a server the way you would ask a voice assistant, and get a spoken answer back. Comparing VPS plans across providers usually means opening several pricing pages and a spreadsheet. Here you just say *"cheapest VPS with at least 4GB RAM"* or *"best value plan under $10"*, and it picks the best match from 120+ real plans with live prices.

**Live demo:** https://p32929.github.io/alexa-plus-vps-finder/

It was built for the [Build, Ship, Shape: Amazon Developer Hackathon](https://amazonappdev2026.devpost.com/) (Alexa+ track) as a simulated Alexa+ experience. It is one HTML file with no dependencies and no server, so anyone can run it by opening a page.

## Features

1. **Ask in plain words.** RAM, vCPU, budget and provider are picked out of your sentence, for example *"2 vCPU on Vultr"*.
2. **Real, live prices.** It reads the [VPS Price Index](https://p32929.github.io/vps-price-index/), which is rebuilt every day from the providers' own pricing (Vultr, Akamai/Linode, Scaleway and AWS Lightsail).
3. **It talks back.** The answer appears in the chat and is spoken out loud, like Alexa+ would.
4. **Voice input** in Chrome and Edge, or just type.
5. **Nothing to install.** No build step, no packages, no backend.

## How it works

1. You type or say what you need.
2. A small parser (`parseIntent` in `index.html`) pulls out the RAM, vCPU, budget and provider you asked for.
3. It fetches the live plan list and picks the best match.
4. It shows the answer and reads it out loud with the browser's Web Speech API.

## Why "simulated" and not an MCP server

The hackathon's Alexa+ track accepts either a self-hosted MCP server, or *"a simulated Alexa+ experience... built using any AI or agentic tool of their choice, no specific framework, SDK, or MCP-shaped surface required."* This project takes the second path: a small agent loop that runs fully in your browser.

## Run it locally

```bash
git clone https://github.com/p32929/alexa-plus-vps-finder.git
cd alexa-plus-vps-finder
python3 -m http.server 8000
# open http://localhost:8000
```

## Data source

The plans come from `https://p32929.github.io/vps-price-index/plans.json`. It is open to read from any page and needs no key.

## License

MIT. See [LICENSE](./LICENSE).

## Contributing

Contributions are very welcome, thank you! Before you start on a pull request, please open an issue and tell me what you would like to add or change. That way we can agree on it first, and your time is not wasted on something that might not fit. Thanks for helping make Alexa+ VPS Concierge better.

## You might also like

<p><a href="https://openstore.pfay.workers.dev/cards/p32929/0?n=4&amp;repo=alexa-plus-vps-finder"><picture><source media="(prefers-color-scheme: dark)" srcset="https://openstore.pfay.workers.dev/cards/p32929/0.svg?n=4&amp;repo=alexa-plus-vps-finder&amp;theme=dark"><img src="https://openstore.pfay.workers.dev/cards/p32929/0.svg?n=4&amp;repo=alexa-plus-vps-finder&amp;theme=light" width="50%" align="top" alt="More apps by p32929 on OpenStore (1)"></picture></a><a href="https://openstore.pfay.workers.dev/cards/p32929/1?n=4&amp;repo=alexa-plus-vps-finder"><picture><source media="(prefers-color-scheme: dark)" srcset="https://openstore.pfay.workers.dev/cards/p32929/1.svg?n=4&amp;repo=alexa-plus-vps-finder&amp;theme=dark"><img src="https://openstore.pfay.workers.dev/cards/p32929/1.svg?n=4&amp;repo=alexa-plus-vps-finder&amp;theme=light" width="50%" align="top" alt="More apps by p32929 on OpenStore (2)"></picture></a><br><a href="https://openstore.pfay.workers.dev/cards/p32929/2?n=4&amp;repo=alexa-plus-vps-finder"><picture><source media="(prefers-color-scheme: dark)" srcset="https://openstore.pfay.workers.dev/cards/p32929/2.svg?n=4&amp;repo=alexa-plus-vps-finder&amp;theme=dark"><img src="https://openstore.pfay.workers.dev/cards/p32929/2.svg?n=4&amp;repo=alexa-plus-vps-finder&amp;theme=light" width="50%" align="top" alt="More apps by p32929 on OpenStore (3)"></picture></a><a href="https://openstore.pfay.workers.dev/cards/p32929/3?n=4&amp;repo=alexa-plus-vps-finder"><picture><source media="(prefers-color-scheme: dark)" srcset="https://openstore.pfay.workers.dev/cards/p32929/3.svg?n=4&amp;repo=alexa-plus-vps-finder&amp;theme=dark"><img src="https://openstore.pfay.workers.dev/cards/p32929/3.svg?n=4&amp;repo=alexa-plus-vps-finder&amp;theme=light" width="50%" align="top" alt="More apps by p32929 on OpenStore (4)"></picture></a></p>

<p><a href="https://p32929.github.io/share/?repo=alexa-plus-vps-finder"><picture><source media="(prefers-color-scheme: dark)" srcset="https://p32929.github.io/readme/footer-share-dark.svg"><img src="https://p32929.github.io/readme/footer-share-light.svg" width="50%" align="top" alt="Share this project with your friends in one click"></picture></a><a href="https://p32929.github.io/support/"><picture><source media="(prefers-color-scheme: dark)" srcset="https://p32929.github.io/readme/footer-support-dark.svg"><img src="https://p32929.github.io/readme/footer-support-light.svg" width="50%" align="top" alt="If you like my work and want to support me, feel free to support"></picture></a><br><a href="https://openstore.pfay.workers.dev/add"><picture><source media="(prefers-color-scheme: dark)" srcset="https://p32929.github.io/readme/footer-join-dark.svg"><img src="https://p32929.github.io/readme/footer-join-light.svg" width="100%" align="top" alt="Put your own apps on OpenStore: free, your listing lives in your own repo"></picture></a></p>
