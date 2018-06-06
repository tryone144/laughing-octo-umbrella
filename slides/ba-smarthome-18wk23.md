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

* Develop a protocol for this applicaiton.
* Proof-of-concept implementation on *Android* and a *Raspberry Pi*.

---

# Current Progress
<!-- .slide: class="center" -->

### Mostly done

* Implementation works and devices can communicate with each other.
* Paper is missing a conclusion and some details about the protocol.


### Protocol Overview

1. Touch devices together
    - SH device contains an NDEF message with its ID and capabilities
2. User enters credentials to be configured
3. Touch devices together
    - Smartphone writes NDEF message with the configuration values

*In case of our implementation: WiFi-SSID and WPA2-PSK*

---

# Next Steps
<!-- .slide: class="center" -->

* Protocol chapter and conclusion has to be finished
* Tweaking the implementation to handle messages correctly

*Print the thesis and hand it in!*

