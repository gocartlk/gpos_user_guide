---
title: Credit sales
description: Let a customer take goods now and pay later, in parts — credit limits, manager approval, taking payments at the till, returns, and the customer's balance in the back office.
sidebar:
  order: 4.5
  badge:
    text: New
    variant: tip
---

:::note[Depends on your plan]
**Credit sales and customer balances** is a plan feature, part of the **Customer list**. Without it,
the till has no <span class="ui">Credit</span> payment or <span class="ui">Receive payment</span>
button. See [Plans and features](/getting-started/plans/).
:::

A regular customer can **take the goods now and pay later**, in one go or in parts. GPOS keeps
what each customer owes, which sales are still unpaid, and every payment.

## Before you start

- The customer must have a profile in [Customers](/sales/customers/) — sales on credit are always
  for a named customer.
- Set the customer's **credit limit** — the most they may owe — in the back office (see
  [Set a credit limit](#set-a-credit-limit)). Without a limit, a manager must approve **every**
  credit sale for that customer.

## Sell on credit

1. Add the customer to the sale (**F3**) — see [Customers at the till](/till/customers/).
2. Select <span class="ui">Pay</span> (**F4**) and choose **Credit**.
3. The till shows the customer's **Credit limit**, what they **Owe now**, **This sale** and what
   they **Will owe**. The credit is always **the whole amount still to pay** — nothing is typed.
4. Select <span class="ui">Complete sale</span>.

The customer pays part now? Take that part first — for example choose **Cash**, change the
**Amount** and select <span class="ui">Take {amount}, then the rest</span> — then choose **Credit**
for the rest. Cash plus credit works even without the **Split payment** feature.

Without a customer on the sale, the till says *Add a customer to the sale to sell on credit.*

### When a manager must approve

The till asks for a manager's PIN when:

- the sale takes the customer **over their limit** — *Credit limit exceeded. A manager must
  approve.*;
- the customer has **no limit** — *This customer has no credit limit. A manager must approve.*;
- the cashier's role may not sell on credit.

The manager checks the figures on the screen and enters their PIN; the sale then completes.

## Receive a payment

Payments for credit sales are taken **on the till**, into the open shift's drawer — also for bank
transfers (record them like a card or QR payment, with the reference).

1. Select <span class="ui">Receive payment</span> at the top of the till (**Ctrl + B**). A **shift
   must be open**.
2. Search the **Customer name or phone**, or pick from **Customers who owe**.
3. The till shows what the customer **Owes** and the **sales not yet paid**. Optionally tick the
   sales this payment is for (*Pay these sales*); otherwise it pays the **oldest sales first**.
4. Choose the payment method and the amount. For cash, type what you received; the till gives the
   change. It shows *Will still owe …* for a part payment.
5. Select <span class="ui">Take {amount}</span>.

A **PAYMENT RECEIVED** receipt prints with the sales it paid (*For: …*) and the **Balance owing**.
It also appears in **Sales** (**F9**) marked *Payment*, and can be reprinted from there.

One payment uses **one method** — part cash, part card is two payments.

## Returns and voids

- A **return** of something bought on credit first **reduces what the customer owes**; only the
  rest is refunded as money. The till shows *… comes off what the customer owes.*
- A credit sale that has **already received a payment** cannot be voided — *A payment was
  received for this sale, so it cannot be voided. Use a return.* See
  [Returns and voids](/till/returns-voids/).

## Offline

Credit sales and payments **work offline**:

- The limit is checked against the customer's balance from the last sync, plus this till's own
  sales and payments since. Two tills offline at the same time do not know each other's sales —
  with a [local hub](/business/local-hub/) they do.
- Offline, the till cannot show the customer's open sales: *Offline: the sales cannot be shown.
  The payment goes against the balance, oldest sales first.*
- If two tills collected the same debt, both payments stand; the extra stays on the customer as an
  **Advance (paid in excess)**, used for their next credit sales.

## In the back office

### The customer's credit

Open the customer in [Customers](/sales/customers/). The **Credit** section shows:

- the **Balance owing** (or an **Advance**, if they paid in excess);
- the **Credit limit**;
- **Sales not fully paid** — each receipt with what was **On credit** and what is **Still owed**;
- the **Statement** — every credit sale, payment and return with the running balance.

### Set a credit limit

Under **Credit**, type the **Credit limit** and save. Leave it empty for **no limit**: a manager
then approves every credit sale on the till. Tills receive the new limit on their next sync.

A customer who **owes money** cannot be made inactive or erased — settle the balance first.

### Shifts and reports

- A credit sale is **not money received**. On the shift it shows as *on credit*; it is not in the
  expected cash.
- Payments received count in the shift that **took** them (*Credit payments received*), and cash
  payments are part of the drawer's expected cash. The till's X report and close show them too.
- **Payments by method** counts the payments when they are received, not the credit.
- The **Credit outstanding** report lists what each customer still owes, by how old the sales are:
  **0–30**, **31–60**, **61–90** and **Over 90 days**. See [Reports](/reports/reports/).

## Who can do what

| Permission | Who by default | Allows |
|------------|----------------|--------|
| **Sell on credit within the customer's limit** | Owner, Administrator, Manager, Cashier | Choose Credit at the till. |
| **Approve credit beyond the limit and set credit limits** | Owner, Administrator, Manager | Approve at the till; set limits in the back office. |
| **Receive payments for credit sales** | Owner, Administrator, Manager, Cashier | The Receive payment screen. |

Take a permission away from a role in [Roles](/business/roles/) — for example so that only
managers take payments.
