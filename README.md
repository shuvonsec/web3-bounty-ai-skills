# web3-skills-brain

> **18 Claude Code skill files for smart contract security — distilled from 2,749 Immunefi reports, 681 DeFiHack reproductions, and real hunt experience.**

[![Skills](https://img.shields.io/badge/skills-18-blue)](./skills/) [![Immunefi Reports](https://img.shields.io/badge/immunefi%20reports%20analyzed-2%2C749-orange)](./skills/00-start-here.md) [![License](https://img.shields.io/badge/license-MIT-green)](./LICENSE)

---

## What Is This?

Most smart contract hunters work the same way: 10 browser tabs, grep commands pasted from memory, Foundry templates rewritten from scratch each hunt, reports drafted from a blank page.

This repo is a **knowledge brain** you load into Claude Code. It turns months of learning into a skills pack that's immediately available in any hunt conversation.

```
You → "load my web3 brain" → Claude reads the chain → you start hunting
```

Built from:
- **2,749 Immunefi vulnerability reports** (406 Critical, 616 High)
- **$100M+ in paid bounties** analyzed for patterns
- **681 DeFiHackLabs** reproduced exploits
- **166 Nethermind** professional audit reports
- Trail of Bits, ConsenSys, SlowMist, Cyfrin methodology
- Live hunt experience (real targets, real findings)

---

## The Skill Chain

Read in order. Each file ends with `→ NEXT`.

| # | File | What's Inside |
|---|------|---------------|
| 00 | `00-start-here.md` | Master index, how to navigate |
| 01 | `01-foundation.md` | Hunter mindset, 10-point target scorecard, recon setup |
| 02 | `02-bug-classes.md` | All 10 bug classes with patterns + real paid examples |
| 03 | `03-grep-arsenal.md` | Master grep patterns for every bug class |
| 04 | `04-poc-and-foundry.md` | Foundry PoC writing, 18 exploit templates, cheatcodes |
| 05 | `05-triage-report-examples.md` | 7-Question validation gate, 20 real paid reports |
| 06 | `06-methodology-research.md` | ToB, SlowMist, ConsenSys, Immunefi, Cyfrin, Nethermind |
| 07 | `07-case-study-role-misconfiguration.md` | Case study: role misconfiguration bug class (real hunt) |
| 08 | `08-ai-tools.md` | Shannon, LuaN1ao, SmartGuard, CAI Framework |
| 09 | `09-case-study-hardened-l2-bridge.md` | Defense study: what unhuntable looks like (25 vectors tested) |
| 10 | `36-solidity-audit-mcp.md` | MCP: Slither + Aderyn + SWC inside Claude Code |

**After file 05 you can hunt independently. Files 06–10 are advanced tools.**

---

## Quick Stats

| Metric | Number |
|--------|--------|
| Immunefi reports analyzed | 2,749 |
| Protocols covered | 51 |
| Critical reports | 406 |
| High reports | 616 |
| Total paid by Immunefi | $100M+ |
| Avg critical payout | $50K–$2M |
| Nethermind reports | 166 |
| DeFiHackLabs reproductions | 681 |

---

## Install in 60 Seconds

### Option A — Add to an existing project

```bash
# Clone into your project's Claude skills directory
git clone https://github.com/shuvonsec/web3-bounty-ai-skills.git .claude/skills/web3-brain

# Open Claude Code in your project
claude
```

Then in any conversation:
```
Read all files in .claude/skills/web3-brain/ starting with 00-start-here.md
```

### Option B — Standalone hunt workspace

```bash
# Clone and open directly
git clone https://github.com/shuvonsec/web3-bounty-ai-skills.git
cd web3-bounty-ai-skills
claude
```

Then tell Claude:
```
You are my web3 security assistant. Read 00-start-here.md then follow the chain.
When ready, I'll give you a target.
```

### Option C — Load specific skills only

```bash
# If you only need bug patterns + PoC templates:
claude
> Read 02-bug-classes.md and 04-poc-and-foundry.md
```

---

## The 10 Bug Classes

Everything in this repo maps back to one of these:

```
01  Accounting Desync       ← Most common Critical (37% of payouts)
02  Access Control          ← Most common High
03  Incomplete Path         ← Missing modifier on sibling function
04  Off-by-One              ← Boundary operators, index errors
05  Oracle Price            ← TWAP manipulation, stale prices
06  ERC4626 Vaults          ← Share inflation, rounding attacks
07  Reentrancy              ← Cross-function, cross-contract, read-only
08  Flash Loan              ← Price manipulation, economic attacks
09  Signature Replay        ← Cross-chain, missing nonce/chainId
10  Proxy/Upgrade           ← Uninitialized impl, storage collisions
```

**The one rule that explains 19% of all Criticals:**

> "Read ALL sibling functions. If `vote()` has a modifier, check `poke()`, `reset()`, `harvest()`. The missing modifier on the sibling IS the bug."

---

## What You Get

### 1. Target Scoring (before you waste time)
A 10-point scorecard that tells you HUNT vs SKIP in 5 minutes:
- TVL, payout, codebase size, audit quality, competition level
- Score ≥ 6 → hunt. Score < 6 → move on.

### 2. Bug Class Patterns (while you read code)
For each of the 10 classes:
- What it looks like in Solidity
- Grep patterns to find it instantly
- Real paid example from Immunefi
- Validation checklist

### 3. Foundry PoC Templates (when you find something)
18 ready-to-run exploit templates:
- Role misconfiguration, accounting desync, flash loan, reentrancy
- Just fill in the target address and run `forge test`

### 4. Report Format (when you submit)
- 7-Question Gate: is this actually submittable?
- Immunefi/Bugcrowd report template
- 20 real paid reports as examples

### 5. AI Integration (to move faster)
- Shannon (AI pentester) integration
- SmartGuard agent workflow
- CAI Framework for automated analysis
- Solidity MCP server: Slither + Aderyn in Claude Code

---

## Pair This With

- **[claude-bug-bounty](https://github.com/shuvonsec/claude-bug-bounty)** — Point at a target, get a full attack surface map + report. Uses these skills internally.
- **[public-skills-builder](https://github.com/shuvonsec/public-skills-builder)** — Feed 500 HackerOne/GitHub writeups, get skill files like these back out.

---

## The Workflow

```
1. New target appears
         ↓
2. Load this brain in Claude Code
         ↓
3. Run target scorecard (01-foundation.md)
         ↓
4. Claude reads contracts + runs grep patterns (02, 03)
         ↓
5. Candidate bugs surface
         ↓
6. Run 7-Question Gate (05-triage-report-examples.md)
         ↓
7. Build PoC from template (04-poc-and-foundry.md)
         ↓
8. Write report from format (05-triage-report-examples.md)
         ↓
9. Submit
```

---

## License

MIT. Use freely. Build on it.

---

*Built during live hunts. Every pattern in here has been tested against real deployed contracts.*

*If this helped you find a bug, star the repo.*
