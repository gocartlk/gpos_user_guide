---
title: Credit sales
description: Customer இப்போது பொருட்களை எடுத்து பின்னர், பகுதி பகுதியாகவும் செலுத்த அனுமதியுங்கள் — credit limits, manager approval, till இல் payments பெறுதல், returns, back office இல் customer இன் balance.
sidebar:
  order: 4.5
  badge:
    text: புதியது
    variant: tip
---

:::note[உங்கள் plan ஐப் பொறுத்தது]
**Credit sales and customer balances** என்பது **Customer list** இன் பகுதியான plan feature. அது இல்லாவிட்டால் till இல்
<span class="ui">Credit</span> payment அல்லது <span class="ui">Receive payment</span> button இருக்காது.
[Plans and features](/ta/getting-started/plans/) ஐப் பாருங்கள்.
:::

வழக்கமான customer **இப்போது பொருட்களை எடுத்து பின்னர் செலுத்தலாம்** — ஒரே தடவையில் அல்லது பகுதி பகுதியாக. ஒவ்வொரு customer
உம் எவ்வளவு கடன்பட்டுள்ளார், இன்னும் செலுத்தப்படாத sales எவை, ஒவ்வொரு payment ஐயும் GPOS வைத்திருக்கும்.

## தொடங்குவதற்கு முன்

- Customer க்கு [Customers](/ta/sales/customers/) இல் profile இருக்க வேண்டும் — credit sales எப்போதும் பெயருள்ள customer க்கே.
- Back office இல் customer இன் **credit limit** ஐ — கடன்பட அனுமதிக்கப்பட்ட அதிகபட்சம் — set செய்யுங்கள் (கீழே *Credit limit
  ஐ set செய்யுங்கள்* ஐப் பாருங்கள்). Limit இல்லாவிட்டால், அந்த customer இன் **ஒவ்வொரு** credit sale ஐயும் manager approve செய்ய
  வேண்டும்.

## Credit இல் விற்பனை செய்யுங்கள்

1. Customer ஐ sale இல் சேருங்கள் (**F3**) — [Customers at the till](/ta/till/customers/) ஐப் பாருங்கள்.
2. <span class="ui">Pay</span> (**F4**) ஐத் தேர்ந்தெடுத்து **Credit** ஐத் தேர்ந்தெடுங்கள்.
3. Till customer இன் **Credit limit**, இப்போதைய கடன் (**Owes now**), **This sale**, ஆகப்போகும் கடன் (**Will owe**) ஐக் காட்டும்.
   Credit எப்போதும் **இன்னும் செலுத்த வேண்டிய முழுத் தொகை** — எதையும் type செய்ய வேண்டியதில்லை.
4. <span class="ui">Complete sale</span> ஐத் தேர்ந்தெடுங்கள்.

Customer இப்போது ஒரு பகுதியைச் செலுத்துகிறாரா? அந்தப் பகுதியை முதலில் பெறுங்கள் — உதா. **Cash** ஐத் தேர்ந்தெடுத்து **Amount**
ஐ மாற்றி <span class="ui">Take {amount}, then the rest</span> ஐத் தேர்ந்தெடுங்கள் — மீதிக்கு **Credit** ஐத் தேர்ந்தெடுங்கள்.
**Split payment** feature இல்லாவிட்டாலும் cash உம் credit உம் சேர்ந்து வேலை செய்யும்.

Sale இல் customer இல்லாவிட்டால் till *Add a customer to the sale to sell on credit.* எனச் சொல்லும்.

### Manager approve செய்ய வேண்டியபோது

Till manager இன் PIN ஐக் கேட்கும்போது:

- sale customer ஐ **limit ஐத் தாண்டச் செய்தால்** — *Credit limit exceeded. A manager must approve.*;
- customer க்கு **limit இல்லாவிட்டால்** — *This customer has no credit limit. A manager must approve.*;
- cashier இன் role க்கு credit இல் விற்க அனுமதி இல்லாவிட்டால்.

Manager screen இல் உள்ள தொகைகளைச் சரிபார்த்து PIN ஐ உள்ளிடுவார்; பின்னர் sale complete ஆகும்.

## Payment ஐப் பெறுங்கள்

Credit sales க்கான payments **till இல்** பெறப்படும், open shift இன் drawer க்கு — bank transfers உம் கூட (card அல்லது QR
போல reference உடன் record செய்யுங்கள்).

1. Till இன் மேலே உள்ள <span class="ui">Receive payment</span> ஐத் தேர்ந்தெடுங்கள் (**Ctrl + B**). **Shift open ஆக இருக்க
   வேண்டும்.**
2. **Customer name or phone** ஐ search செய்யுங்கள், அல்லது **Customers who owe** இலிருந்து தேர்ந்தெடுங்கள்.
3. Till customer இன் கடனை (**Owes**) மற்றும் **இன்னும் செலுத்தப்படாத sales** ஐக் காட்டும். விரும்பினால் இந்த payment எந்த
   sales க்கு என tick செய்யுங்கள் (*Pay these sales*); இல்லாவிட்டால் **பழைய sales முதலில்** செலுத்தப்படும்.
4. Payment method மற்றும் amount ஐத் தேர்ந்தெடுங்கள். Cash க்கு பெற்ற தொகையை type செய்யுங்கள்; till change ஐக் காட்டும்.
   பகுதியாகச் செலுத்தினால் *Will still owe …* எனக் காட்டும்.
5. <span class="ui">Take {amount}</span> ஐத் தேர்ந்தெடுங்கள்.

செலுத்திய sales (*For: …*) மற்றும் **Balance owing** உடன் **PAYMENT RECEIVED** receipt print ஆகும். அது **Sales** (**F9**)
இல் *Payment* எனவும் காட்டப்படும், அங்கிருந்து மீண்டும் print செய்யலாம்.

ஒரு payment க்கு **ஒரு method மட்டுமே** — பகுதி cash, பகுதி card என்றால் இரண்டு payments.

## Returns மற்றும் voids

- Credit இல் வாங்கியதன் **return** முதலில் **customer இன் கடனைக் குறைக்கும்**; மீதி மட்டுமே பணமாகத் திருப்பித் தரப்படும். Till
  *… comes off what the customer owes.* எனக் காட்டும்.
- **ஏற்கனவே payment பெற்ற** credit sale ஐ void செய்ய முடியாது — *A payment was received for this sale, so it cannot be
  voided. Use a return.* [Returns மற்றும் voids](/ta/till/returns-voids/) ஐப் பாருங்கள்.

## Offline

Credit sales உம் payments உம் **offline இல் வேலை செய்யும்**:

- Limit கடைசி sync இன் customer balance உடன், அதன் பின் இந்த till இன் சொந்த sales மற்றும் payments ஐச் சேர்த்துச் சரிபார்க்கப்படும்.
  ஒரே நேரத்தில் offline இல் உள்ள இரண்டு tills ஒன்றின் sales ஐ மற்றொன்று அறியாது — [local hub](/ta/business/local-hub/) உடன் அறியும்.
- Offline இல் till customer இன் open sales ஐக் காட்ட முடியாது: *Offline: the sales cannot be shown. The payment goes against
  the balance, oldest sales first.*
- இரண்டு tills ஒரே கடனை வசூலித்தால் இரண்டு payments உம் நிற்கும்; கூடுதலாகச் செலுத்தியது customer இன் **Advance (paid in
  excess)** ஆக இருக்கும், அடுத்த credit sales க்குக் கணக்கிடப்படும்.

## Back office இல்

### Customer இன் credit

[Customers](/ta/sales/customers/) இல் customer ஐ open செய்யுங்கள். **Credit** பகுதி காட்டுவது:

- **Balance owing** (அல்லது கூடுதலாகச் செலுத்தியிருந்தால் **Advance**);
- **Credit limit**;
- **Sales not fully paid** — ஒவ்வொரு receipt இலும் **On credit** தொகை மற்றும் இன்னும் கடன் (**Still owed**);
- **Statement** — ஒவ்வொரு credit sale, payment, return உம் running balance உடன்.

### Credit limit ஐ set செய்யுங்கள்

**Credit** இன் கீழ் **Credit limit** ஐ type செய்து save செய்யுங்கள். **Limit இல்லாமல்** வைக்க காலியாக விடுங்கள்: அப்போது till
இல் ஒவ்வொரு credit sale ஐயும் manager approve செய்வார். அடுத்த sync இல் tills புதிய limit ஐப் பெறும்.

**கடன் உள்ள** customer ஐ inactive ஆக்கவோ erase செய்யவோ முடியாது — முதலில் balance ஐத் தீர்த்துவையுங்கள்.

### Shifts மற்றும் reports

- Credit sale **பெற்ற பணம் அல்ல**. Shift இல் அது *on credit* எனக் காட்டப்படும்; expected cash இல் சேராது.
- பெற்ற payments அவற்றைப் **பெற்ற** shift இல் கணக்கிடப்படும் (*Credit payments received*), cash payments drawer இன் expected cash
  இல் சேரும். Till இன் X report மற்றும் close இலும் அவை காட்டப்படும்.
- **Payments by method** report payments ஐ அவை பெறப்பட்டபோது கணக்கிடும், credit ஐ அல்ல.
- **Credit outstanding** report ஒவ்வொரு customer உம் இன்னும் கடன்பட்டுள்ளதை sales இன் வயதுப்படி காட்டும்: **0–30**, **31–60**,
  **61–90**, **Over 90 days**. [Reports](/ta/reports/reports/) ஐப் பாருங்கள்.

## யார் என்ன செய்யலாம்

| Permission | Default ஆக யாருக்கு | அனுமதிப்பது |
|------------|---------------------|-------------|
| **Sell on credit within the customer's limit** | Owner, Administrator, Manager, Cashier | Till இல் Credit ஐத் தேர்ந்தெடுத்தல். |
| **Approve credit beyond the limit and set credit limits** | Owner, Administrator, Manager | Till இல் approve செய்தல்; back office இல் limits ஐ set செய்தல். |
| **Receive payments for credit sales** | Owner, Administrator, Manager, Cashier | Receive payment screen. |

[Roles](/ta/business/roles/) இல் role இலிருந்து permission ஐ நீக்கலாம் — உதா. payments ஐ managers மட்டும் பெறும்படி.
