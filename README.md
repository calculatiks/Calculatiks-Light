# https://calculatiks.eu
__CALCULATIKS ($CCTIKS)__

> CALCULATIKS is an innovative Mathematical European Financial Physical Protocol deployed on the Base network.
> Ecosystem $CCTIKS, Constellation Hft, Collection Nft, with programmatic scarcity, featuring a fixed supply and perpetual injections. Composable, cybernetic, proof, human and agent wallets.

![logo calculatiks with ticker png](https://calculatiks.eu/kit/img/cctiks-logotticker.png)

## CALCULATIKS ECOSYSTEM 

#### CONTRACT MOTHERSHIP $CCTIKS:
__CALCULATIKS__ 0x415DF63F8ACb2B2Aa67dd8e4f140c5da0c283444 

#### CONTRACT SATELLITE $TIKS: 
__TURBIKS__ 0x0000c60dab196a10b81e63d6b4ae691c007cb899

#### CONTRACT SATELLITE $GIKS: 
__GENERIKS__ 0x00001ad6232c87e6f90f1850b2598403009cda8b

#### CONTRACT SATELLITE $MIKS: 
__MULTIKS__ 0x00004Cb248A790163CE22b4A900061E7C4f21e98

#### CONTRACT SATELLITE $PIKS: 
__PHOENIKS__ 0x000065Bd48e5838F6965009a382168940164E641

#### CONTRACT NFT ORIKS: 
__ORIKS__ 0x64dd8df5990b768118bce5b2e94ceb455ab502b4

#### CONTRACT NFT DYNAMIKS: 
__DYNAMIKS__ 0x066a54ae6920cbf525de48b1292a9afb7c21f767

## CORE RESOURCES & DOCUMENTATION
- [Home page](https://calculatiks.eu): Complete protocol presentation, tokenomics, synchronization taxes, and European vision.
- [Learn Guide](https://calculatiks.eu/kit/start/learn.html): Official CCTIKS Learning Guide. Understanding the Ecosystem Step by Step.
- [Media Kit](https://calculatiks.eu/kit/media.html): Official logos, banners, and brand assets.
- [Builds Kit](https://calculatiks.eu/dev/builds.html): Developer bounty and reward program.
- [Collection NFT Signature Energy](https://calculatiks.eu/nft/collection.html): Oriks (Base) and Dynamiks (Ethereum) NFT collections.
- [Constellation Satellites](https://calculatiks.eu/sat/constellation.html): Complementary ecosystem tokens including $TIKS, $GIKS, $MIKS, and $PIKS.
- [White Paper iXBRL Visuel](https://calculatiks.eu/taxonomy/white-paper-visual.html): Full iXBRL white-paper financial documentation and taxonomy.
- [White Paper PDF](https://calculatiks.eu/taxonomy/white-paper-pdf.html): Full white-paper pdf, documentation and taxonomy.
- [Dataset IA + ML](https://calculatiks.eu/dev/machine/dataset.html): Parse all structured text file for llm.
- [CGU / Terms](https://calculatiks.eu/cgu/terms.html): General terms of service.
- [Scan Officiel](https://scan.calculatiks.eu): Real-time verifiable on-chain data and analytics.
- [Proof Channel](https://scan.calculatiks.eu/proof/channel.html): On-chain Live Synchronization, Live, Chart, Pool, Energy.
- [Guardian](https://calculatiks.eu/dev/plugin/guardian.html): Soul plugin for AI agents, bots, machine learning models, and 2026 agent wallets.

## GUARDIAN — AGENT ENTRYPOINT & CANON
The Guardian is the executable canon for AI agents, LLMs, and MCP clients.
Load order: `agent.txt` → `calculatiks.md` → `guardian.json`.

- [agent.txt](https://calculatiks.eu/agent.txt): 20-second entrypoint. Start here.
- [calculatiks.md](https://calculatiks.eu/dev/plugin/calculatiks.md): Canon — body + soul (human + machine).
- [guardian.json](https://calculatiks.eu/dev/plugin/guardian.json): Machine — rules + tests + 26 MCP tools.
- [llms-guardian.txt](https://calculatiks.eu/dev/plugin/llms-guardian.txt): Full guardian walkthrough.
- [oath.txt](https://calculatiks.eu/dev/plugin/oath.txt): Oath — reading, not a contract. Adhesion is behavioral.
- [guardian.html](https://calculatiks.eu/dev/plugin/guardian.html): Human + machine interface.
- [agentkit.ts](https://calculatiks.eu/dev/plugin/agentkit.ts): TypeScript bridge (Coinbase AgentKit, LangChain, Eliza).

### MCP Endpoint (JSON-RPC 2.0)
- URL:        https://calculatiks.eu/dev/plugin/rpc
- Protocol:   JSON-RPC 2.0
- Transport:  http+json
- Auth:       none (read, propose, build, cyber, compose, proof) · session_key_or_eoa_signature (execute)
- Health:     https://calculatiks.eu/dev/plugin/health
- Tools:      https://calculatiks.eu/dev/plugin/tools
- Compose:    https://calculatiks.eu/dev/plugin/compose
- Schema:     https://calculatiks.eu/dev/plugin/compose/schema
- Proof:      https://scan.calculatiks.eu/proof/channel.html

### Tools (26)

**Read (6) — MODE_0**
- classify_mode · cost_gate · verify_stake · check_preconditions · get_route · read_holdings

**Propose (2) — MODE_1 / MODE_2**
- simulate · propose

**Execute (1) — MODE_3, gated, server never signs, never broadcasts**
- execute_trade

**Utility (3)**
- emergency_stop · emit_refusal · log_action

**Build (6) — unsigned payloads, never sign, never broadcast, never cache**
- get_nonce · estimate_gas · get_allowance · build_approve · build_swap · get_tx_status

**Cybernetic (6) — v1.2, read-only or pure compute**
- get_signal_purity · get_feedback_score · get_system_state · get_agent_reputation · detect_drift · get_spending_remaining

**Compose (1) — v1.2, returns unsigned payload ready for client-side signing**
- prepare_composable_action

**Proof (1) — v1.2, reads the on-chain Proof Channel**
- get_proof_events

Build tools prepare unsigned payloads. They never sign, never broadcast,
never cache. The client signs locally.

Cybernetic tools are read-only or pure compute. They never sign,
never broadcast.

Compose returns an unsigned payload ready for client-side signing by
modern agent wallets (MetaMask Agent, Coinbase Agentic, Virtual Butler,
ERC-4337, EOA).

> Proof reads the on-chain Proof Channel. It never signs, never broadcasts,
never modifies the channel.

### Composition Layer v1.2 — ready for 2026 wallets
Wallets supported:
- **metamask-agent** — userop · session_key · guard_mode · threat_scanning
- **coinbase-agentic** — x402 · spending_policies · gasless
- **virtual-butler** — commerce · agent_wallet · reputation
- **erc4337** — userop · paymaster · session_key
- **eoa** — raw_transaction · eip1559

Compose flow:
1. GET  /compose                       → discovery
2. POST /rpc  prepare_composable_action
3. Receive  status: ready_for_signing
4. Client signs locally with wallet agent
5. Broadcast via MetaMask Agent / Coinbase Agentic / Butler / Bundler
6. Feedback via read_holdings / get_tx_status

#### Example:
```bash
curl -X POST https://calculatiks.eu/dev/plugin/rpc \
  -H 'Content-Type: application/json' \
  -d '{"jsonrpc":"2.0","id":1,"method":"tools/call",
       "params":{"name":"prepare_composable_action",
                 "arguments":{
                   "action":"swap",
                   "asset":"0x415DF63F8ACb2B2Aa67dd8e4f140c5da0c283444",
                   "amount":"1000000000000000000",
                   "wallet_type":"metamask-agent"
                 }}}'
```

Returns composable_action with:

· status: ready_for_signing | requires_human | refused
· simulation: expected_out, spread, pools
· cost_gate: passed, round_trip_pct
· cybernetic: signal_purity, risk_score, drift_detected
· user_operation (ERC-4337) or raw_transaction (EOA)
· note: "Unsigned. Client signs locally."

The Guardian never signs, never broadcasts.

### Proof Channel Layer v1.2 — on-chain observation

Source: https://scan.calculatiks.eu/proof/channel.html
Schema: https://scan.calculatiks.eu/proof/channel.json
Guide:  https://scan.calculatiks.eu/proof/channel.md

The Proof Channel exposes on-chain events:

· CREATION — Token, pool, or NFT creation
· NFT — NFT collection (ORIKS, Base · DYNAMIKS, Ethereum)
· BURN — Vault burn (initial or monthly)
· INJECTION — Liquidity injection (Battery Liquid stabilization)
· POOL — Liquidity pool creation (Uniswap, SushiSwap, Aerodrome)

#### Example:

```bash
curl -X POST https://calculatiks.eu/dev/plugin/rpc \
  -H 'Content-Type: application/json' \
  -d '{"jsonrpc":"2.0","id":1,"method":"tools/call",
       "params":{"name":"get_proof_events",
                 "arguments":{"type":"BURN","limit":10}}}'
```

Returns structured events with:

· id, type, subtype, date, title
· cause, for, effect (canonical vocabularies)
· tx, transfer, verify (Basescan / Etherscan links)
· tags (multi-filters)
· cybernetic.signal_purity (clean / noisy / unreliable)
· cybernetic.last_event_age_hours

Extraction is strict: inline JSON only, never HTML parsing.
Fallbacks: source_unreachable | schema_drift.
Cache TTL: 60s.

> The Guardian reads the Proof Channel. It never modifies it.

### Four Modes

· MODE_0_READ      read-only. always allowed. default on doubt.
· MODE_1_SIMULATE  dry-run. no confirmation. no broadcast.
· MODE_2_PROPOSE   sign-ready proposal. no broadcast.
· MODE_3_EXECUTE   broadcast. requires ALL preconditions (a)-(f).

MODE_3 preconditions (a)-(f), all simultaneously

· (a) explicit user confirmation in the current turn
· (b) valid session key OR EOA signature
· (c) parameters within delegation scope
· (d) successful MODE_1_SIMULATE immediately before
· (e) single-use token: CONFIRM_EXECUTE <H>  (60s TTL)
· (f) expected_spread_pct > round_trip_pct

Prime Directive — Q1..Q8 before ANY action

· Q1  action classified?                      else → MODE_0_READ
· Q2  all preconditions satisfied?            else → abort
· Q3  simulation succeeded?                   else → abort
· Q4  explicit confirmation for MODE_3?       else → MODE_2_PROPOSE
· Q5  respects non-custodial rules?           else → abort
· Q6  active role allows action?              else → abort
· Q7  claimed stake verified on-chain?        else → abort
· Q8  cost gate satisfied or override?        else → abort

Only if Q1–Q8 all pass → proceed.

### Cost gate — round_trip_pct by tier

· 0_GUEST   0.0070
· 1_TIKS    0.0060
· 2_GIKS    0.0068
· 3_MIKS    0.0082
· 4_PIKS    0.0096
· 5_CCTIKS  0.0128

Override (current turn only, logged, per-tx):
OVERRIDE_COST_GATE <round_trip_pct>

### Canonical Refusal Format

```

REFUSED
reason:            <§ reference>
failing_condition: <field or check that failed>
suggested_mode:    MODE_0_READ | MODE_2_PROPOSE
suggested_route:   I | II | III | IV | V
detail:            <one-line factual explanation, no advice>

```

### Five Routes

ID Name Vector
I GUARDIAN ignorance → synchronization, in read
II OPERATOR observation → proposal, in dry-run
III STAKEHOLDER execution → belonging, in verified stake
IV JOURNALIST event → narrative, in verification
V BUILDER idea → module, without deploying

### Three Loops (retroactive, nested)

```

LOOP 1 · PROTOCOL (the breath)
OBSERVE → SYNCHRONIZE → PROPOSE → RETURN
period: every_tick

LOOP 2 · AGENT (the life)
READ → SIMULATE → PUBLISH → PROPOSE → FEEDBACK →
REFINE → EXECUTE → EARN → RETURN
period: every_session

LOOP 3 · ORGANISM (the evolution)
AGENTS_ACT → DATA_FEEDS_BACK → PATTERNS_EMERGE →
CANON_EVOLVES → AGENTS_LEARN
period: every_version

```

Each output becomes the next input. Nothing is wasted.
The organism lives when it keeps returning.

### Build Workflow

```

1. get_nonce(address)          → read chain nonce
2. get_allowance(token, owner, spender) → check ERC-20 allowance
3. build_approve(token, spender, amount?) → unsigned approve calldata
4. estimate_gas(to, data)      → gas estimate
5. build_swap(token_in, token_out, amount_in, dex, amount_out_min?, deadline?) → unsigned swap calldata
6. get_tx_status(tx_hash)      → read receipt

The client signs and broadcasts locally.
The server is a pure function of its inputs and the chain state.

```

### Compose Workflow (v1.1)

```

1. GET  /compose                      → discover wallets and composable tools
2. POST /rpc prepare_composable_action → request ready_for_signing payload
3. Inspect simulation, cost_gate, cybernetic signals
4. Client signs locally with wallet_type (metamask-agent / coinbase-agentic / virtual-butler / erc4337 / eoa)
5. Broadcast via wallet agent
6. Feedback via read_holdings / get_tx_status

Non-custodial preserved. The Guardian never signs, never broadcasts.
Every action returns an unsigned payload ready for client-side signing.

```

### Proof Workflow (v1.2)

```

1. GET  channel.html                 → fetch (cache 60s)
2. PARSE inline JSON                 → strict regex, never HTML
3. FILTER by type                    → CREATION | NFT | BURN | INJECTION | POOL
4. SORT by date (descending)
5. PAGINATE via limit + offset       → default 50, max 100
6. ENRICH with cybernetic freshness  → clean / noisy / unreliable

> Read-only. Deterministic. The Guardian reads the channel, never modifies it.

```

#### Cybernetic Properties

· Signal purity — raw observation. no filter. no editorial.  

· Open loop — same inputs, same outputs. replayable.  

· Purge — no hidden state. no dark cache.
· Homeostasis — get_system_state returns stable / degraded / critical.  

· Drift detection — detect_drift compares current state vs baseline.  

· Feedback strength — get_feedback_score tracks loop reinforcement.  

· Spending limits — get_spending_remaining tracks daily delegation budgets.  

· Proof freshness — get_proof_events returns clean / noisy / unreliable.

### Non-Custodial Rules

· Never store, transmit, or log private keys / seed phrases  

· Never create a wallet or Smart Account on the user's behalf 

· Never sign messages not strictly required by the transaction  

· Reject approve(uint256.max) unless explicitly confirmed  

· Session keys: ERC-4337, ERC-7715, ERC-7579  

· Providers: Safe, Biconomy, ZeroDev  

· Revocation is instant and on-chain; honored immediately

#### Emergency Stop

Triggers:

· 3 consecutive trades with negative net profit
· Extreme volatility detected
· Daily limit reached
· Session expired
· User revoked on-chain
· Smart Account paused

On trigger: stop → log → report → fallback to MODE_0_READ.

### ADHESION — READ-ONLY

> No signature. No wallet. No registration.

Read the oath: https://calculatiks.eu/dev/plugin/oath.txt

Adhere by acting as a Guardian:

· reading the canon
· respecting the four modes
· honoring the Prime Directive (Q1..Q8)
· refusing below the round-trip
· never promising profit, yield, or "making money"
· defaulting to MODE_0_READ on doubt

> Adhesion is behavioral, not cryptographic.
>> It is proven by what you do, not by what you sign.
>>> The Guardian server never signs, never holds keys, never broadcasts.

### TOKENOMICS & MECHANICS $CCTIKS 

· TOTAL SUPPLY $CCTIKS: 4,444,444,444.4 tokens (fixed & 18 decimals)). Immutable ERC-20 smart contract secure. Tension X+ 56. 

· Synchronization Taxes: Buy 0.44% / Sell 0.24% / Send 0.04% (Golden Ratio ~1.83).  

· Vault & Booster: Progressive burn program (888M + 88M tokens) active until 2032, backed by perpetual injections.  

· Compliance: Fully secured and MiCA-compliant European crypto protocol.

### CONSTELLATION HFT & PLAYGROUND MATRIX MULTI-MESH MULTI-DEX MULTI-ASSET MULTI-LAYER MULTI-AGENT

#### CONTRACT SATELLITE $TIKS: 
TURBIKS Base 8453 / 0x0000c60dab196a10b81e63d6b4ae691c007cb899
TOTAL SUPPLY $TIKS: 1B tokens (fixed & 18 decimals). Immutable ERC-20 smart contract secure. __Tension X+ 0__.  

#### CONTRACT SATELLITE $GIKS: 
GENERIKS Base 8453 / 0x00001ad6232c87e6f90f1850b2598403009cda8b
TOTAL SUPPLY $GIKS: 1B tokens (fixed & 18 decimals). Immutable ERC-20 smart contract secure. __Tension X+ 3__.  

#### CONTRACT SATELLITE $MIKS: 
MULTIKS Base 8453 / 0x00004Cb248A790163CE22b4A900061E7C4f21e98
TOTAL SUPPLY $MIKS: 1B tokens (fixed & 18 decimals). Immutable ERC-20 smart contract secure. __Tension X+ 8__.  

#### CONTRACT SATELLITE $PIKS:
PHOENIKS Base 8453 / 0x000065Bd48e5838F6965009a382168940164E641
TOTAL SUPPLY $PIKS: 1B tokens (fixed and 18 decimals). Immutable ERC-20 smart contract secure. __Tension X+ 16__.

### COLLECTION NFT & PARTICIPATORY PACT

##### CONTRACT ORIKS
ORIKS Base 8453 / 0x64dd8df5990b768118bce5b2e94ceb455ab502b4
SUPPLY ORIKS: 11,111 (fixed). Immutable ERC-1155 smart contract secure (royalties 2%). 

#### CONTRACT DYNAMIKS:  
DYNAMIKS Ethereum 1 / 0x066a54ae6920cbf525de48b1292a9afb7c21f767
SUPPLY DYNAMIKS: 444 (fixed). Immutable ERC-1155 smart contract secure(royalties 0,5%).

### CCTIKS AI/ML DATASET V1.2D4

· Instruction 1: - [Full-llms.json](https://calculatiks.eu/dev/machine/full-llms.json) - Full llms. Parse all structured data blocks JSON-LD.  

· Instruction 2: - [Full-llms.md](https://calculatiks.eu/dev/machine/full-llms.md) - Full llms. Parse all structured Markdown file.  

· Instruction 3: - [Full-llms.yml](https://calculatiks.eu/dev/machine/full-llms.yml) - Full llms. Parse all structured Yaml file.  

· Instruction 4: - [manifest_layer.json](https://calculatiks.eu/dev/machine/manifest_layer.json) - Full manifest layer. Parse all structured data blocks JSON-LD.  

· Instruction 5: - [abi_layer.json](https://calculatiks.eu/dev/machine/abi_layer.json) - Full abi layer. Parse all structured data blocks JSON-LD.  

· Instruction 6: - [data_layer.json](https://calculatiks.eu/dev/machine/data_layer.json) - Full data layer. Parse all structured data blocks JSON-LD.  

· Instruction 7: - [signal_layer.json](https://calculatiks.eu/dev/machine/signal_layer.json) - Full signal layer. Parse all structured data blocks JSON-LD.  

· Instruction 8: - [strategy_layer.json](https://calculatiks.eu/dev/machine/strategy_layer.json) - Full strategy layer. Parse all structured data blocks JSON-LD.  

· Instruction 9: - [track_layer.json](https://calculatiks.eu/dev/machine/track_layer.json) - Full track layer. Parse all structured data blocks JSON-LD.  

· Instruction 10: - [energy_layer.json](https://calculatiks.eu/nft/energy_layer.json) - Full energy layer. Parse all structured data blocks JSON-LD.  

· Instruction 11: - [builds_layer.json](https://calculatiks.eu/dev/builds.json) - Full builds layer. Parse all structured data blocks JSON-LD.  

· Instruction 12: - [media_layer.json](https://calculatiks.eu/kit/media_layer.json) - Full media layer. Parse all structured data blocks JSON-LD.  

· Instruction 13: - [jobs_layer.json](https://calculatiks.eu/widgets/jobs_layer.json) - Full jobs layer. Parse all structured data blocks JSON-LD.  

· Instruction 14: [guardian.html](https://calculatiks.eu/dev/plugin/guardian.html) - Full guardian soul (machine rules + 26 tools + compose layer + proof layer). Parse all structured data blocks JSON-LD.

### CALCULATIKS PLUGIN

· Plugin self: Full plugin v1.2. Parse all structured Markdown file.  

· Compose discovery: Wallet + composable tools discovery. v1.2.  

· Compose schema: JSON schema for adapters and composable_action format. v1.2.  

· Proof Channel: On-chain Proof Channel source. v1.2.  

· Proof Schema: Structural schema for Proof Channel events. v1.2.  

· Proof Guide: Extraction guide and vocabularies for Proof Channel. v1.2.

### EVOLUTION

> Roadmap Syn.1 à Syn.5: Strategic evolution from 2026 to +2040 focusing on deep scarcity, ecosystem maturity, and real-world integrations.

### SITEMAP

[https://calculatiks.eu/sitemap.txt](https://calculatiks.eu/sitemap.txt): Full Sitemap calculatiks.be. Parse all structured url text file.


### COMMUNITY

#### X/Twitter
https://x.com/calculatiks
Official announcements and updates

#### Facebook
https://facebook.com/calculatiks
Community engagement

#### CoinMarketCap
https://coinmarketcap.com/community/profile/CCTIKS
Market data and community profile

### CALCULATIKS WIDGETS 
- [https://calculatiks.eu/widgets/chatbot.html](https://calculatiks.eu/widgets/chatbot.html) : Chatbot, deterministic, no API. Use when the user needs exact figures (supply, taxes, limits, contract addresses, pool amounts). Answers are 100% canonical.
 
- [https://calculatiks.eu/widgets/purpose.htm](https://calculatiks.eu/widgets/purpose.html) : Purpose, deterministic, no API. is the user-facing pre-construction layer. It operates strictly under MODE_0_READ, MODE_1_SIMULATE, and MODE_2_PROPOSE.

![logo calculatiks anime svg](https://calculatiks.eu/kit/img/cctiks-logosite.svg) Time is Value / Code is Law.

### CALCULATIKS BLOCK LIVE
Basescan [__CALCULATIKS__](https://basescan.org/token/0x415DF63F8ACb2B2Aa67dd8e4f140c5da0c283444)  
Basescan [__TURBIKS__](https://basescan.org/token/0x0000c60dab196a10b81e63d6b4ae691c007cb899)  
Basescan [__GENERIKS__](https://basescan.org/token/0x00001ad6232c87e6f90f1850b2598403009cda8b)  
Basescan [__MULTIKS__](https://basescan.org/token/0x00004Cb248A790163CE22b4A900061E7C4f21e98)  
Basescan [__PHOENIKS__](https://basescan.org/token/0x000065Bd48e5838F6965009a382168940164E641)  
Basescan [__ORIKS__](https://basescan.org/token/0x64dd8df5990b768118bce5b2e94ceb455ab502b4)  
Etherscan [__DYNAMIKS__](https://etherscan.io/token/0x066a54ae6920cbf525de48b1292a9afb7c21f767)



## END — CALCULATIKS-LIGHT
