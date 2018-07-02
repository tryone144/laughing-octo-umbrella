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
title_slide: /theme/seceng_ba_title.html
end_slide: /theme/seceng_ba_end.html
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

1. *Capabilities Message* (smart home device)

| Type | Length | Purpose |
| --- | --- | --- |
| <!-- .element: class="tt" --> sshsp:__V__ | 1B | Protocol Version (0x01 == v0.1) |
| <!-- .element: class="tt" --> sshsp:__T__ | 1B | Message Type: __C__ (0x43) |
| <!-- .element: class="tt" --> sshsp:__Uuid__ | 16B | Unique Device ID |
| <!-- .element: class="tt" --> sshsp:__Cap__ | variable | Device Capabilities |
| <!-- .element: class="tt" --> sshsp:__Sig__ | TBD | MAC of this message |

Note:

- Capabilities in a later report


### Protocol Messages
<!-- .slide: class="center" -->

2. <!-- .element: style="counter-increment: li;" --> *Configuration Message* (smartphone configurator)

| Type | Length | Purpose |
| --- | --- | --- |
| <!-- .element: class="tt" --> sshsp:__V__ | 1B | Protocol Version (0x01 == v0.1) |
| <!-- .element: class="tt" --> sshsp:__T__ | 1B | Message Type: __S__ (0x53) |
| <!-- .element: class="tt" --> sshsp:__Uuid__ | 16B | Unique Configurator ID |
| <!-- .element: class="tt" --> sshsp:__Target__ | 16B | Unique Target ID |
| <!-- .element: class="tt" --> sshsp:__Conf__ | variable | Configuration contents |
| <!-- .element: class="tt" --> sshsp:__Sig__ | TBD | MAC of this message |

Note:

- Actual configuration values in a later report


### Lightweight Ciphers
<!-- .slide: class="center" -->

* AES-like and SPN
    - LED
    - PRESENT
* <!-- .element: class="fragment" --> Feistel-like and ARX
    - SIMON and SPECK designed by the NSA for the IoT
    - LEA
    - KATAN

Note:

- SPN = Substitution-Permutation Network
    - *LED*: AES-style rounds, PRESENT S-Box, no key-schedule
    - *PRESENT*: not like AES, hardware oriented
- ARX = Addition Rotation XOR
    - *SIMON* / *SPECK*: by the NSA for the Iot, no security analysis yet
    - *LEA*: software oriented
    - *KATAN*: hardware oriented


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

