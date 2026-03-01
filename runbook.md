# Runbook: Microsoft Entra ID IAM Operations (Users, Groups, MFA, Guest Access)

## Purpose
Provide a repeatable process to perform core Microsoft Entra ID (Azure AD) IAM operational tasks:
- Create users (manual + bulk import)
- Create and manage a group
- Assign an administrative role (for controlled testing)
- Invite an external (B2B) guest user
- Enable MFA for a target user
- Validate actions using Audit Logs

## Scope
Applies to Microsoft Entra ID tenant administration for lab/demo environments.  
**Production note:** Follow organization change control, approvals, and least-privilege policy.

## Preconditions / Requirements
- Admin access to Microsoft Entra admin center
- Tenant has available identities and permissions to create users/groups
- CSV template prepared for bulk user creation
- A test user exists for MFA and role assignment validation
- External email address available for guest invite testing

## Procedure

### A) Create a user (manual)
1. Go to **Microsoft Entra admin center → Identity → Users → All users → New user**.
2. Create user with required attributes (Display name, UPN, password).
3. Confirm the user appears in **All users** and is **enabled**.

**Expected result:** User account is created successfully and visible in directory.

---

### B) Bulk create users (CSV import)
1. Go to **Users → Bulk operations → Bulk create**.
2. Download the CSV template (if needed) and populate:
   - `displayName`, `userPrincipalName`, `passwordProfile`, `accountEnabled`, `givenName`, `surname`
3. Upload the CSV file and start the import.
4. Monitor **Bulk operation results** and confirm success.

**Expected result:** Multiple users are created and visible in **All users**.

---

### C) Create a group and add membership
1. Go to **Identity → Groups → All groups → New group**.
2. Select group type (e.g., **Microsoft 365** or **Security** based on lab goal).
3. Set **Group name**, **Description**, and **Membership type** (Assigned).
4. Add at least one member and create.

**Expected result:** Group is created and membership is correct.

---

### D) Assign an administrative role (controlled testing)
> Use least privilege. Assign roles only to test accounts in a lab.

1. Go to **Users → select user → Assigned roles → Add assignments**.
2. Choose the role required for testing (example from lab: a built-in directory role).
3. Confirm the role shows as assigned.

**Expected result:** Role assignment is visible on the user under **Assigned roles**.

---

### E) Invite external guest user (B2B)
1. Go to **Users → New guest user / Invite external user**.
2. Enter guest email and display name.
3. (Optional) Customize invite message and set redirect URL.
4. Review + invite.

**Expected result:** Guest user object is created (User type: Guest) and invitation is sent.

---

### F) Enable MFA (per-user MFA for lab)
> Note: In production, Microsoft recommends MFA enforcement via **Conditional Access** rather than per-user MFA.

1. Go to **Protection / Security → MFA → Per-user MFA** (or the relevant MFA blade in your tenant).
2. Select the target user.
3. Click **Enable** (or **Enforce** depending on lab requirement).
4. User completes MFA registration at next sign-in.

**Expected result:** MFA status changes for the user, and registration is prompted on sign-in.

---

## Verification (Evidence)
1. Go to **Monitoring → Audit logs** and filter by:
   - Activity (e.g., “Add user”, “Add group”, “Add member to group”, “Update MFA”, “Invite external user”)
   - Target user(s) and group(s)
2. Confirm each action shows **Status: Success** and includes correct actor/target.

**Artifacts to capture (for portfolio):**
- 1 screenshot per major action (config view)
- 1 screenshot of Audit Logs showing successful actions (verification)

## Troubleshooting (Common Issues)
- **Bulk import failures:** CSV formatting, missing required columns, invalid UPN domain, password policy violations.
- **User not visible after import:** Refresh portal; check Bulk operation results; verify filters/search.
- **Role assignment blocked:** Insufficient admin permissions; role restricted; ensure you are authorized.
- **Guest invite not received:** Wrong email, spam filtering, or tenant restrictions for B2B invitations.
- **MFA not prompting:** User already registered, per-user MFA not enabled, or sign-in method not supported; confirm MFA status and test sign-in.

## Rollback / Cleanup (Lab hygiene)
- Remove test role assignment after validation.
- Delete lab users/groups when complete to keep tenant clean.
- Document what was changed and retain audit evidence before cleanup.
