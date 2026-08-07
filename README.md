# Rivet PCB — downloads

This repository exists to host the download. Nothing else is here.

**[→ Get the latest release](https://github.com/ac0rdj/rivet-pcb/releases/latest)**

Rivet PCB is a macOS schematic and PCB editor with an agent in the sidebar that
reads your design, places and wires parts, and checks its own work.

## Which file do I want?

| Your Mac | File |
| --- | --- |
| Apple Silicon — M1, M2, M3, M4 | `RivetPCB-1.0.0-macOS-arm64.dmg` |
| Intel | `RivetPCB-1.0.0-macOS-x64.dmg` |

Apple menu → **About This Mac** tells you which one you have. If the *Chip* line
says "Apple M-something", take the arm64 file.

Honest note on the Intel build: it is a real x64 build and it passes the same
ten launch checks the Apple Silicon build does — but every one of those runs was
under **Rosetta 2 on an Apple Silicon Mac**. It has never been run on genuine
Intel hardware. It should work; it has not been proven on the metal.

macOS 11 or newer. About 166 MB to download, about 1 GB installed.

## Verifying what you downloaded

`SHA256SUMS.txt` is attached to each release. Check your copy against it:

```sh
shasum -a 256 ~/Downloads/RivetPCB-1.0.0-macOS-arm64.dmg
```

For 1.0.0 the sums are:

```
cd05b0e394aa2aecc7e0bf19dfff95929556f212f967485cb89e2857317cbedb  RivetPCB-1.0.0-macOS-arm64.dmg
a787fa4e0d5785407652209cf64942e9d9c728de72c9f8ce71a5fefe850ebda4  RivetPCB-1.0.0-macOS-x64.dmg
```

## macOS says "Apple could not verify Rivet PCB is free of malware"

Open **System Settings → Privacy & Security**, scroll to the bottom, and click
**Open Anyway**. You do this once.

The app *is* signed, with a Developer ID certificate issued to MINIMALI LLC, and
runs under a hardened runtime — macOS can read that and will name us. What it
does not yet have is Apple's notarisation ticket, a separate scan Apple runs on
the uploaded build. Until that ticket is stapled on, Gatekeeper shows the warning
even though the signature checks out. When notarisation lands, this note changes.

Do not remove the quarantine flag by other means, and be suspicious of anyone who
tells you to run `xattr -d` on software you downloaded.
