# QuickVerse Shop Setup — v1.3.1

One link, one zip, 2 minutes per shop. No cost. Nothing to install except the printer driver.

Dashboard lives at: **https://vendor-dashboard-quickverse.vercel.app/**

## What to do on a new billing PC (Windows)

**0. One-time prerequisite:** Epson driver only
(`EPSON Advanced Printer Driver 6 for TM-T82X`), 80mm roll loaded.
No Node, no npm, no exe — the agent is pure PowerShell, every Windows runs it.

**1. Download this repo as zip:** switch branch to **v1.3.1** (latest agent),
click **Code → Download ZIP** on this page
(or open `https://github.com/Lolxd-1/QuickVerse-Dashboard/archive/refs/heads/v1.3.1.zip`),
unzip anywhere.

**2. Run one command** (right-click PowerShell → Run as administrator if you can,
else normal PowerShell works too):

```powershell
cd "<unzipped>\QuickVerse-Dashboard-v1.3.1"
.\Start-Setup.bat
```

That installs the print agent to `C:\QuickVerse\print-agent`, auto-starts it at
every login, creates the `QuickVerse Vendor` desktop shortcut, and prints a
42-col self-test slip.

**3. Open `QuickVerse Vendor` → login with shop mobile OTP → Printer → pick
`EPSON TM-T82X Receipt` in both dropdowns → tick Single printer → Save →
Test Counter Print.** Gate: the `123...42` line prints as ONE line.

## What's inside

- `print-agent/` — silent 80mm print agent v1.3.1-exp3 (GDI Courier New, shares queue with PetPooja)
- `files/Install-QuickVerse.ps1` — the 2-min installer (calls `Install-VendorDashboard.ps1` for shortcut/policy/power)
- `files/QUICKVERSE-ROLLOUT.md` — pilot 5→20→200 gates + diagnostics

Paper over / USB loose: fix it → Reprint on the Accepted card. No reinstall needed.
Two printers later: untick Single printer, set Kitchen to 2nd queue, Save.
