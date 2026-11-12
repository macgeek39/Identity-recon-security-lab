# Executive Security Update — Checkpoint 6: Escalation & Persistence

**Project:** Identity Recon — Identity Security Monitoring & Defense Lab  
**Prepared by:** Taiwei Ko  
**Report date:** November 12, 2026  
**Environment:** Owned, synthetic Microsoft Entra ID training tenant — not production  
**Status:** Hands-on exercises completed as reported; no terminal or audit evidence included for independent validation  
**Audience:** CISO / Security Leadership

## Executive summary

A controlled identity-security lab explored how access obtained through an initially compromised support account could develop into **multiple privileged and persistent access paths** within Microsoft Entra ID. The reported sequence included reuse of an existing access token, application consent abuse, independent application authentication, a misconfigured privileged-group/PIM path, creation of an additional Global Administrator account, and changes to application ownership and privileged group membership.

**Core leadership finding:** A reset of the first compromised user account is **not a complete recovery strategy** when other accounts, application credentials, consent grants, ownership relationships, or privileged group memberships remain active.

## Business exposure illustrated

| Risk theme | Potential enterprise impact | Lab evidence status |
|---|---|---|
| Token reuse | Access to permitted APIs without another interactive sign-in | User-reported; token and logs not reviewed |
| Application consent and credentials | Unauthorized application access independent of a user's password | User-reported; effective permissions unknown |
| Privileged-group escalation | Widespread directory administration if effective Global Administrator rights are obtained | User-reported; role path not independently confirmed |
| Additional privileged account | Continued administrative access after initial account recovery | User-reported; separate admin login described |
| Shadow owners and group membership | Alternative routes to application control and privileged entitlements | User-reported; downstream privileges not established |

**Illustrative severity:** Potentially **critical** in a real enterprise **if** unapproved Global Administrator access and durable independent credentials were confirmed. This is a training scenario, not a scored production finding.

## What the assessment demonstrated

The exercise shows why modern IAM programs must govern **human and non-human identities together**. Controlling passwords and MFA is necessary but insufficient if a compromised identity can approve broad app access, influence privileged groups, or establish additional administrative identities.

The test environment's prior monitoring foundation offers a place to investigate such changes. However, **no Checkpoint 6-specific detections or alerts were verified**, and no conclusion is drawn that the activity was invisible to Microsoft Entra or Sentinel.

## Recommended security priorities

1. **Contain all access paths, not just the starting user.** Inventory newly created admins, high-privilege memberships, app owners, credentials, and consent grants during identity compromise response.
2. **Strengthen privileged access controls.** Govern role-assignable groups and PIM assignments, separate ownership from administration, and require time-bounded access/approval where appropriate.
3. **Govern enterprise applications and workload identities.** Restrict high-risk consent, review permissions and credentials, and monitor non-human sign-ins.
4. **Test monitoring and recovery.** Validate audit collection for role, group, app and credential changes, and demonstrate that containment actually removes access.
5. **Complete authorized lab cleanup.** Disable/review test backdoors, revoke excess permissions and sessions, remove unnecessary app credentials, and validate the final access state.

## Decisions, limitations, and next steps

**Decision required:** None for this owned training lab. A production response would require immediate incident ownership, containment approvals, impact assessment, and preservation of audit evidence.

**Limitations:** No raw output, screenshots, exact permissions, privileged assignment paths, or detection outcomes have been provided for independent validation. Device-code/token behavior is dependent on token type, lifetime, resource scope, and security policy. Application credentials are not guaranteed to survive app disablement, consent revocation, or other controls. **Federation trust abuse was not reported as performed.**

**Next action:** Reconcile and clean up all synthetic persistence artifacts, then document an access-recovery validation exercise. Continue with the remaining Identity Recon curriculum once the lab is in a known state.

**Technical companion:** [Checkpoint 6 — Technical Security Assessment](2026-11-12-checkpoint-06-technical.md).

---

*Educational report for a controlled Microsoft Entra ID lab; not evidence of a production breach or a real organization's security posture.*
