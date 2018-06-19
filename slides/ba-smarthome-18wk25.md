---
layout: slide
title: "Progress Report: Secure Smart Home NFC Setup"
subtitle: "SecEng | Thesis Colloquium"
description: Bi-weekly progress report of my Bachelor Thesis (2018-06-20)
author: "Bernd Busse"
date: 2018-06-20
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

### Recap: Goal of this thesis

* Employ **NFC** to set up new smart home devices with one's smartphone.
* Develop a protocol to *securely* exchange the required data.
* Proof-of-concept implementation on *Android* and a *Raspberry Pi*.

Note:

---

# Current Progress
<!-- .slide: class="center" -->

### New deadline: *2018-07-12*

More time to finish the protocol and update the implementation.

### NFC reader arrived

Works way better on the Raspberry Pi than the wonky USB-reader.

Note:


### Protocol Goals
<!-- .slide: class="center" -->

1. Securely exchange confidential credentials
    - Encryption
2. <!-- .element: class="fragment" --> Detect modified messages
    - Signature or MAC
3. <!-- .element: class="fragment" --> Disallow later re-configuration by different devices
    - Unique configurator ID
    - Hardware reset button
4. <!-- .element: class="fragment" --> Do not leak data to unsolicited configuration requests
    - User explicitly authorizes configuration (2. step)

Note:


### Protocol Messages
<!-- .slide: class="center" -->

Note:


### Lightweight Ciphers
<!-- .slide: class="center" -->

Note:


### Problems with the key exchange
<!-- .slide: class="center" -->

1. Client *Capabilites* contains plain key
    - <!-- .element: class="green" --> No computing overhead for key derivation
    - <!-- .element: class="orange" --> Eavesdropping needs \\(<1\) m distance to read
    - <!-- .element: class="red" --> Extract key before the user configures the device
        - <!-- .element: class="green" --> New random key on every access

Note:


### Problems with the key exchange
<!-- .slide: class="center" -->

2. <!-- .element: style="counter-increment: li;" --> (Elliptic-Curve) Diffe-Hellman key exchange
    - <!-- .element: class="green" --> Secure against eavesdropping
    - <!-- .element: class="orange" --> Key derivation has more overhead
    - <!-- .element: class="orange" --> Fixed public and private-key on device

Note:

---

# Next Steps
<!-- .slide: class="center" -->

### Todo
* Decide on a lightweight cipher to use
* Find a way to *securely* exchange the key
* <!-- .element: class="fragment" data-fragment-index="1" --> Implement protocol wrapper for *Android* and *Dummy*
    - Easily build protocol messages
    - Encryption and MAC primitves
* <!-- .element: class="fragment" data-fragment-index="2" --> Detailed description on attacker models
* <!-- .element: class="fragment" data-fragment-index="2" --> Finish the conclusion chapter

Note:

