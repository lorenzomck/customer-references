# Visual Studio Bundles And GitHub Enterprise Guide

## Purpose

Use this guide to explain how Visual Studio subscriptions with GitHub Enterprise affect GitHub Enterprise licensing, assignment reconciliation, and true-up sizing. The language is customer-safe and can be adapted for emails to administrators, procurement owners, and Microsoft licensing stakeholders.

## Short Answer

GitHub Enterprise coverage can come from more than one licensing pool. Some users may be covered by qualifying Visual Studio subscriptions that include GitHub Enterprise, while other users may be covered by standalone GitHub Enterprise seats.

When the counts do not line up, the first step is to separate those pools and confirm which GitHub users match the Visual Studio subscribers who are entitled to bundled GitHub Enterprise access. After that reconciliation, size any standalone GitHub Enterprise true-up only for users who are not covered by qualifying matched Visual Studio bundled entitlements.

## Licensing Pools

| Pool | What It Means | What To Check |
|---|---|---|
| Visual Studio bundled GitHub Enterprise | GitHub Enterprise entitlement associated with qualifying Visual Studio subscriptions | Whether each GitHub user is matched to the corresponding Visual Studio subscriber |
| Standalone GitHub Enterprise | GitHub Enterprise seats purchased separately from the Visual Studio bundle | Purchased seats, assigned users, renewal timing, and any overage |

Some customers also evaluate usage-based billing for GitHub Enterprise. Treat that as a separate billing-model decision after the current assignment and entitlement reconciliation is understood.

## Why Counts Differ

Common causes include:

- A GitHub user has access, but that user is not the named Visual Studio subscriber.
- Visual Studio subscription assignments changed, but GitHub assignments did not change at the same time.
- A renewal or anniversary true-up changed Visual Studio bundled coverage.
- Standalone GitHub Enterprise seats and Visual Studio bundled entitlements are being viewed together without separating the pools.
- Microsoft enrollment or subscription assignment details differ from what is visible in GitHub.

## Reconciliation Workflow

| Step | Action | Typical Owner |
|---|---|---|
| 1 | Review GitHub Enterprise license usage and download the license details CSV from the enterprise licensing page | Enterprise owner or billing manager |
| 2 | Review Visual Studio subscriber assignments for subscriptions that include GitHub Enterprise | Visual Studio subscriptions admin or Microsoft licensing owner |
| 3 | Compare GitHub users against Visual Studio subscribers and identify matched, pending, unmatched, and standalone-only users | Customer licensing owner with GitHub and Microsoft account teams |
| 4 | Correct Visual Studio assignment, invitation, or identity alignment where needed | Visual Studio subscriptions admin or Microsoft licensing owner |
| 5 | Recalculate the standalone GitHub Enterprise requirement after assignment cleanup | Customer licensing owner and GitHub account team |

The practical rule is:

```text
incremental standalone true-up = max(0, standalone GitHub Enterprise users not covered by qualifying matched Visual Studio bundled entitlements - purchased standalone GitHub Enterprise seats)
```

## True-Up Example

Example starting point:

| Pool | Purchased | Current State | Initial Readout |
|---|---:|---:|---|
| Standalone GitHub Enterprise | 1,000 | 1,500 users consuming standalone GitHub Enterprise | 500 users above the standalone purchase |
| Visual Studio subscriptions with GitHub Enterprise | 2,500 | Assignment and match status still needs review | Potential bundled coverage may exist, but it must be reconciled |

In this case, the visible standalone gap is 500 users before reconciliation. The recommendation is not to automatically place a 500-seat standalone GitHub Enterprise true-up before checking whether some of the 1,500 standalone-consuming users are qualifying Visual Studio subscribers.

If 500 of those 1,500 standalone-consuming users can be correctly matched to qualifying Visual Studio subscriptions with GitHub Enterprise, the incremental standalone true-up may be zero. If those users cannot be matched or are not eligible for bundled coverage, the standalone true-up may remain 500 seats.

## Customer-Ready Email Templates

### Short Explanation

Subject: Visual Studio and GitHub Enterprise licensing

Hi {FirstName},

The short version is that GitHub Enterprise coverage can come from two places: qualifying Visual Studio subscriptions that include GitHub Enterprise, and standalone GitHub Enterprise seats.

If a GitHub user is covered by the Visual Studio bundle, that user needs to line up with the corresponding Visual Studio subscriber. If they are not covered by that bundle, they need standalone GitHub Enterprise coverage or the applicable billing model.

The clean next step is to compare the GitHub license details with the Visual Studio subscriber assignment list so we can separate matched users from users who need a different coverage path.

Best,
Brian LaFlamme

### Renewal Or Anniversary Change

Subject: GitHub Enterprise licensing at renewal

Hi {FirstName},

The renewal impact depends on how many GitHub Enterprise users remain covered by Visual Studio subscriptions after the renewal or anniversary change.

If the Visual Studio-bundled pool is reduced, some users who were previously covered by that bundle may need standalone GitHub Enterprise coverage. The safest way to model this is:

1. Confirm current Visual Studio-bundled GitHub Enterprise coverage.
2. Confirm expected Visual Studio-bundled GitHub Enterprise coverage after {renewal_or_anniversary_date}.
3. Confirm standalone GitHub Enterprise seats currently purchased.
4. Reconcile GitHub users against qualifying Visual Studio subscribers.
5. Size standalone GitHub Enterprise only for users who are not covered by qualifying matched Visual Studio bundled entitlements.

Once those numbers are validated, we can confirm whether the current standalone GitHub Enterprise seats are enough or whether a true-up is needed.

Best,
Brian LaFlamme

### Procurement True-Up Explanation

Subject: GitHub Enterprise licensing reconciliation

Hi {FirstName},

For procurement purposes, I would separate this into the Visual Studio-bundled GitHub Enterprise pool and the standalone GitHub Enterprise pool.

Using the example numbers we discussed: if you purchased 1,000 standalone GitHub Enterprise seats and 1,500 users are currently consuming standalone GitHub Enterprise, that creates a visible 500-user standalone gap before reconciliation. The next step is to determine whether any of those 1,500 users are qualifying Visual Studio subscribers who should be covered by Visual Studio bundled GitHub Enterprise instead.

If 500 of those users can be correctly matched to qualifying Visual Studio subscriptions with GitHub Enterprise, then the incremental standalone true-up may be zero. If they cannot be matched or are not eligible for the bundled entitlement, then the standalone true-up may remain 500 seats.

The right order is:

1. Export GitHub Enterprise license details.
2. Review Visual Studio subscriber assignments.
3. Reconcile matched and unmatched users across the two systems.
4. Size any standalone GitHub Enterprise true-up only after that reconciliation.

Helpful references:

- GitHub Docs: Visual Studio subscriptions with GitHub Enterprise overview: https://docs.github.com/en/billing/managing-licenses-for-visual-studio-subscriptions-with-github-enterprise/about-visual-studio-subscriptions-with-github-enterprise
- GitHub Docs: Reconciling users across Visual Studio and GitHub: https://docs.github.com/en/enterprise-cloud@latest/billing/how-tos/set-up-payment/set-up-vs-subscription#reconciling-users-across-visual-studio-and-github
- Microsoft Learn: Set up GitHub Enterprise with Visual Studio subscriptions: https://learn.microsoft.com/en-us/visualstudio/subscriptions/access-github
- Visual Studio Subscriptions Admin Portal: https://manage.visualstudio.com/subscribers

Best,
Brian LaFlamme

### Name And Email Matching

Subject: Visual Studio subscriber matching

Hi {FirstName},

For Visual Studio subscriptions that include GitHub Enterprise, the important check is whether the GitHub user is matched to the Visual Studio subscriber who has that entitlement.

GitHub's enterprise licensing view can provide a license details export that helps show Visual Studio match status. If a user is not matched, compare the GitHub user identity against the Visual Studio subscriber assignment and determine whether the fix is on the GitHub assignment side, the Visual Studio assignment side, or both.

Best,
Brian LaFlamme

## Reference Links

- GitHub Docs: [Viewing usage for your GitHub Enterprise plan](https://docs.github.com/en/billing/how-tos/manage-plan-and-licenses/view-enterprise-usage)
- GitHub Docs: [About Visual Studio subscriptions with GitHub Enterprise](https://docs.github.com/en/billing/managing-licenses-for-visual-studio-subscriptions-with-github-enterprise/about-visual-studio-subscriptions-with-github-enterprise)
- GitHub Docs: [Reconciling users across Visual Studio and GitHub](https://docs.github.com/en/enterprise-cloud@latest/billing/how-tos/set-up-payment/set-up-vs-subscription#reconciling-users-across-visual-studio-and-github)
- Microsoft Learn: [Set up GitHub Enterprise with Visual Studio subscriptions](https://learn.microsoft.com/en-us/visualstudio/subscriptions/access-github)
- Microsoft Visual Studio Subscriptions Admin Portal: [manage.visualstudio.com/subscribers](https://manage.visualstudio.com/subscribers)