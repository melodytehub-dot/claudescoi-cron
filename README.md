# claudescoi-cron

A tiny GitHub Actions scheduled pinger for https://claudescoi.vercel.app.

Every 5 minutes it calls:

```
GET https://claudescoi.vercel.app/api/cron/scan
Authorization: Bearer <CRON_SECRET>
```

The secret lives in this repository's **Actions secrets**; nothing sensitive is
stored in the workflow or the code. The repository is public only so scheduled
Actions minutes are free.

If GitHub disables the schedule after a long period of repository inactivity,
open **Actions â†’ claudescoi scan â†’ Enable workflow**.

Schedules are registered by the GitHub scheduler on push; this line just re-registers them.

