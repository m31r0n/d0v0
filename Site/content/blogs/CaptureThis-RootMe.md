---
title: "Forensic Writeup: Capture This – Root Me"
date: 2025-04-17T18:36:00+05:30
draft: false
github_link: "https://github.com/m31r0n"
author: "D0V0"
tags:
  - Forensic
  - RootMe
  - PNG
  - KeePass
  - aCropalypse
  - CTF
image: /images/CaptureThis-Post-RootMe.jpg
description: "Step-by-step forensic analysis of Root Me's Capture This CTF challenge exploiting the aCropalypse vulnerability to recover a KeePass master password."
toc:
---

## Writeup: "Capture This" - Root Me

## Introduction and Context

A user lost their **KeePass** database password and cannot find the `.kdbx` file. After hours of searching, they discovered that they had sent a **screenshot** of their password manager to a colleague, but the image was **cropped**, hiding part of the password.

In the RootMe challenge **"Capture This"** (15 points), you are given:

1. A ZIP archive (`ch42.zip`) containing:
    
    - **Database.kdbx**: the KeePass database.
        
    - **Capture.png**: the cropped screenshot of the password manager.
        
2. The SHA256 checksum of the ZIP: `028c8561f087da873b08968d55141dcfc8f10a47e787f79c35b2da611a5e07ce`.
    

Its goal is to **recover the missing part** of the screenshot, reconstruct the full password, and open `Database.kdbx` to recover the flag, but to understand how we got to that goal we need to understand the reasoning above.

![Details-Chall](/images/Blog/Capture-This-Rootme.png)

## Reasoning

A quick glance at the Excel shot shows terrible password hygiene—and a tempting row labeled “Flag”—but the real clue appears in the far‑right column of the Google entry, where the cell is cut off showing only “Ke”.  
Moreover, the Windows taskbar reveals only two open apps: Microsoft Excel and the Snipping Tool.

![Image-Chall](/Site/static/images/Blog/File1-CaptureThis-Chall.png)

The cropped file’s metadata dates back to early 2023, pointing us toward the **aCropalypse** vulnerability (CVE‑2023‑28303). This flaw, affecting tools like Windows Snipping Tool and certain mobile editors, leaves the original image data intact after cropping. Though hidden from normal viewers, these residual bytes can reveal the full picture.

![Time](/Site/static/images/Blog/Fecha-CaptureThis-RootMe.png)

This gives us a clue to associate it with the **aCropalypse** vulnerability, identified as _CVE-2023-28303_, which was discovered in early 2023. This flaw affects image editing tools on Google Pixel phones, as well as the Snipping Tool in Windows 10 and 11. The vulnerability allowed cropped images to retain parts of the original full-screen content because the editing software failed to properly truncate the file, leaving residual data accessible.

To validate this hypothesis we can use the web tool [Acropadetect](https://lordofpipes.github.io/acropadetect/), which quickly tells us that it has this vulnerability, as well as the amount of extra data found.

> **Capture.png** Vulnerable! Has 409.4 KiB more than it should


## Tools

Several web tools can attempt aCropalypse recovery—like [acropalypse.app](https://acropalypse.app/) and [Acropalypse‑Multi‑Tool](https://github.com/frankthetank-music/Acropalypse-Multi-Tool)—but they often produce noisy output or require complex installs.

Instead, I adapted the Python logic into a lean, command‑line utility specifically for Windows‑style screenshots: [**SnipRecover-CLI**](https://github.com/m31r0n/SnipRecover-CLI). 

```bash
> ls
Capture.png  LICENSE  README.md  sniprecover.py
> python3 sniprecover.py detect Capture.png
[VULNERABLE] Capture.png
> python3 sniprecover.py restore Capture.png
[RESTORED] restored-Capture.png
> feh restored-Capture.png
```
_(Feel free to swap_ `_feh_` _for your favorite Linux image viewer.)_

Opening `restored-Capture.png` reveals the full Excel view. The Google row’s password cell now reads in full:

![Restored](/Site/static/images/Blog/Restore-CaptureThis-RootMe.png)

With this string in hand, we can unlock the KeePass database. Inside the **Root-me** entry, the password field finally reveals our flag:

![Restored](/Site/static/images/Blog/KeePass-CaptureThis-Flag.png)

> **Flag:** @cropalypse_vuln_is_impressive

---
## Additional Reading

About PNG structure:
- [PNG structure for beginner](https://medium.com/@0xwan/png-structure-for-beginner-8363ce2a9f73)
- [PNG Specification](https://www.w3.org/TR/png/)

Additionally, this challenge reminded me of some steganography challenges involving JPEG files. In those cases, the behavior is related to the intrinsic structure of the file and the manipulation of dimension indices. You can find more information and an example [here](https://cyberhacktics.com/hiding-information-by-changing-an-images-height/)