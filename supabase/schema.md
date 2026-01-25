# Supabase Schema – community_profiles Table

Created via Table Editor.

Columns:
- id: uuid (primary key, auto-generate)
- community_url: text (unique)
- trust_score: integer
- analysis_json: jsonb
- spam_report_count: integer (default 0)
- spam_tier: text (calculated in frontend or view)
- blockchain_tx_hash: text
- verified_admin_wallet: text
- created_at: timestamptz (default now())

Indexes:
- Unique index on community_url

Real-time: Enabled via supabase_realtime publication
