# SipHeron VDR

> Anchor any document's fingerprint permanently to the Solana blockchain.
> Tamper-proof. Publicly verifiable. Forever.

The document never leaves your device. Only its mathematical fingerprint touches the chain.
The proof lives on Solana's public ledger — verifiable by anyone, forever, even if SipHeron ceases to exist.

---

## What Problem We Solve

Digital documents can be silently altered with no way to prove it happened.
Contracts get disputed. Records get questioned. Audit trails get challenged in court.
Healthcare records get falsified. Credentials get forged. Clinical trial data gets manipulated.

**SipHeron makes document tampering mathematically detectable. Instantly. Forever.**

---

## How It Works

```
Document → SHA-256 Hash → Solana Blockchain → Public Verification URL
```

**Step 1 — Fingerprint**
SHA-256 hashes your document into a unique 64-character string.
Change one byte anywhere in the document and the fingerprint changes completely.
The document never leaves your device.

**Step 2 — Anchor**
The fingerprint is written permanently to the Solana blockchain.
Sub-second confirmation. $0.001 per anchor. Immutable forever.

**Step 3 — Verify**
Anyone can verify authenticity by hashing their copy and comparing it
against the on-chain record. No account required. No trust required. Pure mathematics.

---

## Get Started in 60 Seconds

```bash
# Install the CLI
npm install -g sipheron-vdr

# Authenticate
sipheron login

# Anchor your first document
sipheron anchor ./contract.pdf

# Verify authenticity
sipheron verify ./contract.pdf
```

---

## Repositories

| Repository | Description | License | Status |
|------------|-------------|---------|--------|
| [vdr-core](https://github.com/SipHeron-VDR/vdr-core) | Core verification library — SHA-256 hashing, Solana anchoring, public verification | Apache 2.0 | Public |
| [vdr-cli](https://github.com/SipHeron-VDR/vdr-cli) | Command line tool — anchor and verify from your terminal | MIT | Public |
| [vdr-js](https://github.com/SipHeron-VDR/vdr-js) | JavaScript and TypeScript SDK | Apache 2.0 | Public |
| [vdr-python](https://github.com/SipHeron-VDR/vdr-python) | Python SDK | Apache 2.0 | Public |
| [vdr-protocol](https://github.com/SipHeron-VDR/vdr-protocol) | Open verification protocol specification | CC BY 4.0 | Public |
| [vdr-docs](https://github.com/SipHeron-VDR/vdr-docs) | Complete public documentation | CC BY 4.0 | Public |
| [vdr-examples](https://github.com/SipHeron-VDR/vdr-examples) | Integration examples for popular platforms | MIT | Public |
| [vdr-embed](https://github.com/SipHeron-VDR/vdr-embed) | Embeddable verification widget for websites | Apache 2.0 | Public |

---

## Built For

```
Legal & Contracts        →  Prove contracts were not altered after signing
Healthcare Records       →  Tamper-proof patient records and clinical trial data
Finance & Audit          →  Immutable audit trails for SOX, GDPR compliance
Education & Credentials  →  Verifiable diplomas and professional certifications
Government Documents     →  Unforgeable permits, filings, and public records
Software & IP            →  Prove codebase state at any point in time
```

---

## Why Solana

| Property | Why It Matters for Document Verification |
|----------|------------------------------------------|
| Sub-second finality | Verification certificates generated in real time during document signing |
| $0.001 per transaction | Enterprise-scale anchoring is economically viable at any volume |
| Public distributed ledger | Proofs verifiable by anyone without trusting SipHeron |
| Immutable history | No single party can alter or delete a recorded proof |
| 99.98% uptime | Production-grade reliability for enterprise workflows |

---

## Independent Verification

You do not need SipHeron to verify a proof. Ever.

```bash
# Step 1 — Compute the hash of your document yourself
# macOS / Linux
shasum -a 256 your-document.pdf

# Windows PowerShell
Get-FileHash your-document.pdf -Algorithm SHA256

# Step 2 — Look up the transaction on any Solana block explorer
# Visit: https://solscan.io/tx/{transactionSignature}
# Read the memo field
# Compare the hash in the memo to your computed hash

# If they match  →  document is authentic
# If they differ →  document has been modified
```

SipHeron could cease to exist tomorrow.
Every proof ever created would still be verifiable forever.
That is the design. That is the point.

---

## Open Protocol

The complete specification of how SipHeron's anchoring and verification
protocol works is publicly documented in
[vdr-protocol](https://github.com/SipHeron-VDR/vdr-protocol).

It is written so that any developer can implement it independently,
verify proofs without SipHeron's involvement, and build compatible tooling.

We open sourced the protocol because trust requires transparency.
A black box is not trustworthy infrastructure. An open specification is.

---

## Pricing

| Plan | Anchors | Users | Price |
|------|---------|-------|-------|
| Free | 100/month | 1 | $0 forever |
| Business | 10,000/month | 10 | $99/month |
| Enterprise | Unlimited | Unlimited | Custom |

[Get your free API key →](https://app.sipheron.com)
No credit card. No commitment. 100 free anchors every month.

---

## Status

| Component | Status |
|-----------|--------|
| Solana Devnet | 🟢 Live |
| REST API | 🟢 Operational |
| Webhooks | 🟢 Operational |
| Dashboard | 🟢 Operational |
| CLI | 🟢 Operational |
| Mainnet | 🔵 Coming Soon |

[app.sipheron.com](https://app.sipheron.com)

---

## Links

- 🌐 Website: [app.sipheron.com](https://app.sipheron.com)
- 📖 Documentation: [app.sipheron.com/docs](https://app.sipheron.com/docs)
- 🛝 Playground: [app.sipheron.com](https://app.sipheron.com/playground)
- 🐦 X: [@SipHeronVDR](https://x.com/SipHeronVDR)
- 💬 Discord: [discord.gg/sipheron](https://discord.gg/sipheron)
- 📧 Contact: [hello@sipheron.com](mailto:hello@sipheron.com)

---

## For Developers

```typescript
import { SipHeronClient } from 'sipheron-js';

const client = new SipHeronClient({
  apiKey: process.env.SIPHERON_API_KEY,
  network: 'devnet'
});

// Anchor a document
const anchor = await client.anchors.create({
  file: fileBuffer,
  name: 'Service Agreement — Acme Corp',
  metadata: { type: 'contract' }
});

console.log(anchor.verificationUrl);
// https://verify.sipheron.com/a3f4b2c1...

// Verify a document
const result = await client.verify.check({ file: fileBuffer });
console.log(result.authentic); // true
```

---

## For Legal and Compliance Teams

No blockchain expertise required.
No cryptocurrency required.
No technical knowledge required.

**Three things you get:**

1. **Proof of existence** — mathematically prove a document existed at a specific date and time
2. **Proof of integrity** — mathematically prove a document has not been altered since anchoring
3. **Public verifiability** — anyone can verify your document's authenticity with a link, forever

**One thing you keep:**

Your document never leaves your device. SipHeron never sees it.

[Book a 15-minute demo →](https://cal.sipheron.com/demo)

---

## Current Stage

SipHeron is live on **Solana Devnet** with the complete feature set.
Mainnet launch is in progress.

We are actively onboarding design partners in the legal and compliance verticals.
If you work in legal, healthcare, finance, or government and want to be
among the first organizations to anchor documents on mainnet —

[**Apply to be a design partner →**](https://sipheron.com/design-partners)

---

*Built on Solana · Open Protocol · Apache 2.0 Core*
