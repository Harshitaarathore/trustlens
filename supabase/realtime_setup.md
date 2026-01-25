# How We Enabled Real-Time in Supabase

1. Database → Publications
2. Opened supabase_realtime publication
3. Added table: community_profiles
4. Saved → now INSERT/UPDATE events trigger live subscriptions in frontend

Used for: live spam_report_count updates → instant tier recalculation in UI
