---
hidden: true
---

# Account Management

Maple borrower accounts are built around three concepts:

* **Organization** - your top-level Maple account
* **Legal Entity** - one or more legal entities under your Organization that hold loans, e.g. a fund vehicle, an offshore subsidiary
* **User** - a member of your team that can log into the app

A single team can manage multiple borrowing entities under one login, with portfolio-level visibility and per-entity loan management.

## Users and roles

Maple sets up your first Admin during onboarding. From there, Admins & Managers can invite team members, assign and change roles.

<table><thead><tr><th width="173.6961669921875">Role</th><th>Access</th></tr></thead><tbody><tr><td>Admin</td><td>Full access. Manage users and execute all loan actions</td></tr><tr><td>Manager</td><td>All loan actions plus add and remove non-Admin users</td></tr><tr><td>Loan Actions</td><td>Execute all loan actions across entities. No user management</td></tr><tr><td>Viewer</td><td>Read-only. View entities, loans, payments and wallets</td></tr></tbody></table>

## Inviting and removing users

Admins and Managers manage users from Account Settings → Team Management:

* **Invite** - enter an email and assign a role. The invitee receives an email to set up their login
* **Change role** - update a user's role in place
* **Remove** - access is revoked immediately

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

## Borrower wallets

Loan actions are signed onchain, so taking an action requires:

1. A role with action permissions (Admin, Manager or Loan Actions)
2. A borrower wallet registered with Maple for the relevant Legal Entity

Borrower wallets are added by the Maple team at onboarding. To add or remove a wallet, contact Maple. Any wallet can pay interest. Only your approved borrower wallet can receive funds, accept a refinance and repay a loan.

For onchain action workflows, see [Loan Management](https://docs.maple.finance/maple-for-borrowers/loan-management).
