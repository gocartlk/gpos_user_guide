---
title: Local hub
description: Branch இன் tills இணையும் shop இல் உள்ள ஒரு computer — internet இல்லாதபோதும் அவை சேர்ந்து வேலை செய்யும். தேவையானவை, install செய்தல், tills ஐ இணைத்தல், அன்றாட வேலை.
sidebar:
  order: 5.5
  badge:
    text: புதியது
    variant: tip
---

:::note[உங்கள் plan ஐப் பொறுத்தது]
**Local hub** ஒரு plan feature. அது இல்லாவிட்டால் **POS devices** இல் **Local hub** பகுதி இருக்காது.
[Plans and features](/ta/getting-started/plans/) ஐப் பாருங்கள். தேவைப்பட்டால் GPOS — அல்லது உங்கள் partner — இடம் கேளுங்கள்.
:::

**Local hub** என்பது ஒரு branch இன் tills shop இன் சொந்த network மூலம் இணையும் ஒரு computer. இந்த page owners க்கும், உங்களுக்காக
அதை setup செய்யும் partner அல்லது IT நபருக்கும்.

## Hub தருவது

- **Internet போய்விட்டதா? Tills ஒரே shop ஆக வேலை செய்யும்.** Hub மூலம் ஒவ்வொரு till உம் branch இன் stock மற்றும் customers இன்
  credit ஐ **எல்லா** tills இன் sales ஐயும் கணக்கிட்டுப் பார்க்கும், return க்கு வேறு till இன் receipt ஐக் கண்டுபிடிக்கும், வேறு till இல்
  சேர்த்த customers ஐக் கண்டுபிடிக்கும், வேறு till இல் hold செய்த sale ஐ முடிக்கலாம்.
- **சொந்த internet இல்லாத tills வேலை செய்யும்** — hub க்கு internet இருந்தால்.
- **புதிய அல்லது reinstall செய்த till சில வினாடிகளில் hub இலிருந்து data ஐ நிரப்பும்.**
- **ஒவ்வொரு sale உம் இரண்டு devices இல் இருக்கும்** — till இலும் hub இலும் — GPOS பெறும் வரை.

Hub **ஒருபோதும் ஒரே copy அல்ல**: அது பழுதானாலும் எதுவும் இழக்கப்படாது. Hub இல்லாமலும் ஒவ்வொரு till உம் தனியாக offline இல் வேலை
செய்யும் — [Offline மற்றும் sync](/ta/till/offline-sync/) ஐப் பாருங்கள்.

## தேவையானவை

- **Shop திறந்திருக்கும்போது on ஆக இருக்கும் computer**: **4 GB** memory மற்றும் **SSD** உள்ள எந்த PC அல்லது mini PC உம், 64-bit
  **Windows 10 அல்லது 11**, அல்லது **Linux** உடன். SSD உடன் Raspberry Pi 5 உம் வேலை செய்யும். பழைய Windows 7 அல்லது 8.1
  computers க்கு, பதிலாக சிறிய Linux mini PC ஐ hub ஆகப் பயன்படுத்துங்கள்.
- Shop இன் router உடன் **cable** மூலம் இணைக்கப்பட்டு, **UPS** இல் — மின்வெட்டு அதை நிறுத்தக் கூடாது.
- Shop network இல் **fixed address**: router இல் hub computer க்கு ஒரு address ஐ reserve செய்யுங்கள் (பொதுவாக *DHCP
  reservation* எனப்படும்). அதை எழுதி வையுங்கள், உதா. `192.168.1.10`.
- **Disk encryption** on: BitLocker (Windows Pro) அல்லது device encryption (Windows Home), Linux இல் LUKS. GPOS பெறும் வரை branch
  இன் sales hub இல் இருக்கும்.
- Tills shop இன் **சொந்த** network அல்லது Wi-Fi இல் — **guest Wi-Fi இல் அல்ல**.

## 1. Back office இல் hub ஐச் சேருங்கள்

1. **POS devices** க்குச் செல்லுங்கள். Branch இன் கீழ் **Local hub** இல் <span class="ui">Add a local hub</span> ஐத்
   தேர்ந்தெடுங்கள்.
2. **Name** கொடுங்கள், உதா. *Back office PC*.
3. **15 நிமிடங்கள்** valid ஆன one-time **code** தோன்றும். Page ஐத் திறந்தே வையுங்கள் — code ஐ hub computer இல் type செய்ய
   வேண்டும். (இன்னொன்று வேண்டுமா? <span class="ui">Show a new code</span>; முந்தைய codes வேலை செய்யாது.)

## 2. Hub ஐ install செய்யுங்கள்

எல்லாம் GPOS Hub download page இல்:
**[github.com/gocartlk/gpos-hub/releases/latest](https://github.com/gocartlk/gpos-hub/releases/latest)**
(account தேவையில்லை). எப்போதும் latest ஐ எடுங்கள்; install செய்த hubs பின்னர் தானாகவே update ஆகும்.

| Hub computer | Install செய்யும் வழி |
|--------------|-----------------------|
| Windows 10 அல்லது 11 (64-bit) | **GPOS Hub installer** (`gpos-hub-setup-<version>.exe`) — பரிந்துரைக்கப்படுகிறது |
| Linux (mini PC, server) | **Docker** (`compose.yml`) |
| Windows, ஏற்கனவே Docker / WSL பயன்படுத்தினால் | WSL இல் Docker (`setup-hub-docker.ps1`) |

### Windows (installer)

1. Hub computer இல் `gpos-hub-setup-<version>.exe` ஐ download செய்து run செய்து accept செய்யுங்கள். Windows *Windows protected
   your PC* எனச் சொன்னால் **More info → Run anyway** ஐத் தேர்ந்தெடுங்கள்.
2. கடைசியில் **Open the hub's setup page** ஐ tick செய்தபடியே விட்டு finish செய்யுங்கள். `http://localhost:8080` page திறக்கும்
   (Start menu இலும் உள்ளது: **GPOS Hub setup**).
3. Back office இன் **code** ஐ type செய்து hub இன் status page க்கு **PIN** (4 முதல் 8 இலக்கங்கள்) ஐத் தேர்ந்தெடுங்கள்.
   **Register** ஐத் தேர்ந்தெடுங்கள்.
4. சுமார் ஒரு நிமிடத்தில் page hub இன் address ஐ — உதா. `https://h2k3m4n5.hub.gpos.lk` — மற்றும் **Online** ஐக் காட்டும். POS
   devices உம் hub ஐ **Online** எனக் காட்டும்.

### Linux (Docker)

1. Docker ஐ install செய்து, hub files ஐப் பெறுங்கள் (root ஆக):

   ```sh
   mkdir -p /opt/gpos-hub && cd /opt/gpos-hub
   base=https://github.com/gocartlk/gpos-hub/releases/latest/download
   curl -fsSLO "$base/compose.yml" && curl -fsSLO "$base/gpos-hub-update.sh"
   curl -fsSL "$base/env.example" -o .env && curl -fsSL "$base/hub.env.example" -o hub.env
   chmod 755 gpos-hub-update.sh
   ```

   Hub இன் fixed address ஐ `hub.env` இல் போடுங்கள் (`HUB_LAN_IP=192.168.1.10`).

2. அதை start செய்து automatic updates ஐ on செய்யுங்கள்:

   ```sh
   docker compose up -d && ./gpos-hub-update.sh --install
   ```

3. Register செய்யுங்கள்: hub computer இல் `http://localhost:8080` ஐத் திறங்கள், அல்லது screen இல்லாவிட்டால்
   `docker compose exec hub gpos-hub register <CODE> <PIN>` ஐ run செய்யுங்கள்.

### Docker உடன் Windows (WSL)

Download page இலிருந்து `setup-hub-docker.ps1`, `compose.yml`, `gpos-hub-update.sh`, `hub.env.example` ஐ ஒரு folder இல் save
செய்து, `hub.env.example` ஐ `hub.env` என rename செய்யுங்கள். பிறகு அந்த folder இல் administrator PowerShell இல் (`<version>` download
page இல் உள்ளபடி):

```powershell
powershell -ExecutionPolicy Bypass -File setup-hub-docker.ps1 -Release <version> -Code <CODE> -Pin <PIN>
```

அது restart கேட்கலாம் (WSL ஐ install செய்ய); பிறகு மீண்டும் run செய்யுங்கள். Windows account இன் password ஐ ஒருமுறை கேட்கும், யாரும்
sign in செய்யாவிட்டாலும் computer start ஆகும்போது hub start ஆக.

## 3. Tills ஐ இணையுங்கள்

- **புதிய till:** till இல் hub இன் address ஐ இறுதியில் `/pos/` உடன் திறங்கள் — உதா. `https://h2k3m4n5.hub.gpos.lk/pos/` (POS
  devices இலும் hub இன் status page இலும் காட்டப்படும்) — வழக்கம்போல் till code மூலம் [setup செய்யுங்கள்](/ta/till/set-up-a-till/).
- **ஏற்கனவே பயன்பாட்டில் உள்ள till:** till இல் sync panel ஐ (கீழே உள்ள வரி) திறங்கள் → **Local hub** →
  <span class="ui">Move to the hub</span> → <span class="ui">Move now</span>. Till முதலில் காத்திருப்பவை அனைத்தையும் அனுப்பி, hub
  இன் address ஐத் திறந்து, அதே register க்குத் தானாகவே register ஆகும். இதை manager மட்டுமே செய்யலாம் — அல்லது lock screen இலிருந்து
  யாரும்.
- **சொந்த internet இல்லாத Windows till** hub இன் பெயரைக் கண்டுபிடிக்க முடியாது. Download page இலிருந்து `till-hosts.ps1` ஐ அதற்கு
  copy செய்து, administrator PowerShell இல் ஒருமுறை run செய்யுங்கள்:

  ```powershell
  powershell -ExecutionPolicy Bypass -File till-hosts.ps1 -Name <hub name> -Address <hub address>
  ```

## அன்றாடம்

Cashiers க்கு எதுவும் மாறாது. Till இன் கீழே உள்ள வரி அது எப்படி இணைந்துள்ளது எனச் சொல்லும்:

| Till சொல்வது | அர்த்தம் |
|--------------|-----------|
| *Online · via hub Back office PC · All synced* | எல்லாம் சரி. |
| *Hub Back office PC · cloud offline · 12 safe on the hub* | Shop இன் internet இல்லை. Sales till இலும் hub இலும் பாதுகாப்பாக உள்ளன; internet வந்ததும் செல்லும். |
| *Hub not reachable · selling offline · 12 waiting* | Till hub ஐ அடைய முடியவில்லை (hub off, cable, Wi-Fi). தொடர்ந்து விற்கும், பின்னர் அனுப்பும். |
| *Hub updating · back in a minute or two · selling continues* | Hub update ஐ install செய்கிறது. தொடர்ந்து விற்பனை செய்யுங்கள். |

**Internet இல்லாமல், hub மூலம்:**

- **Stock** — search results உம் [Stock screen](/ta/till/stock-at-till/) உம் ஒவ்வொரு till இன் sales மற்றும் returns ஐக் கணக்கிடும்:
  *No internet: stock as of 10:15, with every till's sales since.* Back office இல் receive அல்லது adjust செய்த stock internet
  திரும்பியதும் காட்டப்படும்.
- **Credit** — customer இன் balance branch இன் ஒவ்வொரு till ஐயும் கணக்கிடும், எனவே இரண்டு tills தனித்தனியாக customer ஐ limit ஐத்
  தாண்ட விட முடியாது. Payment ஐத் தேர்ந்தெடுத்த sales க்கு இடவும் முடியும். [Credit sales](/ta/till/credit-sales/) ஐப் பாருங்கள்.
- **Returns** — branch இன் வேறு till இன் receipt (கடைசி 7 நாட்களிலிருந்து) கண்டுபிடிக்கப்படும்.
- ஒரு till இல் சேர்த்த **customers** மற்றவற்றிலும் கண்டுபிடிக்கப்படுவார்கள்.
- **Held sales** — list வேறு tills இல் hold செய்த sales ஐயும் காட்டும் (*on Front*). இங்கே முடிக்க ஒன்றை resume செய்யுங்கள்; அதை
  ஒரு till மட்டுமே எடுக்க முடியும்.

**Updates** ஒவ்வொரு GPOS release க்கும் 30 நிமிடங்களுக்குள், ஓரிரு நிமிட சிறிய maintenance இல் தானாகவே install ஆகும். Update சரியாக
start ஆகாவிட்டால் hub முந்தைய version க்குத் திரும்பும்.

## Back office இல்

**POS devices** ஒவ்வொரு branch இன் hub ஐயும் காட்டும்: **Online** அல்லது **Not reachable**, அதன் **Address**, **இணைந்துள்ள
tills** எண்ணிக்கை, கடைசியாக **last seen**, **cloud க்குக் காத்திருப்பவை**, update ஆகும் release, **Certificate until …**. Till
இன் sync panel இல், hub அந்த till க்காக வைத்திருக்கும் sales **On the hub** எனக் காட்டப்படும்.

- **E-mail warning:** shop trading செய்யும்போது **2 மணி நேரம்** hub GPOS ஐ அடையாவிட்டால், அல்லது அனுப்ப முடியாத sales ஐ
  வைத்திருந்தால் owners க்கு e-mail வரும். Hub computer on ஆக உள்ளதா, internet உள்ளதா எனப் பாருங்கள். அதன் status page
  (`https://<hub address>/hub/`, உங்கள் PIN உடன்) மற்றும் POS devices அது எதற்காகக் காத்திருக்கிறது எனக் காட்டும். மீண்டும் வேலை
  செய்யும்போது இரண்டாவது e-mail வரும்.
- **Certificate:** hub இன் security certificate தானாகவே renew ஆகும். அதன் date amber நிறத்தில் காட்டப்பட்டால் GPOS support ஐத்
  தொடர்பு கொள்ளுங்கள்.

## Replace, remove, uninstall

- **Hub computer பழுதானது அல்லது மாற்றப்படுகிறது:** **Local hub** இல் <span class="ui">Replace</span> மற்றும்
  <span class="ui">Make a code</span> ஐத் தேர்ந்தெடுத்து, அந்த code மூலம் புதிய computer இல் install செய்யுங்கள். அது **அதே
  address** ஐ வைத்திருக்கும்: tills க்கு எதுவும் தேவையில்லை, காத்திருந்தவற்றை மீண்டும் அனுப்பும். பழைய computer உடனே வேலை செய்வதை
  நிறுத்தும்.
- **Hub ஐப் பயன்படுத்துவதை நிறுத்த:** அதில் **எதுவும் காத்திருக்காத** வரை பொறுங்கள். பிறகு ஒவ்வொரு till க்கும்: POS devices இல்
  <span class="ui">Decommission</span> செய்து, till இல் [app.gpos.lk/pos](https://app.gpos.lk/pos/) ஐத் திறந்து புதிய till code
  மூலம் register செய்யுங்கள். பிறகு hub இல் <span class="ui">Remove</span> ஐத் தேர்ந்தெடுங்கள்.
- **Uninstall:** Windows: **Settings → Apps → GPOS Hub → Uninstall** (hub இன் data ஐ delete செய்யும் முன் கேட்கும் — back office
  இலிருந்து hub ஐ remove செய்த பின்பே ஆம் எனச் சொல்லுங்கள்). Docker: `/opt/gpos-hub` இல் `docker compose down`.

**Local hub** உங்கள் plan இலிருந்து நீங்கினால், hub தன்னிடம் உள்ள அனைத்தையும் தொடர்ந்து அனுப்பும்; மேலே உள்ளபடி tills ஐத் திருப்பி
மாற்றி அதை remove செய்யுங்கள்.

## யார் செய்யலாம்

**Add, replace and remove a branch's local hub** — default ஆக Owner மற்றும் Administrator. Hub POS devices page இல் manage
செய்யப்படுவதால் **Register and revoke POS devices** உம் தேவை.
