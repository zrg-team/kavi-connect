# kavi-connect

The phone-facing **connections page** for [Kavi](https://github.com/zrg-team/rokid-personal-assistant),
an AIUI agent for Rokid Glasses.

A single static page (`index.html`), served on GitHub Pages. Opened from a link the
glasses show, it lists the services Kavi can connect (Google Calendar, Gmail,
Slack, …) and authorizes each through Composio. All logic lives in the agent's
Supabase Edge Function; this page only renders what the function returns.

It is public and static on purpose — the Supabase functions domain refuses to
render HTML, so the list page lives here instead. It holds no secrets: only the
Supabase project URL and publishable key, both meant to ship to browsers (row-level
security is on with no policies, so the key can read and write nothing directly).

See `docs/16-connections-hub-plan.md` in the main repo for the design.
