---
layout: slide
title: "Progress Report: Smart Home NFC Setup"
subtitle: "SecEng | Thesis Colloquium"
description: Bi-weekly progress report of my Bachelor Thesis (2018-06-06)
author: "Bernd Busse"
date: 2018-06-06
theme: /theme/rub.css
highlight: /theme/hl/github.css
section_header: true
section_footer: true
title_slide: /theme/seceng_title.html
end_slide: /theme/seceng_end.html
transition: convex
widescreen: false
center: false
---

# Overview
<!-- .slide: class="center" -->

### Employ **NFC** to set up new smart home devices with one's smartphone.

* Develop a protocol for this applicaiton:
    - *Secure* integration into existing infrastructure.
* Proof-of-concept implementation on *Android* and a *Raspberry Pi*.
    - Exchange *WiFi-SSID* and *WPA2-PSK*

Note:
- First presentation -> Short introduction
- Examine if and how NFC is applicable to configure smart home devices.
    - Existing methods like WiFi Hotspots or Bluetooth pairing
- Develop a protocol to securely configure devices over NFC (initial)
- Implement this protocol with *Android* and a *Rapsberry Pi*

---

# Current Progress
<!-- .slide: class="center" -->

### Mostly done

* Implementation works and devices can communicate with each other.
    - Encryption is not yet implemented.
* Paper is missing a conclusion and details about the protocol.

Note:
- Most stuff has been written
- Implementation works on both platforms
- Encryption and the like not yet done
- Paper is still missing details about the protocol messages


### Protocol Overview
<!-- .slide: class="center" -->

1. Touch devices together
    - SH device contains an NDEF message with its ID and capabilities
2. User enters credentials to be configured
3. Touch devices together
    - Smartphone writes NDEF message with the configuration values

Note:
- Two steps: *Device Discovery* and *Device Configuration*
- Optionally encrypt the message contents
- The user verifies the device configuration
- Make sure we only allow subsequent configurations by the same device

---

# Next Steps
<!-- .slide: class="center" -->

* Protocol chapter and conclusion has to be finished
    - Explicit description of protocol messages and its contents
    - Countermeasures against different attackers
* Tweaking the implementation to handle messages correctly
    - New hardware just arrived
    - If the time allows: Add lightweight crypto

*Print the thesis and hand it in!*

