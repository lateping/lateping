<p align="center">
  <img src="logo.svg" alt="Lateping" width="80" height="72">
  <br><br>
  <strong>Lateping</strong>
  <br>
  Know when a scheduled job doesn't run. Cron, GitHub Actions, Workers, Kubernetes, backups: one line to monitor, an alert when it's late.
  <br><br>
  <a href="https://app.lateping.com/signup"><img src="https://img.shields.io/badge/Start%20free-0d7a5f?logoColor=white" alt="Start free"></a>
  <a href="https://lateping.com/guides"><img src="https://img.shields.io/badge/Guides-lateping.com-0b0b0b" alt="Guides"></a>
  <a href="https://github.com/marketplace/actions/lateping-ping"><img src="https://img.shields.io/badge/GitHub%20Action-lateping%2Fping-181717?logo=github&logoColor=white" alt="GitHub Action"></a>
  <br>
  <img src="https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white" alt="TypeScript">
  <img src="https://img.shields.io/badge/Cloudflare%20Workers-F38020?logo=cloudflareworkers&logoColor=white" alt="Cloudflare Workers">
  <img src="https://img.shields.io/badge/Cloudflare%20D1-F38020?logo=cloudflare&logoColor=white" alt="Cloudflare D1">
  <img src="https://img.shields.io/badge/React-20232A?logo=react&logoColor=61DAFB" alt="React">
  <img src="https://img.shields.io/badge/Hono-E36002?logo=hono&logoColor=white" alt="Hono">
</p>

---

## About

The scheduled jobs that hurt most are the ones that fail by not running. A crontab line lost in a server rebuild. A GitHub Actions schedule switched off after 60 days without commits. A backup script that hangs forever, or a Worker cron trigger that disappeared in a deploy. Nothing errors when a job doesn't run, so nothing tells you.

Lateping flips it around. Your job calls a URL when it finishes. If the call doesn't arrive by the deadline (a period or a cron expression in your timezone, plus a grace period), you get an alert. Silence is the alarm, so it catches every way a job can fail to run, including the ones you didn't think of.

```bash
# crontab: back up at 02:17, then tell Lateping it worked
17 2 * * * /usr/local/bin/backup.sh && curl -fsS -m 10 --retry 5 -o /dev/null https://lateping.com/p/<check-id>
```

Free for 10 checks with email alerts. No card, no password.

[lateping.com](https://lateping.com) · [Create an account](https://app.lateping.com/signup) · [Guides](https://lateping.com/guides) · [Pricing](https://lateping.com/pricing)

## Features

| Feature | What it does |
| --- | --- |
| Heartbeat checks | A period ("every hour") or a cron expression with a timezone, and a grace period. Preview the next runs before you save. |
| Start, success and fail pings | `/start` times each run; `/fail` alerts at once instead of waiting for the deadline. Or send the exit code (`/p/<check-id>/$?`): 0 is a success, anything else alerts and shows the code. |
| Alerts where you work | Email on every plan; Slack, Discord and signed webhooks on Pro. Turn any destination on or off per check, and make the account email a backup so nobody gets every alert twice. |
| Our downtime is never your alert | If Lateping itself goes down, every deadline that fell inside the gap moves back by the gap. If a large share of checks go late at once, alerts are held, because a mass event is more likely our problem than yours. |
| Run analytics | How long each run takes, how early or late pings arrive, charts and CSV export (Pro). |
| Status badges | A README badge that shows a check is up, late or failing, without revealing its ping URL. |
| GitHub Action | [`lateping/ping@v1`](https://github.com/lateping/ping): one step reports start, success or failure for a workflow. |
| API | Manage checks and destinations from scripts with an API key (Pro). |
| Sign-in | Emailed link, passkeys, or Google and GitHub, with optional two-factor. No passwords. |
| Private by default | We don't store IP addresses, only a country code per ping. No tracking cookies. |
| Guides that work | Copy-paste setup for GitHub Actions, Cloudflare Workers, crontab, Vercel Cron, pg_cron, Kubernetes CronJobs, systemd timers, Laravel and backup jobs. Every snippet is tested in CI. |

| Plan | Price | Checks | Alerts | History |
| --- | --- | --- | --- | --- |
| Free | $0 | 10 | Email | 7 days |
| Pro | US$12/month or $120/year | 50 | Email, Slack, Discord, webhooks | 1 year |
| Team | US$39/month or $390/year | 300 | As Pro, plus priority support | 1 year |
| Founding | US$90/year, first 50 buyers | 50 | As Pro, price locked while subscribed | 1 year |

See the [pricing page](https://lateping.com/pricing) for the details.

## Getting started

1. [Create an account](https://app.lateping.com/signup). It takes an email address, or one click with Google or GitHub.
2. Create a check with your job's schedule and timezone. Give it a grace period a little longer than the job normally takes.
3. Add the ping to the end of the job, after the work, so it only runs when the work succeeded. The check's Setup tab has the line for your platform, with your URL filled in.

That's it. If the ping is late, you hear about it. When it comes back, you get a recovery.

Full walkthroughs: [lateping.com/guides](https://lateping.com/guides).

## Support

| For | Go to |
| --- | --- |
| Questions and setup help | [support@lateping.com](mailto:support@lateping.com). We reply within 12 hours. |
| Bug reports and feature requests | [Open an issue](https://github.com/lateping/lateping/issues/new/choose) |
| Security vulnerabilities | [SECURITY.md](SECURITY.md). Do not open a public issue. |
| Billing, account and privacy requests | [support@lateping.com](mailto:support@lateping.com) |

## About this repository

This is the public repository for Lateping. It holds the issue tracker, the security policy, and this README. The service's source code is proprietary and is not published here. The [GitHub Action](https://github.com/lateping/ping) is open source under MIT.

## License

Proprietary. Copyright (c) 2026 JTF Labs Pty Ltd. All rights reserved. See [LICENSE](LICENSE).
