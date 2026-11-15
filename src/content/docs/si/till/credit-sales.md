---
title: Credit sales
description: Customer කෙනෙකුට දැන් බඩු අරන් පස්සේ, කොටස් වශයෙනුත් ගෙවන්න දෙන්න — credit limits, manager approval, till එකේ payments ගැනීම, returns, සහ back office එකේ customer ගේ balance එක.
sidebar:
  order: 4.5
  badge:
    text: අලුත්
    variant: tip
---

:::note[ඔබේ plan එක අනුව වෙනස් වේ]
**Credit sales and customer balances** කියන්නේ **Customer list** එකේ කොටසක් වන plan feature එකක්. ඒක නැත්නම් till එකේ
<span class="ui">Credit</span> payment එකක් හෝ <span class="ui">Receive payment</span> button එකක් නැහැ.
[Plans and features](/si/getting-started/plans/) බලන්න.
:::

නිතර එන customer කෙනෙකුට **දැන් බඩු අරන් පස්සේ ගෙවන්න** පුළුවන් — එක පාරට හෝ කොටස් වශයෙන්. හැම customer කෙනෙක්ම කොච්චර
ණයද, තවම ගෙවලා නැති sales මොනවද, හැම payment එකක්ම GPOS තියාගන්නවා.

## පටන් ගන්න කලින්

- Customer ට [Customers](/si/sales/customers/) හි profile එකක් තියෙන්න ඕන — credit sales හැමවිටම නමක් තියෙන customer කෙනෙකුට.
- Back office එකේ customer ගේ **credit limit** එක — ණය වෙන්න පුළුවන් උපරිමය — set කරන්න (පහත *Credit limit එකක් set කරන්න*
  බලන්න). Limit එකක් නැත්නම්, ඒ customer ගේ **හැම** credit sale එකක්ම manager කෙනෙක් approve කරන්න ඕන.

## Credit එකට විකුණන්න

1. Customer ව sale එකට add කරන්න (**F3**) — [Customers at the till](/si/till/customers/) බලන්න.
2. <span class="ui">Pay</span> (**F4**) තෝරා **Credit** තෝරන්න.
3. Till එක customer ගේ **Credit limit**, දැන් ණය ගණන (**Owes now**), **This sale** සහ ණය වෙන ගණන (**Will owe**) පෙන්නනවා.
   Credit එක හැමවිටම **තවම ගෙවන්න තියෙන මුළු ගණනයි** — මුකුත් type කරන්න ඕන නැහැ.
4. <span class="ui">Complete sale</span> තෝරන්න.

Customer දැන් කොටසක් ගෙවනවද? ඒ කොටස මුලින් ගන්න — උදා. **Cash** තෝරා **Amount** එක වෙනස් කර
<span class="ui">Take {amount}, then the rest</span> තෝරන්න — ඉතිරිය සඳහා **Credit** තෝරන්න. **Split payment** feature එක
නැතත් cash සහ credit එකට වැඩ කරනවා.

Sale එකේ customer කෙනෙක් නැත්නම් till එක *Add a customer to the sale to sell on credit.* කියනවා.

### Manager කෙනෙක් approve කරන්න ඕන වෙලාවල්

Till එක manager ගේ PIN එක අහනවා:

- sale එකෙන් customer **limit එක ඉක්මවනවා නම්** — *Credit limit exceeded. A manager must approve.*;
- customer ට **limit එකක් නැත්නම්** — *This customer has no credit limit. A manager must approve.*;
- cashier ගේ role එකට credit එකට විකුණන්න අවසර නැත්නම්.

Manager screen එකේ ගණන් බලලා PIN එක ගහනවා; එතකොට sale එක complete වෙනවා.

## Payment එකක් ගන්න

Credit sales වල payments ගන්නේ **till එකේ**, open shift එකේ drawer එකට — bank transfers වුණත් (card හෝ QR වගේ reference
එකත් එක්ක record කරන්න).

1. Till එකේ උඩ තියෙන <span class="ui">Receive payment</span> තෝරන්න (**Ctrl + B**). **Shift එකක් open වෙලා තියෙන්න ඕන.**
2. **Customer name or phone** search කරන්න, නැත්නම් **Customers who owe** list එකෙන් තෝරන්න.
3. Till එක customer ණය ගණන (**Owes**) සහ **තවම ගෙවලා නැති sales** පෙන්නනවා. ඕන නම් මේ payment එක අදාළ sales tick කරන්න
   (*Pay these sales*); නැත්නම් **පරණම sales මුලින්** ගෙවනවා.
4. Payment method එක සහ amount එක තෝරන්න. Cash නම් ලැබුණු ගණන type කරන්න; till එක change එක පෙන්නනවා. කොටසක් ගෙව්වොත්
   *Will still owe …* පෙන්නනවා.
5. <span class="ui">Take {amount}</span> තෝරන්න.

ගෙවපු sales (*For: …*) සහ **Balance owing** එක්ක **PAYMENT RECEIVED** receipt එකක් print වෙනවා. ඒක **Sales** (**F9**) හි
*Payment* ලෙසත් පෙන්නනවා, එතනින් ආයෙත් print කරන්න පුළුවන්.

එක payment එකකට **එක method එකයි** — කොටසක් cash, කොටසක් card නම් payments දෙකක්.

## Returns සහ voids

- Credit එකට ගත්ත දෙයක **return** එකක් මුලින්ම **customer ගේ ණය අඩු කරනවා**; ඉතිරිය විතරයි සල්ලි විදිහට ආපහු දෙන්නේ. Till එක
  *… comes off what the customer owes.* පෙන්නනවා.
- **දැනටමත් payment එකක් ලැබුණු** credit sale එකක් void කරන්න බැහැ — *A payment was received for this sale, so it cannot be
  voided. Use a return.* [Returns සහ voids](/si/till/returns-voids/) බලන්න.

## Offline

Credit sales සහ payments **offline වැඩ කරනවා**:

- Limit එක check කරන්නේ අන්තිම sync එකේ customer ගේ balance එකට, ඊට පස්සේ මේ till එකේම sales සහ payments එකතු කරලා. එකම
  වෙලාවේ offline ඉන්න tills දෙකක් එකිනෙකාගේ sales දන්නේ නැහැ — [local hub](/si/business/local-hub/) එකක් එක්ක දන්නවා.
- Offline ඉන්නකොට till එකට customer ගේ open sales පෙන්නන්න බැහැ: *Offline: the sales cannot be shown. The payment goes
  against the balance, oldest sales first.*
- Tills දෙකක් එකම ණය එකතු කළොත් payments දෙකම තියෙනවා; වැඩිපුර ගෙවපු ගණන customer ට **Advance (paid in excess)** එකක් විදිහට
  ඉතුරු වෙනවා, ඊළඟ credit sales වලට ගණන් වෙනවා.

## Back office එකේ

### Customer ගේ credit

[Customers](/si/sales/customers/) හි customer ව open කරන්න. **Credit** කොටසේ පෙන්නනවා:

- **Balance owing** (නැත්නම් වැඩිපුර ගෙව්වා නම් **Advance**);
- **Credit limit**;
- **Sales not fully paid** — හැම receipt එකකම **On credit** ගණන සහ තවම ණය (**Still owed**) ගණන;
- **Statement** — හැම credit sale, payment සහ return එකක්ම running balance එක එක්ක.

### Credit limit එකක් set කරන්න

**Credit** යටතේ **Credit limit** type කර save කරන්න. **Limit එකක් නැත්නම්** හිස්ව තියන්න: එතකොට till එකේ හැම credit sale
එකක්ම manager කෙනෙක් approve කරනවා. ඊළඟ sync එකේදී tills වලට අලුත් limit එක ලැබෙනවා.

**ණය තියෙන** customer කෙනෙක් inactive කරන්න හෝ erase කරන්න බැහැ — මුලින් balance එක settle කරන්න.

### Shifts සහ reports

- Credit sale එකක් **ලැබුණු සල්ලි නෙවෙයි**. Shift එකේ ඒක *on credit* ලෙස පෙන්නනවා; expected cash එකට ගණන් වෙන්නේ නැහැ.
- ලැබුණු payments ගණන් වෙන්නේ ඒවා **ගත්ත** shift එකේ (*Credit payments received*), cash payments drawer එකේ expected cash එකට
  එකතු වෙනවා. Till එකේ X report එකේ සහ close එකේත් ඒවා පෙන්නනවා.
- **Payments by method** report එක payments ගණන් කරන්නේ ඒවා ලැබුණු වෙලාවේ, credit එක නෙවෙයි.
- **Credit outstanding** report එක හැම customer කෙනෙක්ම තවම ණය ගණන sales වල වයස අනුව පෙන්නනවා: **0–30**, **31–60**, **61–90**
  සහ **Over 90 days**. [Reports](/si/reports/reports/) බලන්න.

## කාටද මොනවා කරන්න පුළුවන්

| Permission | Default විදිහට කාටද | ඉඩ දෙන දේ |
|------------|----------------------|-----------|
| **Sell on credit within the customer's limit** | Owner, Administrator, Manager, Cashier | Till එකේ Credit තෝරන්න. |
| **Approve credit beyond the limit and set credit limits** | Owner, Administrator, Manager | Till එකේ approve කරන්න; back office එකේ limits set කරන්න. |
| **Receive payments for credit sales** | Owner, Administrator, Manager, Cashier | Receive payment screen එක. |

[Roles](/si/business/roles/) හි role එකකින් permission එකක් අයින් කරන්න පුළුවන් — උදා. payments ගන්න managers ට විතරක් දෙන්න.
