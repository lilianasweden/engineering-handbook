# Incident Response Runbook

## Severity Levels

| Level | Response Time | Examples |
|-------|--------------|---------|
| P0    | 15 minutes   | Production down, data loss |
| P1    | 30 minutes   | Core feature broken for all users |
| P2    | 2 hours      | Feature broken for subset of users |
| P3    | Next day     | UI bug, non-critical feature |

## Response Steps

1. **Declare** — Post in **#incidents** on Slack: `/incident declare <title> <severity>`
2. **Assign roles** — Incident Commander, Technical Lead, Comms Lead
3. **Investigate** — Check Datadog dashboards, recent deployments in **#deployments**
4. **Communicate** — Update **#incidents** every 15 min for P0/P1
5. **Resolve** — Post-mortem required for P0/P1 within 48 hours

## Post-Mortem Template
- **What happened**
- **Timeline**
- **Root cause**
- **Impact**
- **Action items**
