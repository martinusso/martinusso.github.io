---
title: "Runbook"
summary: "Template for operational runbooks covering symptoms, diagnosis, mitigation, resolution, and escalation procedures."
draft: false
---

# Runbook - <System / Service Name>

Owner: <Team or primary owner>  
Last updated: YYYY-MM-DD  
Severity scope: SEV-1 | SEV-2 | SEV-3 (if applicable)

## Overview

Briefly describe what this runbook covers and when it should be used.

Example:  
Procedure to restart the authentication service in case of partial or total unavailability.

## Symptoms

How to recognize that the issue is occurring.

- User-facing errors (HTTP status codes, UI behavior, reports from support)
- Alerts triggered (alert name, threshold)
- Observable system behavior

Example:

- Users receive HTTP 500 errors during login attempts.
- Alert `auth-service-error-rate` is firing.

## Quick checks (Initial diagnosis)

Fast steps to confirm the problem and assess impact.

- Check logs: `<log location or command>`
- Verify service status:  
  `systemctl status <service>`
- Review metrics and dashboards: `<dashboard link>`
- Confirm scope (single instance, region, or global)

> Goal: confirm **what is broken** and **how bad it is** in under a few minutes.

## Immediate actions (Mitigation)

_Optional - use when the goal is to reduce impact while root cause is investigated._

- Restart service or pod
- Scale replicas up/down
- Disable a feature flag
- Fail over to a secondary component

Example:

- Restart the authentication service.
- Temporarily disable rate limiting via feature flag `auth_rate_limit`.

⚠️ Note any side effects or risks of these actions.

## Resolution

Steps to fix the root cause once identified.

- Apply configuration change or patch
- Clear cache or reset state
- Run corrective script or migration
- Roll back a recent deployment

Example:

- Apply patch `v1.2.3`.
- Clear Redis cache related to session tokens.
- Redeploy service with updated configuration.

## Validation

How to confirm the issue is fully resolved.

- Which metrics should return to normal
- Which logs should stop appearing
- Manual or automated checks to perform

Example:

- Error rate below threshold for 10 minutes.
- Successful login attempts confirmed via logs.

## Escalation

Who to contact if the issue cannot be resolved using this runbook.

- Primary engineer: `<name + contact>`
- Team or on-call group: `<Slack channel / PagerDuty>`
- External provider or vendor: `<contact / URL>`

Include **when** to escalate (e.g., after X minutes or if SEV-1).

## Post-incident follow-up

Checklist to complete after recovery.

- Create or update postmortem
- Document changes or fixes applied
- Review and improve monitoring and alerts
- Identify preventive actions

## Related resources

(Optional)

- Architecture diagram
- Related runbooks
- Dashboards
- Past incidents or postmortems
