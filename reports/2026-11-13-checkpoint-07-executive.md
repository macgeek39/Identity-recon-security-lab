# CISO Executive Update — Checkpoint 7: Identity Governance

**Project:** Identity Recon — Identity Security Monitoring & Defense Lab  
**Prepared by:** Taiwei Ko  
**Report date:** November 13, 2026  
**Environment:** Isolated Microsoft Entra ID Governance learning tenant  
**Overall status:** **Implemented with exceptions; end-to-end governance validation incomplete**  
**Assurance basis:** Six screenshot artifacts; no independent access to tenant or audit records

## Executive summary

An authorized IAM governance lab implemented employee lifecycle automation, a job-related access package, and an access review using Microsoft Entra ID Governance. The exercise demonstrated why governance controls must be evaluated on **task outcomes and verified access changes**, not only on whether a configuration exists.

One onboarding execution encountered a **failed welcome-email task due to a missing/invalid manager attribute**, while the subsequent group task was **cancelled**. An offboarding workflow displayed three completed tasks but its overall execution status remained **In progress** in the captured view. An IT support access package had a configured resource and policy but **no assignments**, and the privileged-group access review was **Not started**.

## Business risk and control posture

| Control objective | Observed result | Leadership implication |
|---|---|---|
| New-hire onboarding | Partial execution, failed email and cancelled group task | Employee may not receive expected communications or role access; incomplete records require remediation |
| Timely offboarding | Account-disable task completed; group/Teams tasks completed with no memberships to remove; run still in progress | A successful task list is not yet proof of full deprovisioning, session invalidation, or final workflow completion |
| Access package governance | Policy/resource configured; zero assignments | Design exists; effectiveness of approval and provisioning untested |
| Privileged-access review | One-time review created; one user not reviewed; status Not started | No recertification decision or removal has yet been demonstrated |
| Mover governance | Configuration reported without screenshot | Least-privilege changes on a role move remain unverified |

## Key risks and remediation priorities

**Priority 1 — Onboarding resilience:** Repair the manager-dependent welcome-email configuration and investigate why group assignment was cancelled. Repeat a full joiner test and verify expected access was actually delivered.

**Priority 2 — Leaver assurance:** Confirm the workflow reaches a terminal state. Retest with a synthetic account that has a known harmless group membership, and validate its removal. Review residual sessions, application permissions and privileged identities separately where applicable.

**Priority 3 — Access certification:** Activate and complete the privileged-group review. Confirm that reviewer decisions are actually reflected in the user's retained or removed access.

**Priority 4 — Access request outcomes:** Test a complete package request and approval, verify resource assignment and time-bound removal if configured. Document the mover access-change case separately.

## Decision and next milestone

**Decision requested:** None for an educational lab. If these were production observations, the IAM owner should assign corrective actions and retest before accepting the governance controls as effective.

**Success criteria:** No failed/cancelled tasks in the expected joiner test; verified offboarding and entitlement removal; tested package request/approval; completed access review with evidence of application; and mover access transitions validated.

**Limitations:** Evidence is drawn from screenshots dated November 13, 2026. This is not a production environment or independent audit. No actual production access, enterprise-wide policy coverage, or closed-loop remediation is claimed.

**Technical reference:** [Checkpoint 7 Technical Implementation & Findings Report](2026-11-13-checkpoint-07-technical.md).
