# QuickVerse Shop Setup — v1.1.0

One link, one zip, 2 minutes per shop. No cost.

Dashboard lives at: **https://vendor-dashboard-quickverse.vercel.app/**

## What to do on a new billing PC (Windows)

**0. One-time prerequisites:** install Node LTS (`nodejs.org`) + Epson driver
(`EPSON Advanced Printer Driver 6 for TM-T82X`), 80mm roll loaded.

**1. Download this repo as zip:** click **Code → Download ZIP** on this page
(or open `https://github.com/Lolxd-1/QuickVerse-Dashboard/archive/refs/heads/main.zip`),
unzip anywhere.

**2. Run one command** (right-click PowerShell → Run as administrator if you can,
else normal PowerShell works too):

```powershell
cd "<unzipped>\QuickVerse-Dashboard-main"
.\Start-Setup.bat
```

That installs the print agent to `C:\QuickVerse\print-agent`, auto-starts it at
every login, creates the `QuickVerse Vendor` desktop shortcut, and prints a
42-col self-test slip.

**3. Open `QuickVerse Vendor` → login with shop mobile OTP → Printer → pick
`EPSON TM-T82X Receipt` in both dropdowns → tick Single printer → Save →
Test Counter Print.** Gate: the `123...42` line prints as ONE line.

## What's inside

- `print-agent/` — silent 80mm print agent v1.1.0 (GDI Courier New, shares queue with PetPooja)
- `files/Install-QuickVerse.ps1` — the 2-min installer (calls `Install-VendorDashboard.ps1` for shortcut/policy/power)
- `files/QUICKVERSE-ROLLOUT.md` — pilot 5→20→200 gates + diagnostics

Paper over / USB loose: fix it → Reprint on the Accepted card. No reinstall needed.
Two printers later: untick Single printer, set Kitchen to 2nd queue, Save.
