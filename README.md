# Native scheduler diagnostic

Temporary public experiment created on 2026-10-09 to check whether native GitHub Actions schedule events are created for this account.

The workflow prints only the trigger, cron expression, run ID, commit SHA and UTC time. It does not check out code, use secrets, install dependencies, or contact production services. Its GITHUB_TOKEN has no granted permissions.

## Observation window

Expected UTC opportunities: October 9 at :17 and :47 from 08:00 to 23:59; October 10 at :17 and :47 from 00:00 to 08:59. Only opportunities after the workflow was committed count. GitHub can delay or drop scheduled runs.

Filter the Actions history by event `schedule`. A successful `push` or `workflow_dispatch` run verifies execution, but does not establish that scheduling works.

If native schedules run here while the production repository still has none, that narrows the issue to repository-specific behavior; it does not by itself prove visibility caused the difference. If neither runs, an account-level or platform scheduling problem remains possible.

Disable the workflow after reviewing the experiment. Cron expressions have no year field, so these dates would otherwise match again next October. No production repository visibility or settings were changed.
