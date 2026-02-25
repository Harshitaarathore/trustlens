# TrustLens – Community Credibility Layer

AI + Web3-powered platform to verify Telegram, Discord, WhatsApp & Instagram communities for scams and bot manipulation.  
Built by Team Nexus for #LNMHacks 2026.

---

## 🚀 Overview

TrustLens analyzes online communities and assigns a transparent **trust score (0–100)** using AI.  
Each analysis is backed by blockchain immutability to ensure tamper-proof credibility tracking.

Users can paste a community URL → AI evaluates risk signals → TrustLens generates a trust score and spam tier warning.

---

## 🔎 How It Works

1. User submits a community URL.
2. AI analyzes message patterns, bot ratio, and scam indicators.
3. System calculates:
   - Trust Score (0–100)
   - Spam Tier classification
4. Data stored in Supabase.
5. Immutable proof recorded on Monad blockchain.
6. Reporters earn $TLENS tokens.

### Spam Tier Classification
- **Low Risk:** < 20 reports (mild caution)
- **Medium Risk:** 20–50 reports (clear alert)
- **High Risk:** > 50 reports (red flag)

---

## 🛠 Tech Stack

**Frontend**
- React + Vite
- Tailwind CSS

**Backend**
- Supabase (Database, Auth, Real-time, Storage)

**AI**
- OpenAI API

**Blockchain**
- Monad Testnet (immutability + NFT badges)

**Token**
- $TLENS on Solana

**Wallet Integration**
- MetaMask (Monad)
- Phantom (Solana)

---

## 🗄 Backend Architecture (Supabase)

### Database Table: `community_profiles`

| Column                | Type        | Purpose |
|-----------------------|------------|----------|
| id                    | uuid        | Primary key |
| community_url         | text        | Unique group URL |
| trust_score           | integer     | AI-generated score (0–100) |
| analysis_json         | jsonb       | Full AI output |
| spam_report_count     | integer     | Total spam flags |
| spam_tier             | text        | low / medium / high |
| blockchain_tx_hash    | text        | Monad transaction hash |
| verified_admin_wallet | text        | Verified admin wallet |
| created_at            | timestamptz | Auto timestamp |

### Features Used
- Real-time subscriptions
- Email authentication
- Public storage bucket for screenshots
- Postgres-based structured queries

---

## 🔒 Why Blockchain?

- Ensures analysis history cannot be altered
- Creates transparency in community credibility
- Enables token-based governance via $TLENS

--

🗺 Roadmap

- Deploy frontend to Vercel
- Move to Monad mainnet
- Add $TLENS staking
- Multi-language AI support
- Advanced bot-detection heuristics

👥 Team Nexus

This project was collaboratively developed for LNMHacks 2026.
Contributors :
- Nishika Jain ( @nishikaJain )
- Harshita Rathore (@Harshitaarathore)
- Komal Gaur (@komalgaur24)
