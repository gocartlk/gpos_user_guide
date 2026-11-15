---
title: Offline and sync
description: How the till keeps selling without internet, how to read the sync status, and what to do when something needs attention.
sidebar:
  order: 10
---

:::note[Depends on your plan]
This page is part of the **Selling at the counter (POS), cash shifts and tills** feature. If it is not in your plan, you will not see it in the menu. See [Plans and features](/getting-started/plans/).
:::

The till keeps a copy of your products, prices, staff PINs, customers and settings **on the
device**. When the internet is down it carries on selling and stores the sales. When the
connection is back it sends them automatically. **Nothing is lost**, as long as the till's browser
data is not deleted.

## The status bar

| Shows | Meaning |
|-------|---------|
| **Online · All synced** | Everything has reached the back office. |
| **Syncing…** | Sending now. |
| **Offline · {n} waiting** | No internet. {n} sales or other operations are stored on the till. Keep selling. |
| **Sync error · {n} need attention** | Something could not be sent — see below. |
| **Last sync …** | When the till last talked to the back office. |

With a [local hub](/business/local-hub/), the bar also says how the till is connected — for
example *Online · via hub Back office PC*, *Hub Back office PC · cloud offline · 12 safe on the
hub*, or *Hub not reachable · selling offline*. Sales the hub holds show as **On the hub**.

## Works offline / needs internet

| Works offline | Needs internet |
|---------------|----------------|
| Selling, payments, discounts, approvals | Setting up or re-authorising the till |
| Opening and closing shifts, cash in/out | Finding a sale made on **another till** |
| Returns of sales from **this** till | Getting new prices, products, PINs (on the next sync) |
| Adding customers | [Stock](/till/stock-at-till/) (without a local hub) |
| [Credit sales and payments](/till/credit-sales/) | |

## The sync panel

Select the status bar to open **Sync and this till**:

- <span class="ui">Sync now</span> — try sending immediately.
- **Waiting and problem operations** — each one with its status: *Waiting*, *Sending*, *Needs
  attention*, *Waiting for a manager*.
- <span class="ui">Try again</span> — resend one that failed.
- <span class="ui">Export (JSON)</span> — save the waiting operations to a file as a backup. Shown
  to people who can manage POS devices (owners and administrators). Use it before replacing a
  till that cannot connect. Keep the file and give it to your service provider: it cannot be
  loaded back yet, but they can use it to reconcile the sales by hand.
- <span class="ui">Download everything again</span> — if the catalog on the till looks wrong.
  **Waiting operations are kept.**
- Details of **This till**: register, branch, app version, storage and screen status.
- **Local hub** — when the branch has a hub: its address and when it last reached the cloud.
  On a till not yet using it, <span class="ui">Move to the hub</span> (see
  [Local hub](/business/local-hub/#3-connect-the-tills)).

## "Waiting for a manager"

The back office could not accept something exactly as recorded — for example the cashier lost a
permission while offline. It is **not dropped**: an administrator decides in
[POS devices → Sync issues](/business/pos-devices/#sync-issues).

## A new version is ready

When the till shows *A new version is ready*, select <span class="ui">Update now</span> between
customers. The till never updates in the middle of a sale.

A till looks for a new version when it is opened. If it stays open all day, select
<span class="ui">Check for updates</span> (the **↻** button in the top bar, also on the lock
screen) to look at once. It shows *Checking for updates…*, then either the *A new version is
ready* banner or *Up to date (version …)*. Offline, it says to check again when the network is
back.

:::danger[Never clear a till's browser data]
Clearing site data, using incognito mode or resetting the browser deletes anything still waiting.
If you must replace a till, decommission it first and wait for **All synced**.
:::
