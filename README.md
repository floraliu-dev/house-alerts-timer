# house-alerts-timer

A clock, nothing else. It runs on a schedule and calls `workflow_dispatch` on
the private [`house-alerts`](https://github.com/floraliu-dev/house-alerts)
crawler.

It exists because `house-alerts` is private and its own `schedule:` trigger has
never fired, while scheduled workflows on this account's public repos do run.
Rather than keep guessing at why, the scheduling moved to a repo where it works.

No listing data, no crawler code and no Slack webhook live here. The only secret
is `HOUSE_ALERTS_TOKEN`, a fine-grained token scoped to `house-alerts` alone
with `actions: write` and nothing else, so the worst it can do is start that one
workflow.
