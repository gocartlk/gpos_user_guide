---
title: Local hub
description: Branch එකේ tills connect වෙන shop එකේ එක computer එකක් — internet නැති වුණත් ඒවා එකට වැඩ කරනවා. ඕන දේවල්, install කිරීම, tills connect කිරීම, සහ දිනපතා වැඩ.
sidebar:
  order: 5.5
  badge:
    text: අලුත්
    variant: tip
---

:::note[ඔබේ plan එක අනුව වෙනස් වේ]
**Local hub** කියන්නේ plan feature එකක්. ඒක නැත්නම් **POS devices** හි **Local hub** කොටසක් නැහැ.
[Plans and features](/si/getting-started/plans/) බලන්න. ඕන නම් GPOS — නැත්නම් ඔබේ partner — ගෙන් අහන්න.
:::

**Local hub** එකක් කියන්නේ branch එකක tills shop එකේම network එක හරහා connect වෙන එක computer එකක්. මේ page එක owners ලාට, සහ
ඔබ වෙනුවෙන් ඒක setup කරන partner හෝ IT කෙනාට.

## Hub එකකින් ලැබෙන දේ

- **Internet නැති වුණාද? Tills එක shop එකක් වගේ වැඩ කරනවා.** Hub එක හරහා හැම till එකක්ම branch එකේ stock සහ customers ලාගේ credit
  **හැම** till එකකම sales ගණන් කරලා දකිනවා, return එකකට වෙනත් till එකක receipt එකක් හොයාගන්නවා, වෙනත් till එකක add කරපු customers
  හොයාගන්නවා, වෙනත් till එකක hold කරපු sale එකක් ඉවර කරන්න පුළුවන්.
- **තමන්ගේම internet නැති tills වැඩ කරනවා** — hub එකට internet තියෙනවා නම්.
- **අලුත් හෝ reinstall කරපු till එකක් තත්පර කිහිපයකින් hub එකෙන් data පුරවගන්නවා.**
- **හැම sale එකක්ම devices දෙකක තියෙනවා** — till එකේ සහ hub එකේ — GPOS වලට ලැබෙනකම්.

Hub එක **කවදාවත් එකම copy එක නෙවෙයි**: ඒක කැඩුණත් මුකුත් නැති වෙන්නේ නැහැ. Hub එකක් නැතුවත් හැම till එකක්ම තනියම offline වැඩ
කරනවා — [Offline සහ sync](/si/till/offline-sync/) බලන්න.

## ඕන දේවල්

- **Shop එක open ඇති වෙලාවේ on වෙලා තියෙන computer එකක්**: **4 GB** memory සහ **SSD** එකක් තියෙන ඕනෑම PC හෝ mini PC එකක්,
  64-bit **Windows 10 හෝ 11**, නැත්නම් **Linux**. SSD එකක් එක්ක Raspberry Pi 5 එකකුත් වැඩ කරනවා. පරණ Windows 7 හෝ 8.1 computers
  නම්, ඒ වෙනුවට පොඩි Linux mini PC එකක් hub එක විදිහට පාවිච්චි කරන්න.
- Shop එකේ router එකට **cable** එකකින් connect කරලා, **UPS** එකක — current යනකොට ඒක නවතින්න හොඳ නැහැ.
- Shop network එකේ **fixed address** එකක්: router එකේ hub computer එකට address එකක් reserve කරන්න (සාමාන්‍යයෙන් *DHCP
  reservation* කියනවා). ඒක ලියාගන්න, උදා. `192.168.1.10`.
- **Disk encryption** on කරලා: BitLocker (Windows Pro) හෝ device encryption (Windows Home), Linux නම් LUKS. GPOS වලට ලැබෙනකම්
  branch එකේ sales hub එකේ තියෙනවා.
- Tills shop එකේ **තමන්ගේම** network එකේ හෝ Wi-Fi එකේ — **guest Wi-Fi එකේ නෙවෙයි**.

## 1. Back office එකේ hub එක add කරන්න

1. **POS devices** වලට යන්න. Branch එක යටතේ **Local hub** හි <span class="ui">Add a local hub</span> තෝරන්න.
2. **Name** එකක් දෙන්න, උදා. *Back office PC*.
3. **විනාඩි 15ක්** valid one-time **code** එකක් පෙන්නනවා. Page එක open කරලා තියන්න — code එක hub computer එකේ type කරන්න ඕන.
   (තව එකක් ඕනද? <span class="ui">Show a new code</span>; පරණ codes වැඩ කරන්නේ නැහැ.)

## 2. Hub එක install කරන්න

හැම දෙයක්ම GPOS Hub download page එකේ:
**[github.com/gocartlk/gpos-hub/releases/latest](https://github.com/gocartlk/gpos-hub/releases/latest)**
(account එකක් ඕන නැහැ). හැමවිටම latest එක ගන්න; install කරපු hubs ඊට පස්සේ තනියම update වෙනවා.

| Hub computer එක | Install කරන විදිහ |
|-----------------|-------------------|
| Windows 10 හෝ 11 (64-bit) | **GPOS Hub installer** (`gpos-hub-setup-<version>.exe`) — recommend කරනවා |
| Linux (mini PC, server) | **Docker** (`compose.yml`) |
| Windows, දැනටමත් Docker / WSL පාවිච්චි කරනවා නම් | WSL එකේ Docker (`setup-hub-docker.ps1`) |

### Windows (installer)

1. Hub computer එකේ `gpos-hub-setup-<version>.exe` download කරලා run කරන්න, accept කරන්න. Windows *Windows protected your PC*
   කිව්වොත් **More info → Run anyway** තෝරන්න.
2. අන්තිමට **Open the hub's setup page** tick කරලාම තියලා finish කරන්න. `http://localhost:8080` page එක open වෙනවා (Start menu
   එකෙත් තියෙනවා: **GPOS Hub setup**).
3. Back office එකේ **code** එක type කරලා hub එකේ status page එකට **PIN** එකක් (ඉලක්කම් 4 සිට 8) තෝරන්න. **Register** තෝරන්න.
4. විනාඩියක් විතර ඇතුළත page එකේ hub එකේ address එක — උදා. `https://h2k3m4n5.hub.gpos.lk` — සහ **Online** පෙන්නනවා. POS devices
   වලත් hub එක **Online** පෙන්නනවා.

### Linux (Docker)

1. Docker install කරලා, hub files ගන්න (root විදිහට):

   ```sh
   mkdir -p /opt/gpos-hub && cd /opt/gpos-hub
   base=https://github.com/gocartlk/gpos-hub/releases/latest/download
   curl -fsSLO "$base/compose.yml" && curl -fsSLO "$base/gpos-hub-update.sh"
   curl -fsSL "$base/env.example" -o .env && curl -fsSL "$base/hub.env.example" -o hub.env
   chmod 755 gpos-hub-update.sh
   ```

   Hub එකේ fixed address එක `hub.env` එකට දාන්න (`HUB_LAN_IP=192.168.1.10`).

2. ඒක start කරලා automatic updates on කරන්න:

   ```sh
   docker compose up -d && ./gpos-hub-update.sh --install
   ```

3. Register කරන්න: hub computer එකේ `http://localhost:8080` open කරන්න, නැත්නම් screen එකක් නැත්නම්
   `docker compose exec hub gpos-hub register <CODE> <PIN>` run කරන්න.

### Docker එක්ක Windows (WSL)

Download page එකෙන් `setup-hub-docker.ps1`, `compose.yml`, `gpos-hub-update.sh` සහ `hub.env.example` එක folder එකකට save කරලා,
`hub.env.example` එක `hub.env` ලෙස rename කරන්න. ඊට පස්සේ ඒ folder එකේ administrator PowerShell එකක (`<version>` download page
එකේ තියෙන විදිහට):

```powershell
powershell -ExecutionPolicy Bypass -File setup-hub-docker.ps1 -Release <version> -Code <CODE> -Pin <PIN>
```

ඒක restart එකක් ඉල්ලන්න පුළුවන් (WSL install කරන්න); ඊට පස්සේ ආයෙත් run කරන්න. Windows account එකේ password එක එක පාරක් අහනවා,
කවුරුත් sign in නොවුණත් computer එක start වෙනකොට hub එක start වෙන්න.

## 3. Tills connect කරන්න

- **අලුත් till එකක්:** till එකේ hub එකේ address එක අගට `/pos/` එක්ක open කරන්න — උදා. `https://h2k3m4n5.hub.gpos.lk/pos/`
  (POS devices වල සහ hub එකේ status page එකේ පෙන්නනවා) — සාමාන්‍ය විදිහටම till code එකකින් [setup කරන්න](/si/till/set-up-a-till/).
- **දැනටමත් පාවිච්චි කරන till එකක්:** till එකේ sync panel එක (පහළ තියෙන line එක) open කරන්න → **Local hub** →
  <span class="ui">Move to the hub</span> → <span class="ui">Move now</span>. Till එක මුලින් waiting ඔක්කොම යවලා, hub එකේ address
  එක open කරලා, එකම register එකට තනියම register වෙනවා. මේක කරන්න පුළුවන් manager කෙනෙකුට විතරයි — නැත්නම් lock screen එකේ ඉඳන්
  ඕනෑම කෙනෙකුට.
- **තමන්ගේම internet නැති Windows till එකකට** hub එකේ නම හොයාගන්න බැහැ. Download page එකේ `till-hosts.ps1` එක ඒකට copy කරලා,
  administrator PowerShell එකක එක පාරක් run කරන්න:

  ```powershell
  powershell -ExecutionPolicy Bypass -File till-hosts.ps1 -Name <hub name> -Address <hub address>
  ```

## දිනපතා

Cashiers ලාට මුකුත් වෙනස් වෙන්නේ නැහැ. Till එකේ පහළ line එක ඒක connect වෙලා තියෙන විදිහ කියනවා:

| Till එක කියන දේ | තේරුම |
|-----------------|-------|
| *Online · via hub Back office PC · All synced* | හැමදේම හරි. |
| *Hub Back office PC · cloud offline · 12 safe on the hub* | Shop එකේ internet නැහැ. Sales till එකේ සහ hub එකේ ආරක්ෂිතයි; internet ආවම යනවා. |
| *Hub not reachable · selling offline · 12 waiting* | Till එකට hub එකට යන්න බැහැ (hub එක off, cable, Wi-Fi). දිගටම විකුණනවා, පස්සේ යවනවා. |
| *Hub updating · back in a minute or two · selling continues* | Hub එක update එකක් install කරනවා. දිගටම විකුණන්න. |

**Internet නැතුව, hub එක හරහා:**

- **Stock** — search results සහ [Stock screen](/si/till/stock-at-till/) එක හැම till එකකම sales සහ returns ගණන් කරනවා: *No internet:
  stock as of 10:15, with every till's sales since.* Back office එකේ receive හෝ adjust කරපු stock පෙන්නන්නේ internet ආපහු ආවාමයි.
- **Credit** — customer ගේ balance එක branch එකේ හැම till එකක්ම ගණන් කරනවා, ඒ නිසා tills දෙකකට වෙන වෙනම customer කෙනෙකුට limit එක
  ඉක්මවන්න දෙන්න බැහැ. Payment එකක් තෝරපු sales වලට දාන්නත් පුළුවන්. [Credit sales](/si/till/credit-sales/) බලන්න.
- **Returns** — branch එකේ වෙනත් till එකක receipt එකක් (අන්තිම දින 7 ඇතුළත) හොයාගන්නවා.
- එක till එකක add කරපු **customers** අනිත් ඒවායෙත් හොයාගන්නවා.
- **Held sales** — list එකේ වෙනත් tills වල hold කරපු sales පෙන්නනවා (*on Front*). මෙතන ඉවර කරන්න එකක් resume කරන්න; ඒක ගන්න
  පුළුවන් එක till එකකට විතරයි.

**Updates** හැම GPOS release එකකටම විනාඩි 30ක් ඇතුළත, විනාඩියක් දෙකක පොඩි maintenance එකකදී තනියම install වෙනවා. Update එකක් හරියට
start වුණේ නැත්නම් hub එක කලින් version එකට ආපහු යනවා.

## Back office එකේ

**POS devices** හැම branch එකකම hub එක පෙන්නනවා: **Online** හෝ **Not reachable**, ඒකේ **Address**, **connect වෙලා ඉන්න tills**
ගණන, අන්තිමට **last seen**, **cloud එකට waiting** ගණන, update වෙන release එක, සහ **Certificate until …**. Till එකක sync panel එකේ,
hub එක ඒ till එක වෙනුවෙන් තියාගෙන ඉන්න sales **On the hub** ලෙස පෙන්නනවා.

- **E-mail warning:** shop එක trading කරද්දී පැය **2**ක් hub එක GPOS වලට ගියේ නැත්නම්, නැත්නම් යවන්න බැරි sales තියෙනවා නම්
  owners ලාට e-mail එකක් එනවා. Hub computer එක on ද, internet තියෙනවද බලන්න. ඒකේ status page එක (`https://<hub address>/hub/`,
  ඔබේ PIN එක එක්ක) සහ POS devices ඒක බලාගෙන ඉන්නේ මොනවටද කියලා පෙන්නනවා. ආයෙත් වැඩ කරනකොට දෙවෙනි e-mail එකක් එනවා.
- **Certificate:** hub එකේ security certificate එක තනියම renew වෙනවා. ඒකේ date එක amber පාටින් පෙන්නුවොත් GPOS support අමතන්න.

## Replace, remove, uninstall

- **Hub computer එක කැඩුණා හෝ මාරු කරනවා:** **Local hub** හි <span class="ui">Replace</span> සහ <span class="ui">Make a code</span>
  තෝරලා, ඒ code එකෙන් අලුත් computer එකේ install කරන්න. ඒකට **එකම address එක** තියෙනවා: tills වලට මුකුත් කරන්න ඕන නැහැ, waiting
  තිබ්බ දේවල් ආයෙත් යවනවා. පරණ computer එක එවෙලේම වැඩ නවත්වනවා.
- **Hub එක පාවිච්චි කරන එක නවත්වන්න:** ඒකේ **මුකුත් waiting නැති** වෙනකම් ඉන්න. ඊට පස්සේ හැම till එකකටම: POS devices හි
  <span class="ui">Decommission</span> කරලා, till එකේ [app.gpos.lk/pos](https://app.gpos.lk/pos/) open කරලා අලුත් till code
  එකකින් register කරන්න. ඊට පස්සේ hub එකේ <span class="ui">Remove</span> තෝරන්න.
- **Uninstall:** Windows: **Settings → Apps → GPOS Hub → Uninstall** (hub එකේ data delete කරන්න කලින් අහනවා — ඔව් කියන්න back
  office එකෙන් hub එක remove කළාට පස්සේ විතරයි). Docker: `/opt/gpos-hub` හි `docker compose down`.

**Local hub** ඔබේ plan එකෙන් අයින් වුණොත්, hub එක තියෙන ඔක්කොම දිගටම යවනවා; ඉහත විදිහට tills ආපහු මාරු කරලා ඒක remove කරන්න.

## කාටද කරන්න පුළුවන්

**Add, replace and remove a branch's local hub** — default විදිහට Owner සහ Administrator. Hub එක manage කරන්නේ POS devices page
එකේ නිසා **Register and revoke POS devices** එකත් ඕන.
