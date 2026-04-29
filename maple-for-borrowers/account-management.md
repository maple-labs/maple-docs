---
hidden: true
---

# Account Management

Account Management covers how your team accesses Maple, the roles assigned to each user, and the wallets approved to transact onchain on your loans.

Maple borrower accounts are built around three concepts:

* **Organization**: your top-level Maple account.
* **Legal Entity**: one or more legal entities under your Organization that hold loans, e.g. a fund vehicle, an offshore subsidiary.
* **User**: a member of your team who can log into the app.

A single team can manage multiple borrowing entities under one login, with portfolio-level visibility and loan management per entity.

## Users and roles

Maple sets up your first Admin during onboarding. From there, Admins and Managers can invite team members and assign or change roles.

<table><thead><tr><th width="147.32464599609375">Role</th><th>Access</th></tr></thead><tbody><tr><td>Admin</td><td>Full access. Manage users and execute all loan actions.</td></tr><tr><td>Manager</td><td>All loan actions plus add and remove non-Admin users.</td></tr><tr><td>Loan Actions</td><td>Execute all loan actions across entities. No user management.</td></tr><tr><td>Viewer</td><td>Read-only. View entities, loans, payments, and wallets.</td></tr></tbody></table>

## Inviting and removing users

Admins and Managers manage users from Account Settings → Team Management:

* **Invite**: enter an email and assign a role. The invitee receives an email to set up their login.
* **Change role**: update a user's role.
* **Remove**: access is revoked immediately.

![Team Management](<../.gitbook/assets/image (12).png>)

## Borrower wallets

Loan actions are signed onchain, so taking an action requires:

1. A role with action permissions (Admin, Manager, or Loan Actions).
2. A borrower wallet registered with Maple for the relevant Legal Entity.

Borrower wallets are added by the Maple team during onboarding. To add or remove a wallet, contact Maple. Any wallet can pay interest. Only approved borrower wallets can receive funds, accept a refinance, and repay a loan.

Onchain actions are subject to your wallet's own signing requirements (e.g. multi-sig quorum), independent of Maple's role-based permissioning.
