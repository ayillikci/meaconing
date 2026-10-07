# Does OSNMA stop meaconing?

Source: https://meaconing.com/osnma-and-meaconing/ · Last reviewed: 7 October 2026 · By the meaconing.com editorial team
Site: https://meaconing.com/ · Sister site: https://gnssdenial.com/

No. **OSNMA** proves a navigation message came from a real satellite. A replayed message did come from a real satellite, so its signature is valid. Tests have shown OSNMA-enabled receivers reporting meaconed signals as authentic.

## What OSNMA does

**OSNMA** (Navigation Message Authentication) is Galileo's digital signature for its open signal. It stops forged messages: a spoofer who builds fake signals cannot produce valid signatures, so a receiver that checks them can reject the fake.

## Why it does not stop meaconing

Authentication answers one question: "Did this message come from a satellite?" In meaconing the honest answer is yes. The attacker never forges anything. They copy a real message, signature included, and play it somewhere else or later.

The signature cannot tell the receiver where or when it was captured. That is the only false part of the attack, and nothing in the message checks it.

## Why integrity monitoring does not help either

**RAIM** (Receiver Autonomous Integrity Monitoring) looks for one satellite that disagrees with the others. In meaconing every satellite signal arrives through the same relay, so they all agree perfectly. The check passes.

## What about several constellations and frequencies?

Comparing GPS, Galileo, BeiDou and several frequency bands helps only partly. A wideband relay copies every band at once, so the copies agree with each other.

## What does work

The reliable approach is to compare GNSS with something the attacker cannot copy. Independent absolute navigation, such as terrain referencing and scene matching combined with inertial motion, asks whether the reported position matches the world below. A replayed signal can fool a receiver, but it can't move the hills, roads and coastlines under the aircraft.

## Summary: what each defence checks

| Defence | Question it asks | Stops meaconing? |
|---|---|---|
| OSNMA signal authentication | Is this message genuine? | No |
| RAIM integrity monitoring | Do all satellites agree? | No |
| Multi-constellation, multi-frequency | Do the bands agree? | Partly |
| Independent absolute navigation | Does the position match the terrain? | Yes |

## Quick answers

### Why doesn't signal authentication like OSNMA stop meaconing?

Authentication proves a message came from a real satellite. A replayed message did come from a real satellite. Tests have shown OSNMA-enabled receivers reporting meaconed signals as authentic.

### Does RAIM detect meaconing?

No. RAIM flags one satellite that disagrees with the others. In meaconing all satellites arrive through the same relay and agree.

### Does using several GNSS constellations protect against meaconing?

Only partly. A wideband relay can copy every constellation and band at once.

## Keep reading

- [Detecting meaconing in real time](https://meaconing.com/detect-meaconing/)
- [Meaconing vs GPS spoofing](https://meaconing.com/meaconing-vs-spoofing/)
- [What is meaconing?](https://meaconing.com/what-is-meaconing/)
- [The full explainer](https://meaconing.com/)

## Sources

1. [Inside GNSS, OSNMA: necessary but not sufficient](https://insidegnss.com/osnma-necessary-but-not-sufficient-for-gnss-security/)
2. [arXiv, Distributed and mobile message-level relaying of GNSS signals](https://arxiv.org/pdf/2202.11341)
3. [NAVIGATION (ION), Multipath situation under meaconing](https://navi.ion.org/content/73/1/navi.738)
4. [Detecting meaconing attacks by analysing receiver clock bias](https://www.researchgate.net/publication/265008517_Detecting_Meaconing_Attacks_by_Analysing_the_Clock_Bias_of_Gnss_Receivers)

Disclosure: this site features Navion Terra by Ultrakinematic. See https://meaconing.com/about/
