# PulseFolio

Track your portfolio value across **PulseChain** and **Ethereum** — no sign-up, no backend, no wallet address ever leaves your browser. Just paste an address (or a few) and the app queries the blockchain directly.

🔗 **Demo:** just open `index.html` in your browser — the whole app is a single HTML file.

![status](https://img.shields.io/badge/status-active-brightgreen) ![license](https://img.shields.io/badge/license-MIT-blue)

---

## ✨ Features

- **Token balances** — native token (PLS / ETH) plus a list of popular tokens (WPLS, PLSX, HEX, USDC, USDT, DAI, WBTC and more), fetched in bulk via Multicall3 (with a fallback to individual RPC calls).
- **USD pricing** — prices and 24h changes pulled from DexScreener, no API key required.
- **Farms & staking** — automatic detection of:
  - **HEX** stakes (principal, days remaining, progress),
  - **PulseX MasterChef** LP farm positions, broken down into their underlying tokens.
- **Multiple addresses at once** — add as many wallets as you like; the app sums balances into a single view.
- **PulseChain, Ethereum, or both at once** — the network switcher next to the portfolio value lets you view PulseChain, Ethereum, or a combined "PulseChain + Ethereum" view, with badges showing which network each token/farm came from.
- **Custom tokens** — missing a token from the list? Add it by contract address; it's saved locally in your browser.
- **ATH Dream 🚀** — see what your portfolio would be worth at each token's historical all-time-high price.
- **Multiplier ✖️** — recalculate your portfolio at any price multiplier (e.g. "what if prices went 10x").
- **Farm display mode** — show farm tokens separately or merge them into the rest of your portfolio.
- **Caching & instant preview** — the last loaded portfolio snapshot is saved to `localStorage` and shown instantly on your next visit (with a "Cached data — refreshing…" indicator) while fresh data loads in the background. If the refresh fails, the app doesn't wipe the view — it keeps showing the cached data along with an error notice.
- **100% local** — wallet addresses, custom tokens, selected network, and the portfolio cache are stored only in your browser's `localStorage`. Nothing is sent to or stored on any server besides public blockchain RPCs/APIs.

## 🚀 Quick start

No build step, no dependencies to install.

```bash
git clone https://github.com/<your-user>/pulsefolio.git
cd pulsefolio
```

Then just open `index.html` in your browser (double-click works fine), or spin up a lightweight static server, e.g.:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

Paste a wallet address (`0x…`), hit **Check** — done.

## 🛠️ Tech stack

- Plain **HTML + CSS + JavaScript** (no framework, no bundler)
- [ethers.js v5](https://docs.ethers.org/v5/) — talking to RPCs (balances, ERC-20 contracts, MasterChef, HEX)
- [Multicall3](https://www.multicall3.com/) — batching token balance calls into a single RPC request
- [DexScreener API](https://docs.dexscreener.com/) — prices and 24h changes
- [Tabler Icons](https://tabler.io/icons) — UI icons
- Google Fonts (Space Grotesk + Inter)

Public RPCs used by default:

| Network | RPC |
|---|---|
| PulseChain | `rpc.pulsechain.com`, `rpc.pulsechainstats.com` |
| Ethereum | public RPC configured in the code |

## 📁 Project structure

```
.
├── index.html   # the entire app — HTML, CSS and JS in a single file
└── README.md
```

## 🔒 Privacy

- No accounts, no login, no backend.
- Wallet addresses and manually added tokens are stored **only in your browser's `localStorage`** — never sent to or saved on any server.
- The only network traffic is requests to public blockchain RPCs and to DexScreener for pricing.

## 🗺️ Possible roadmap

- [ ] Additional EVM networks (e.g. BNB Chain, Base)
- [ ] Export portfolio to CSV
- [ ] Portfolio value chart over time
- [ ] Price change notifications

## 🤝 Contributing

Pull requests and issues are welcome. If you'd like to add support for a new token, farm, or network, open an issue describing it or go ahead and send a PR.

## 📄 License

Released under the [MIT](LICENSE) license.
