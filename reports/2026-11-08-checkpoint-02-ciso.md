# Executive Security Update — Identity Recon Monitoring Foundation

**Project:** Identity Recon — Identity Security Monitoring & Defense Lab (Cybernoia IAM Path)  
**Milestone:** Checkpoint 2 — Range Setup  
**Prepared by:** Taiwei Ko  
**Report date:** November 8, 2026  
**Environment:** Isolated training/lab tenant (not production)  
**Delivery status:** Lab foundation deployed; sign-in and audit ingestion validated on November 8, 2026. Detection rules not yet tested.

## Executive summary

Established the foundation for identity security monitoring in an isolated Microsoft Entra ID lab. The environment uses **Azure Log Analytics** as a centralized destination for identity telemetry and **Microsoft Sentinel** for security analysis and investigation. KQL screenshots from November 8, 2026 show **122 sign-in events** and **29 directory audit events** within a 24-hour query window, confirming both log types are available in the selected workspace.

This milestone prepares the range for future identity threat simulations and defensive investigations. **It does not, by itself, establish that every event is collected, every attack is detected, or any production environment is protected.**

## Business and security value

- **Visibility:** Centralized access to identity activity can support investigation of sign-ins and directory changes.
- **Incident readiness:** Establishes a telemetry foundation for future detections, investigations, and response exercises.
- **Auditability:** Creates a starting point for demonstrating how identity events can be collected and reviewed.
- **Engineering foundation:** Supports the next exercises involving identity abuse, governance, and Zero Trust controls.

## Implemented scope

| Component | Purpose | Status |
|---|---|---|
| Microsoft Entra ID lab | Identity provider and controlled test environment | Configuration screenshot attached |
| Azure Log Analytics workspace | Centralized identity log collection and query platform | Screenshot attached |
| Microsoft Sentinel | Security monitoring and investigation layer | Screenshot attached |
| Entra diagnostic routing | Sends selected identity event categories to the workspace | Configuration screenshot attached |
| Sign-in and audit ingestion | Shows records arriving and queryable | **Validated:** 122 sign-in and 29 audit events over 24 hours |

## Risks and limitations

1. **Full coverage remains unverified.** The two queryable log types do not prove continuous ingestion, complete event coverage, or sufficient retention.
2. **Detection content must be tested.** Sentinel onboarding alone does not demonstrate that a specific identity attack will generate an alert.
3. **Usage and cost require oversight.** Workspace ingestion, retention, and Sentinel usage can generate Azure charges. Two similarly named workspaces appear in evidence, and budget controls have not been documented.
4. **Scope is lab-only.** Findings are training outcomes, not an assessment of an enterprise production tenant.

## Next actions and acceptance criteria

- Preserve the [seven Checkpoint 2 screenshots](../evidence/checkpoint-02/) documented in the [technical report](2026-11-08-checkpoint-02-technical.md).
- Repeat log-ingestion verification after configuration changes and record dated results.
- Record which diagnostic categories are enabled and identify any telemetry gaps.
- Confirm subscription cost controls and retention settings appropriate to the lab.
- Use the validated logging pipeline as the basis for later controlled detection and incident-response exercises.

**Management decision requested:** None at this stage. Continue with the next lab milestone after the telemetry pipeline is verified and documented.
