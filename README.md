# PCmover 11.3.1015.1802 Download for Windows — PC Migration

PCmover moves applications, files and settings from an old Windows machine to a new one, including programs whose installer is no longer on disk. It reads the installed application list, the registry entries behind it and the profile data each program writes, then recreates that state on the target. The transfer runs over a home network, a direct Ethernet cable between the two machines or a Laplink USB cable, and the selection step lets you drop folders or whole user profiles. An undo log records every change on the old PC so the transfer can be reversed.

It does not move Windows itself: the target has to be a working installation. The tool carries the contents of a machine, not the operating system under them.

<p align="center">
  <a href="https://www.laplink.com/pcmover">
    <img src="https://img.shields.io/badge/DOWNLOAD-PCmover-1B5E9B?style=for-the-badge&logo=windows&logoColor=white" alt="Download PCmover">
  </a>
</p>

| | |
|---|---|
| **Version** | 11.3.1015.1802 |
| **Package** | installer from the product download page |
| **Architecture** | x64 / x86 |
| **Platform** | Windows 10, Windows 11 |
| **License** | Trial |

## Download

| Package | Link |
|---|---|
| **PCmover** | [Download](https://www.laplink.com/pcmover) |

The link opens the product download page, where the current build sits at the top. Nothing is repackaged or re-signed here.

## Works with

- Windows 11 and Windows 10
- Windows 8.1 and 7 with the older build
- Home network, direct cable and USB transfer modes
- Local and domain user profiles

## SHA-256

The installer is code-signed, and the download page states the current build. After saving the file, hash it before you run it:

```powershell
Get-FileHash -Algorithm SHA256 <path-to-installer>
```

## Install

1. Download the trial from the Laplink page and install it on both machines.
2. Pick the transfer route: home network, direct Ethernet cable or Laplink USB cable.
3. Choose what moves — applications, folders, user profiles or the whole account.
4. Run the transfer and keep the undo file on the old PC until the new machine is verified.

Both machines run the program at once; one acts as the source, one as the destination. Start the destination first, then the source: the two ends find each other on the network, and both have to stay running until the copy finishes.

## What it does

- Moves installed applications, not only documents and settings
- Transfer over home network, direct Ethernet cable or Laplink USB cable
- Selective transfer of folders, user profiles or whole drives
- Undo log that restores the old PC to its pre-transfer state
- Handles 32-bit to 64-bit upgrade paths between machines
- Keeps application registration and per-user preferences where they can be carried
- Reports what will move before anything is written to the new machine

## Compatibility

PCmover works between Windows versions as long as the destination is the same release or newer. Moving from an older build of Windows to a newer one is the common case and the one the selection step is designed around; moving backwards is not supported.

The architecture boundary is handled: a 32-bit application on a 32-bit Windows source can land on 64-bit Windows, provided the application itself runs there. A driver or shell extension compiled only for 32-bit is skipped, and the program that depended on it may need a reinstall.

Edition matters more than version. Express covers files and settings. Home and Professional add applications, and Professional adds domain profiles and several users in one pass. Business and Enterprise exist for volume work with licensing to match.

Two categories are excluded by design: security software and hardware drivers. An antivirus copied without its kernel driver is worse than one that is reinstalled, and a graphics or chipset driver belongs to the new machine. Plan to reinstall those, and to re-authorise anything bound to a hardware fingerprint.

## Troubleshooting

**The two machines will not connect.** Both have to be on the same network and see each other. Guest Wi-Fi that isolates clients, a firewall profile set to Public, or one machine on a VPN are the usual causes. A direct Ethernet cable between the two, with static addresses on the same subnet, removes the network from the equation.

**The transfer stalls near the end.** A large profile with many small files takes the longest, and either machine going to sleep breaks the session. Disable sleep on both and let it run — restarting loses progress rather than resuming it.

**A moved program starts but cannot find its data.** Some applications keep paths in the registry that point at a folder you excluded. Re-run the transfer with that folder included, or repair the application so it re-registers its paths.

**A program asks for its licence again.** Activation data tied to the old hardware does not travel. Keep the licence details at hand before starting; a few products also need a deactivation on the old machine first.

**The old PC is needed back in its previous state.** That is what the undo file is for, and it has to stay on the old machine. Deleting it after a successful transfer removes the only way back.

**A domain profile arrived as a local one.** Domain account migration needs the Professional edition or above and working credentials at transfer time. Without them the profile moves as a local account with the same name.

## Alternatives

EaseUS Todo PCTrans covers the same ground with a simpler interface and a free tier limited by volume. Zinstall WinWin transfers applications and profiles and is often compared on the same jobs. For a few programs, a clean install plus a file copy is slower but produces a machine with no inherited oddities — and it is the only route when the old system is already unstable. Enterprises usually reach for user environment virtualisation, where profiles and settings are containerised rather than copied.

PCmover earns its price when the old machine has applications that cannot be reinstalled — no media, no licence key, no download portal — and the user needs them working on the new box the same day.

## FAQ

**Is PCmover free?** — Trial. The build linked above installs as an evaluation copy that reports what can be moved; a licence is needed to complete a transfer.

**Does it run on Windows 11?** — Yes, as destination or source. Windows 7 and 8.1 need the older build listed under Works with.

**Can it be installed silently?** — No documented silent switch, and both ends need an interactive selection before the copy starts.

**Does it move the operating system?** — No. It moves applications, files and settings onto an existing Windows installation.

**Can it move programs without their installers?** — Yes, that is the point of the product. Most applications arrive working; hardware-bound and security software are the exceptions.

**Can the transfer be undone?** — Yes, with the undo file written on the old PC. Keep it until the new machine has been checked.

## Disclaimer

This page collects the installer link, version data and SHA-256 checksum for offline installation and archival. Product names and trademarks belong to their respective owners. No affiliation or endorsement is implied.
