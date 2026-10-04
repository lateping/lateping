# Security Policy

Lateping runs as a hosted service, so the only version we support is the one
currently live at `lateping.com` and `app.lateping.com`.

## Reporting a vulnerability

Report it privately rather than opening a public issue. Either:

- Use the **Report a vulnerability** button on the
  [Security tab](https://github.com/lateping/lateping/security), or
- Email [support@lateping.com](mailto:support@lateping.com) with `SECURITY` in
  the subject.

Tell us what the problem is, which part it affects (the ping endpoint, the
panel, the API, alert delivery, sign-in, or the GitHub Action) and how to
reproduce it. A proof of concept helps. So does anything that lets us find it
in our logs: a check ID, your account email, a rough timestamp.

## What to expect

We'll acknowledge inside 3 business days and come back with an assessment within
a week. After that you'll get a timeline, though anything critical jumps the
queue. We'll tell you when the fix is live, and we're happy to credit you by
name if you want that.

## Scope

Covered: `lateping.com` (including the `/p/` ping endpoint), `app.lateping.com`
and its API, alert delivery (email, Slack, Discord, webhooks), sign-in
(emailed links, passkeys, Google and GitHub, two-factor), and the
[`lateping/ping`](https://github.com/lateping/ping) GitHub Action.

Not covered:

- Denial of service, volumetric or load testing
- Social engineering of our staff or our customers
- Pinging, guessing or enumerating check IDs that aren't yours
- Raw scanner output, missing hardening headers, and similar best-practice
  findings with nothing exploitable behind them

## Testing

Only test against accounts and checks you created. Don't read, change or keep
other customers' checks, alerts or personal data. If you stumble into any,
stop there and mention it in your report.

We don't run a paid bounty. We won't come after anyone who follows this policy
in good faith.
