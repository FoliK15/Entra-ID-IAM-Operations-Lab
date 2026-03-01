# Project Summary — Microsoft Entra ID IAM Operations Lab

## Overview
This project demonstrates core Identity & Access Management (IAM) operational capabilities using Microsoft Entra ID (Azure AD). The goal was to perform common IAM tasks that identity teams execute daily and validate each change using audit evidence.

## What I Built
- Created a test Entra ID user (manual provisioning) and confirmed account status
- Bulk provisioned multiple users using a CSV import workflow
- Created a Microsoft 365 group and configured membership for access organization
- Assigned an administrative role to a test user (for controlled RBAC/role testing)
- Invited an external guest (B2B) user to validate external collaboration onboarding
- Enabled per-user MFA for a test account (lab method)
- Verified administrative activity using Entra ID Audit Logs (evidence-based validation)

## Evidence & Validation
- Configuration evidence is captured in `/screenshots`
- Verification evidence is supported through Entra ID **Audit Logs** showing successful administrative actions and correct targets/actors

## Skills Demonstrated (IAM-Relevant)
- Identity lifecycle operations (manual + bulk provisioning)
- Group-based access organization and membership management
- Role assignment concepts (RBAC / directory roles) and least-privilege awareness
- External identity onboarding (B2B guest invite workflow)
- Authentication hardening (MFA enablement)
- Audit evidence collection and change validation

## Why This Matters
IAM teams depend on consistent operational execution and proof of changes for troubleshooting and audits. This lab mirrors real IAM work by focusing on:
**change → verification → documentation**.

## Next Enhancements
- Implement Conditional Access policies to enforce MFA (production-recommended approach)
- Add group-based access patterns for least-privilege role separation
- Build an access review workflow (identity governance) and document outcomes
- Add sign-in log analysis scenarios for authentication troubleshooting
