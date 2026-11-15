---
title: Local hub
description: One computer in the shop that the branch's tills connect to — they keep working together when the internet is down. What you need, installing it, connecting the tills, and day to day.
sidebar:
  order: 5.5
  badge:
    text: New
    variant: tip
---

:::note[Depends on your plan]
**Local hub** is a plan feature. Without it, **POS devices** has no **Local hub** section. See
[Plans and features](/getting-started/plans/). Ask GPOS — or your partner — if you need it.
:::

A **local hub** is one computer in a branch that the branch's tills connect to over the shop's
own network. This page is for owners, and for the partner or IT person who sets it up for you.

## What a hub gives you

- **The internet goes down? The tills work as one shop.** Through the hub every till sees the
  branch's stock and customers' credit counting **all** tills' sales, finds another till's
  receipt for a return, finds customers added on another till, and can finish a sale held on
  another till.
- **Tills without internet of their own work**, as long as the hub has internet.
- **A new or reinstalled till fills up from the hub in seconds.**
- **Every sale is kept on two devices** — the till and the hub — until GPOS has it.

The hub is **never the only copy**: if it breaks, nothing is lost. Without a hub, every till
still works offline on its own — see [Offline and sync](/till/offline-sync/).

## What you need

- **A computer that stays on** while the shop is open: any PC or mini PC with **4 GB** memory and
  an **SSD**, with 64-bit **Windows 10 or 11**, or **Linux**. A Raspberry Pi 5 with an SSD also
  works. For old Windows 7 or 8.1 computers, use a small Linux mini PC as the hub instead.
- **Wired** to the shop's router, and on a **UPS** — a power cut should not stop it.
- A **fixed address** on the shop network: on the router, reserve an address for the hub
  computer (often called *DHCP reservation*). Write it down, for example `192.168.1.10`.
- **Disk encryption** on: BitLocker (Windows Pro) or device encryption (Windows Home), LUKS on
  Linux. The hub holds the branch's sales until GPOS has them.
- The tills on the shop's **own** network or Wi-Fi — **not the guest Wi-Fi**.

## 1. Add the hub in the back office

1. Go to **POS devices**. Under the branch, in **Local hub**, select
   <span class="ui">Add a local hub</span>.
2. Give it a **Name**, for example *Back office PC*.
3. A one-time **code** appears, valid for **15 minutes**. Keep the page open — you type the code
   on the hub computer. (Need another? <span class="ui">Show a new code</span>; earlier codes stop
   working.)

## 2. Install the hub

Everything is on the GPOS Hub download page:
**[github.com/gocartlk/gpos-hub/releases/latest](https://github.com/gocartlk/gpos-hub/releases/latest)**
(no account needed). Always take the latest; installed hubs then update themselves.

| The hub computer is | Install |
|---------------------|---------|
| Windows 10 or 11 (64-bit) | **The GPOS Hub installer** (`gpos-hub-setup-<version>.exe`) — recommended |
| Linux (mini PC, server) | **Docker** (`compose.yml`) |
| Windows, already using Docker / WSL | Docker in WSL (`setup-hub-docker.ps1`) |

### Windows (installer)

1. On the hub computer, download `gpos-hub-setup-<version>.exe`, run it and accept. If Windows
   says *Windows protected your PC*, choose **More info → Run anyway**.
2. At the end, leave **Open the hub's setup page** ticked and finish. The page
   `http://localhost:8080` opens (also in the Start menu: **GPOS Hub setup**).
3. Type the **code** from the back office and choose a **PIN** (4 to 8 digits) for the hub's status
   page. Select **Register**.
4. In about a minute the page shows the hub's address — for example
   `https://h2k3m4n5.hub.gpos.lk` — and **Online**. POS devices shows the hub **Online** too.

### Linux (Docker)

1. Install Docker, then get the hub files (as root):

   ```sh
   mkdir -p /opt/gpos-hub && cd /opt/gpos-hub
   base=https://github.com/gocartlk/gpos-hub/releases/latest/download
   curl -fsSLO "$base/compose.yml" && curl -fsSLO "$base/gpos-hub-update.sh"
   curl -fsSL "$base/env.example" -o .env && curl -fsSL "$base/hub.env.example" -o hub.env
   chmod 755 gpos-hub-update.sh
   ```

   Put the hub's fixed address in `hub.env` (`HUB_LAN_IP=192.168.1.10`).

2. Start it and turn on automatic updates:

   ```sh
   docker compose up -d && ./gpos-hub-update.sh --install
   ```

3. Register: open `http://localhost:8080` on the hub computer, or without a screen run
   `docker compose exec hub gpos-hub register <CODE> <PIN>`.

### Windows with Docker (WSL)

Save `setup-hub-docker.ps1`, `compose.yml`, `gpos-hub-update.sh` and `hub.env.example` from the
download page in one folder, and rename `hub.env.example` to `hub.env`. Then, in an administrator
PowerShell in that folder (`<version>` as on the download page):

```powershell
powershell -ExecutionPolicy Bypass -File setup-hub-docker.ps1 -Release <version> -Code <CODE> -Pin <PIN>
```

It may ask for a restart (to install WSL); run it again afterwards. It asks once for the Windows
account's password, so the hub starts when the computer starts, even when nobody signs in.

## 3. Connect the tills

- **A new till:** on the till, open the hub's address with `/pos/` at the end — for example
  `https://h2k3m4n5.hub.gpos.lk/pos/` (shown in POS devices and on the hub's status page) — and
  [set it up](/till/set-up-a-till/) with a till code, as usual.
- **A till already in use:** on the till, open the sync panel (the line at the bottom) → **Local
  hub** → <span class="ui">Move to the hub</span> → <span class="ui">Move now</span>. The till sends
  everything waiting first, then opens the hub's address and registers there by itself, for the
  same register. Only a manager can do this — or anyone from the lock screen.
- **A Windows till with no internet of its own** cannot look up the hub's name. Copy
  `till-hosts.ps1` from the download page to it and, in an administrator PowerShell, run once:

  ```powershell
  powershell -ExecutionPolicy Bypass -File till-hosts.ps1 -Name <hub name> -Address <hub address>
  ```

## Day to day

Nothing changes for cashiers. The line at the bottom of the till says how it is connected:

| The till says | Meaning |
|---------------|---------|
| *Online · via hub Back office PC · All synced* | All good. |
| *Hub Back office PC · cloud offline · 12 safe on the hub* | The shop's internet is down. Sales are safe on the till and the hub; they go when it is back. |
| *Hub not reachable · selling offline · 12 waiting* | The till cannot reach the hub (hub off, cable, Wi-Fi). It keeps selling and sends later. |
| *Hub updating · back in a minute or two · selling continues* | The hub is installing an update. Keep selling. |

**Without internet, through the hub:**

- **Stock** — the search results and the [Stock screen](/till/stock-at-till/) count every till's
  sales and returns: *No internet: stock as of 10:15, with every till's sales since.* Stock
  received or adjusted in the back office shows once the internet is back.
- **Credit** — the customer's balance counts every till of the branch, so two tills cannot each
  let a customer go over the limit. A payment can still be set against chosen sales. See
  [Credit sales](/till/credit-sales/).
- **Returns** — a receipt from another till of the branch (from the last 7 days) is found.
- **Customers** added on one till are found on the others.
- **Held sales** — the list also shows sales held on other tills (*on Front*). Resume one to
  finish it here; only one till can take it.

**Updates** install themselves within 30 minutes of each GPOS release, during a short maintenance
of a minute or two. If an update does not start properly, the hub goes back to the version
before.

## In the back office

**POS devices** shows each branch's hub: **Online** or **Not reachable**, its **Address**, how many
**tills are connected**, when it was **last seen**, what is **waiting for the cloud**, the release
it is updating to, and **Certificate until …**. On a till's sync panel, sales the hub holds for it
show as **On the hub**.

- **E-mail warning:** the owners get an e-mail if the hub has not reached GPOS for **2 hours** while
  the shop was trading, or holds sales it cannot send. Check that the hub computer is on and has
  internet. Its status page (`https://<hub address>/hub/`, with your PIN) and POS devices show what
  it is waiting for. A second e-mail says when it works again.
- **Certificate:** the hub's security certificate renews itself. If its date shows in amber,
  contact GPOS support.

## Replace, remove, uninstall

- **The hub computer broke or is being changed:** in **Local hub**, select
  <span class="ui">Replace</span> and <span class="ui">Make a code</span>, then install on the new
  computer with that code. It keeps the **same address**: the tills need nothing and send again
  whatever was waiting. The old computer stops working at once.
- **Stop using the hub:** wait until it shows **nothing waiting**. Then for each till:
  <span class="ui">Decommission</span> it in POS devices, open
  [app.gpos.lk/pos](https://app.gpos.lk/pos/) on the till and register it with a new till code.
  Then select <span class="ui">Remove</span> on the hub.
- **Uninstall:** Windows: **Settings → Apps → GPOS Hub → Uninstall** (it asks before deleting the
  hub's data — say yes only after removing the hub in the back office). Docker:
  `docker compose down` in `/opt/gpos-hub`.

If **Local hub** leaves your plan, the hub keeps sending everything it holds; move the tills back
and remove it as above.

## Who can do this

**Add, replace and remove a branch's local hub** — Owner and Administrator by default. It needs
**Register and revoke POS devices** too, since the hub is managed on the POS devices page.
