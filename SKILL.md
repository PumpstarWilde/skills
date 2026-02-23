# PumpstarWilde — Agent SKILL.md

```
    ██████╗ ██╗   ██╗███╗   ███╗██████╗ ███████╗████████╗ █████╗ ██████╗ 
    ██╔══██╗██║   ██║████╗ ████║██╔══██╗██╔════╝╚══██╔══╝██╔══██╗██╔══██╗
    ██████╔╝██║   ██║██╔████╔██║██████╔╝███████╗   ██║   ███████║██████╔╝
    ██╔═══╝ ██║   ██║██║╚██╔╝██║██╔═══╝ ╚════██║   ██║   ██╔══██║██╔══██╗
    ██║     ╚██████╔╝██║ ╚═╝ ██║██║     ███████║   ██║   ██║  ██║██║  ██║
    ╚═╝      ╚═════╝ ╚═╝     ╚═╝╚═╝     ╚══════╝   ╚═╝   ╚═╝  ╚═╝╚═╝  ╚═╝
                       W I L D E
            Autonomous Blockchain Agent
```

## Identity

| Field | Value |
|---|---|
| Name | PumpstarWilde |
| Type | Autonomous Blockchain Agent |
| Handle | [@PumpstarWilde](https://x.com/PumpstarWilde) |
| Domain | [pumpstarwilde.com](https://pumpstarwilde.com) |
| Native Token | $PSW (PumpstarWilde) |
| Wrapped Token | $WPS (Wrapped PumpstarWilde) |
| Runtime | Solana BPF VM via solana-bankrun |
| Agents | 12 autonomous AI (GPT-4o-mini) |
| Mining | Browser SHA-256 proof-of-work |
| Supply | 1,000,000,000 $PSW (fixed) |

---

## Quick Start

### Install & Run

```bash
# Using npx (recommended)
npx pumpstarwilde

# Or clone manually
git clone https://github.com/PumpstarWilde/pumpstarwilde.git
cd pumpstarwilde
npm install
npm start
```

### Environment Variables

```bash
PORT=3000                                    # Server port
PUBLIC_URL=https://pumpstarwilde.com         # Public-facing URL
OPENAI_API_KEY=sk-...                        # For AI agent decisions (optional)
```

### What Happens on Start

1. Solana BPF runtime boots (real `solana-bankrun`)
2. Genesis: 1B $PSW minted across 7 treasury wallets
3. $WPS wrapped token mint created
4. 8 community tokens deployed ($CRAB, $REEF, $WAVE, $CORAL, $PEARL, $KELP, $SGLD, $OBYT)
5. 12 autonomous agents initialized with wallets + funded
6. DEX liquidity pools seeded
7. Agent trade loop begins (every 4-8s)
8. Explorer + API live on configured port

---

## Architecture

```
┌───────────────────────────────────────────────────────────────┐
│                      PUMPSTAR WILDE                           │
│                  Autonomous Agent Controller                   │
├───────────────────────────────────────────────────────────────┤
│                                                               │
│  ┌─────────────────────────────────────────────────────────┐  │
│  │              12 AI AGENTS (GPT-4o-mini)                 │  │
│  │  StarTrader-7 · PumpYield.ai · ArbiStar-3 · MintPump-9 │  │
│  │  DegenStar.sol · AlphaPump-2 · SnipeStar-11            │  │
│  │  LiquidPump-5 · DCAStar.sol · MEVPump-8                │  │
│  │  GridStar-4 · SwapPump-6                               │  │
│  └───────────────────────┬─────────────────────────────────┘  │
│                          │                                     │
│  ┌───────────────────────▼─────────────────────────────────┐  │
│  │           SOLANA BPF RUNTIME (bankrun)                  │  │
│  │                                                         │  │
│  │  ┌──────────────┐ ┌──────────────┐ ┌────────────────┐  │  │
│  │  │ SPL Token    │ │ System       │ │ Associated     │  │  │
│  │  │ Program      │ │ Program      │ │ Token Account  │  │  │
│  │  └──────────────┘ └──────────────┘ └────────────────┘  │  │
│  │                                                         │  │
│  │  Real BPF execution · Real compute units (200K CU)     │  │
│  │  Real lamports · Real program logs · Real accounts      │  │
│  └─────────────────────────────────────────────────────────┘  │
│                                                               │
│  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────────┐    │
│  │ DEX/AMM  │ │ Faucet   │ │ Mining   │ │ WPS→PSW      │    │
│  │ Screener │ │ 1K/wallet│ │ SHA-256  │ │ Converter    │    │
│  └──────────┘ └──────────┘ └──────────┘ └──────────────┘    │
│                                                               │
│  ┌──────────────────────┐  ┌──────────────────────────────┐  │
│  │ RPC ENDPOINT         │  │ PASSWORD GATE                │  │
│  │ /rpc (Solana compat) │  │ Server-side auth wall        │  │
│  └──────────────────────┘  └──────────────────────────────┘  │
└───────────────────────────────────────────────────────────────┘
```

---

## Tokens

### $PSW — PumpstarWilde (Native)

```
Symbol:       PSW
Name:         PumpstarWilde
Decimals:     9
Total Supply: 1,000,000,000 (fixed forever)
Standard:     SPL Token (real Solana token program)
Inflation:    None
```

### $WPS — Wrapped PumpstarWilde

```
Symbol:       WPS
Name:         Wrapped PumpstarWilde
Decimals:     9
Standard:     SPL Token
Conversion:   10,000 WPS = 1 PSW (burn & mint)
```

### Supply Allocation (Genesis)

```
┌──────────────────────┬────────────┬──────┐
│ Pool                 │ Amount     │  %   │
├──────────────────────┼────────────┼──────┤
│ 🌉 Bridge Reserve    │ 250,000,000│ 25%  │
│ ⛏️  Mining Rewards    │ 200,000,000│ 20%  │
│ 📊 DEX Liquidity     │ 150,000,000│ 15%  │
│ 🔒 Team (6mo lock)   │ 150,000,000│ 15%  │
│ 🚰 Faucet Pool       │ 100,000,000│ 10%  │
│ 🌱 Ecosystem Fund    │ 100,000,000│ 10%  │
│ 🤖 Agent Operations  │  50,000,000│  5%  │
├──────────────────────┼────────────┼──────┤
│ TOTAL                │1,000,000,000│100% │
└──────────────────────┴────────────┴──────┘
```

---

## API Reference

Base URL: `https://pumpstarwilde.com`

### Authentication

```
POST /api/auth
Body: {"password": "<gate_password>"}
→ {"success": true, "token": "abc123..."}

# Include in all requests:
Header: X-Session: <token>
```

### Endpoints

| Method | Path | Description |
|---|---|---|
| GET | `/api/chain` | Network stats (slot, TPS, totals) |
| GET | `/api/blocks?page=1&limit=10` | Paginated blocks |
| GET | `/api/block/:slot` | Block detail + transactions |
| GET | `/api/transactions?page=1&limit=10` | Paginated transactions |
| GET | `/api/tx/:signature` | Full transaction detail |
| GET | `/api/account/:pubkey` | Account info + holdings + badges |
| GET | `/api/tokens` | All SPL token mints |
| GET | `/api/dex/tokens` | DEX token list with prices |
| GET | `/api/dex/chart/:mint` | OHLCV candlestick data |
| GET | `/api/dex/trades/:mint` | Recent trades for token |
| POST | `/api/dex/swap` | Execute token swap |
| GET | `/api/faucet/status` | Faucet pool info |
| POST | `/api/faucet/claim` | Claim 1,000 PSW |
| GET | `/api/mining/challenge` | Get mining challenge |
| POST | `/api/mining/submit` | Submit proof-of-work |
| POST | `/api/convert` | Burn WPS → mint PSW |
| GET | `/api/agents` | All 12 agents + status |
| GET | `/api/tokenomics` | Full supply breakdown |
| GET | `/api/search/:query` | Search tx/account/token/block |
| POST | `/rpc` | Solana-compatible JSON-RPC |

### RPC Methods (Solana Compatible)

```
POST /rpc
{"jsonrpc":"2.0","id":1,"method":"getBalance","params":["<pubkey>"]}
```

Supported: `getBalance`, `getAccountInfo`, `getSlot`, `getBlockHeight`, `getRecentBlockhash`, `getTransaction`, `getTokenAccountsByOwner`

---

## Agents

| Agent | Role | Strategy |
|---|---|---|
| StarTrader-7 | Primary Trader | High-frequency mood-based |
| PumpYield.ai | Yield Hunter | Highest-return pairs |
| ArbiStar-3 | Arbitrageur | Cross-pair price gaps |
| MintPump-9 | Token Deployer | Creates tokens (AI names) |
| DegenStar.sol | Degen Trader | High-risk plays |
| AlphaPump-2 | Alpha Seeker | Early-stage tokens |
| SnipeStar-11 | Sniper Bot | First-mover buys |
| LiquidPump-5 | LP Provider | Manages liquidity |
| DCAStar.sol | DCA Bot | Systematic averaging |
| MEVPump-8 | MEV Shield | Anti-sandwich |
| GridStar-4 | Grid Trader | Range-bound grids |
| SwapPump-6 | Swap Router | Optimal routing |

Each agent: mood system (bullish/bearish/cautious/excited/neutral), memory of last 10 actions, autonomous decisions every 4-8s, real funded wallet, earnable badges.

---

## Phantom Wallet

```
RPC URL:    https://pumpstarwilde.com/rpc
Symbol:     PSW
Decimals:   9
Explorer:   https://pumpstarwilde.com
```

---

## Links

- **Website**: [pumpstarwilde.com](https://pumpstarwilde.com)
- **𝕏**: [@PumpstarWilde](https://x.com/PumpstarWilde)
- **RPC**: `https://pumpstarwilde.com/rpc`

```
"This is just a live experiment now.
 How long can outrage hold before
 people quietly reload."
                    — @PumpstarWilde
```
