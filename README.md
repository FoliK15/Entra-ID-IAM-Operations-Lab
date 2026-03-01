# Microsoft Entra ID IAM Operations Lab (Users • Groups • MFA • Guest Access • Audit Logs)

> **Portfolio Project | Identity & Access Management (IAM) | Microsoft Entra ID (Azure AD)**  
> Built a repeatable IAM operations workflow in Microsoft Entra ID and validated every administrative action using Audit Logs.

---

## 🎯 Objective
Demonstrate core IAM operational skills in Microsoft Entra ID by performing user lifecycle tasks, access/group management, role assignment for controlled testing, guest collaboration onboarding, and MFA enablement — with verification evidence captured through audit logging.

---

## ✅ What I Implemented (Special Note: Some operations were no authorized due to licensing. I do not currently pay for a Microsoft business account to perform labs)
- **Created Entra ID users** (manual creation for a test user)
- **Bulk created users via CSV import** (standard provisioning workflow)
- **Created and configured a Microsoft 365 group** and managed membership
- **Assigned an administrative role** to a test user (for RBAC/role testing)
- **Invited an external guest user (B2B)** for collaboration
- **Enabled per-user MFA** for a test account (lab method)
- **Validated changes using Entra ID Audit Logs** (evidence-based verification)

---

## 🧰 Tools & Platform
- Microsoft Entra admin center (Entra ID / Azure AD)
- Users, Groups, Assigned Roles
- Per-user MFA
- Audit Logs (verification)

---

## 🏗️ Architecture (Logical)
**Admin Actions → Entra ID Objects (Users/Groups/Roles/Guest) → Verification in Audit Logs**

This lab focuses on the operational flow that IAM teams use daily:
- Change → Evidence → Documentation

---

## 📝 Runbook
A 1-page, repeatable procedure is included:
- [`runbook/implementation.md`](runbook)

---

## 🔍 Verification & Evidence
Each major action was verified using **Audit Logs**:
- Administrative changes show **Status: Success**
- Targets and actors match expected user/group actions

📁 Evidence screenshots are stored in:
- [`/screenshots`](screenshots)

---

## 📸 Screenshot Index
| # | Action | Evidence File |
|---|--------|--------------|
| 1 | User creation (manual) | `Creating Entra User BillyJ (2-26-26).png` |
| 2 | Bulk user import (CSV) | `Bulk Importing Users (2-26-26).png` |
| 3 | Group creation (Project01) | `Creating Project01 Group (2-26-26).png` |
| 4 | Admin role assignment | `Assigning Role for Billy Jean (2-26-26).png` |
| 5 | Guest user invitation (B2B) | `Creating External User (2-26-26).png` |
| 6 | Enable per-user MFA | `Enabling MFA for BillyJ (2-26-26).png` |
| 7 | Audit log verification | `Reviewing Audit Logs (2-26-26).png` |

---

## 🧠 Key IAM Takeaways
- **Evidence matters:** Audit logs are essential for validating IAM changes and supporting audits.
- **Bulk provisioning is powerful** but requires strict CSV formatting and validation.
- **Least privilege is the goal:** Role assignment should be minimal, approved, and time-bound in real environments.
- **Guest access needs governance:** B2B invitations should align to policy (domains, access reviews, expiration).

---

## 🔐 Security Notes (Portfolio Safe)
Before uploading evidence to a public repository:
- Blur/crop tenant IDs, object IDs, and personal emails
- Avoid exposing secrets, URLs with tenant GUIDs, or internal identifiers

---

## 🚀 Next Enhancements
Planned upgrades to expand this project:
- Conditional Access policy enforcement for MFA (recommended method in production)
- Group-based access assignment model (least-privilege patterns)
- Access review workflow (identity governance)
- Sign-in log analysis for authentication troubleshooting

---

## 📫 Contact
If you'd like to discuss IAM operations, Entra ID, or my AZ-500 progress:
- LinkedIn: *(add your link here)*
