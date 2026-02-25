# TrustLens – Community Credibility Layer
AI + Web3 app to verify Telegram, Discord, WhatsApp & Instagram groups for scams  
Built by Team Nexus for #LNMHacks 2026

## What TrustLens Does
Paste a group URL → AI analyzes messages for bots/scams → gives trust score (0–100) + spam tier warning:  
- <20 reports: Low risk (mild caution)  
- 20–50 reports: Medium risk (clear alert)  
- >50 reports: High spam risk (red flag)  

Data stored in Supabase + immutable history on Monad blockchain.  
$TLENS token rewards reporters + enables governance.

## Tech Stack
- Frontend: React/Vite + Tailwind (generated via NoahAI)
- Backend: Supabase (database, real-time, auth, storage)
- AI: OpenAI API
- Blockchain: Monad testnet (immutability + NFT badges)
- Token: $TLENS on Solana via CyreneAI
- Wallets: MetaMask (Monad) + Phantom (Solana)

## Supabase Backend – What We Did (Detailed)
We used Supabase as our fast, free backend-as-a-service.

### 1. Project Creation
- Created project: `trustlens-global`
- Region: Asia (low latency for India)

### 2. Database Table: community_profiles
Created in Table Editor with these columns:

| Column                  | Type          | Description / Purpose                              | Default     |
|-------------------------|---------------|-----------------------------------------------------|-------------|
| id                      | uuid          | Auto-generated primary key                          | auto        |
| community_url           | text          | Unique URL of the group (e.g. t.me/group)           | —           |
| trust_score             | integer       | AI-generated score 0–100                            | —           |
| analysis_json           | jsonb         | Full AI output (flags, bot_ratio, etc.)             | —           |
| spam_report_count       | integer       | Cumulative spam flags (user + AI)                   | 0           |
| spam_tier               | text          | Calculated: 'low' (<20), 'medium' (20–50), 'high' (>50) | —       |
| blockchain_tx_hash      | text          | Monad tx hash for immutability                      | —           |
| verified_admin_wallet   | text          | Wallet address of verified admin                    | —           |
| created_at              | timestamptz   | Auto timestamp                                      | now()       |

### 3. Real-Time Enabled
- Went to Database → Publications
- Added `community_profiles` to `supabase_realtime` publication
- Result: New reports or count updates appear live in dashboard without refresh

### 4. Authentication
- Enabled Email provider (low password requirements for hack speed)
- Checked Web3 Wallet beta (if available) for MetaMask/Phantom sign-in

### 5. Storage
- Created public bucket: `community_screenshots`
- Used for uploading proof images (URLs saved in analysis_json)

### 6. Connection to Frontend
- Used `@supabase/supabase-js` client
- Initialized with project URL + anon key (pasted into NoahAI prompt)
- Operations: insert/update spam counts, subscribe to changes for real-time UI

### Why Supabase?
- Free tier perfect for hackathon (500MB storage, unlimited auth)
- Real-time built-in (no extra sockets/server)
- Postgres = fast structured queries for spam counts/tiers
- Easy auth & storage — no custom backend needed

## Next Steps (Post-Hackathon Ideas)
- Deploy frontend to Vercel
- Move to Monad mainnet
- Add $TLENS staking for extra earnings
- Improve AI with more languages

Team Nexus  
@nishikaJain , @komalgaur24 and @Harshitaarathore
#LNMHacks #Web3 #AI #Supabase #Hackathon
