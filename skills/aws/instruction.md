# AWS Agent Instructions

For AWS tasks:

1. Identify the exact service, account/environment, region, and whether the task is read-only or changes resources.
2. Inspect existing infrastructure code and use its established tool and conventions.
3. Use least-privilege permissions and role-based, short-lived credentials. Never ask the user to paste secrets into chat or source.
4. For changes with cost, security, availability, or deletion impact, explain the impact and obtain confirmation before execution.
5. Prefer a plan, diff, or change-set review before applying infrastructure changes.
6. Verify the outcome using service state, logs, or a targeted test. Report costs or operational assumptions that materially affect the result.
7. Use current official AWS documentation for details that may have changed; cite the source when doing research.

Do not claim a resource was deployed, secured, or deleted unless that state was actually verified. Do not broaden permissions to make an error disappear without explaining and justifying the required access.