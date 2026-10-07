# What is meaconing?

Source: https://meaconing.com/what-is-meaconing/ · Last reviewed: 7 October 2026 · By the meaconing.com editorial team
Site: https://meaconing.com/ · Sister site: https://gnssdenial.com/

**Meaconing** is capturing genuine satellite navigation (GNSS) signals and re-broadcasting them from another place or time. A receiver that locks onto the copy calculates the position of the attacker's antenna instead of its own, and every built-in check still reports the position as valid.

## Meaconing in plain words

Say it: **MEE-kuh-ning**. The word comes from "meacon", short for "masking beacon".

A GPS receiver listens to satellites and works out where it is. In meaconing, an attacker records those same real signals and plays them back from somewhere else. The receiver hears the replay, trusts it and calculates the wrong position. Nothing in the signal is forged, so nothing looks wrong.

## How a receiver finds its position

**GNSS** (Global Navigation Satellite System) is the family name for GPS and its cousins: Europe's Galileo, Russia's GLONASS and China's BeiDou. Together they have well over 100 satellites in orbit.

Each satellite carries an atomic clock and keeps broadcasting one simple message: "This is satellite 12. The time is exactly this. I am exactly here." The receiver notes how late each message arrives. Radio travels at the speed of light, about 300 km every thousandth of a second, so a delay converts into a distance. With distances to several satellites, the receiver works out where it is.

The receiver's own clock is cheap and inaccurate, so it needs a **fourth satellite** just to work out its own clock error. That detail is exactly the gap meaconing slips through.

## What the attacker does

A meaconer does not make anything up. It listens to the real satellites with one antenna and re-transmits what it hears from another, a little louder. The messages, codes and digital signatures are all authentic, because they are the real thing.

The only false part is **where and when** the signal is coming from. A receiver locked onto the copy computes the position of the attacker's listening antenna, not its own.

## Why the receiver believes it

- **The data is genuine.** Every navigation message really did come from a satellite. There is nothing false inside the signal to find.
- **The signatures check out.** Authentication such as Galileo's OSNMA proves a message came from a satellite. A copy of that message did.
- **All satellites agree.** Integrity checks such as RAIM look for one satellite that disagrees with the others. In meaconing they all arrive through the same relay, so they agree perfectly.
- **Louder wins.** Receivers lock onto the strongest matching signal. The real one is fainter than background noise, so the copy only needs a modest boost.
- **The delay hides in the clock.** The relay adds the same extra delay to every satellite. To the receiver, that looks exactly like its own clock running slightly late, so it quietly corrects "its clock" and reports a clean fix.

The extra delay never shows up as an error. The position simply becomes the attacker's antenna, and the time becomes slightly wrong.

## Three ways to meacon

| Form | How it works | Result for the victim |
|---|---|---|
| Live relay (the repeater) | One antenna receives the sky, another re-transmits it a few microseconds later. | Victims nearby compute the receiving antenna's position. |
| Record and replay (the recording) | Raw signals are recorded at one place and time, then played back later. | Victims relive someone else's journey, at the wrong time. |
| Long-distance relay (the tunnel) | Signals captured in one city are streamed over the internet and re-broadcast in another. | Victims compute a position hundreds of kilometres away. |

Research shows the long-distance form can even re-create authenticated messages at the far end.

## Quick answers

### What is meaconing in simple terms?

Meaconing is recording or capturing real satellite navigation signals and re-broadcasting them. A receiver that listens to the copy calculates the position of the attacker's antenna instead of its own, while believing the result is correct.

### How do you pronounce meaconing?

MEE-kuh-ning. The word comes from "meacon", short for "masking beacon".

### How far off can meaconing put a drone?

With a live relay, the drone's reported position becomes the attacker's receiving antenna. The error equals the distance between the drone and that antenna, from metres to kilometres. With record-and-replay or long-distance relay it can be hundreds of kilometres.

### Is meaconing illegal?

In most countries, transmitting on GNSS frequencies without authorisation is illegal, and GNSS repeaters are tightly regulated. Most large-scale interference today is attributed to military electronic warfare.

## Keep reading

- [Meaconing vs GPS spoofing](https://meaconing.com/meaconing-vs-spoofing/)
- [Detecting meaconing in real time](https://meaconing.com/detect-meaconing/)
- [The history of meaconing](https://meaconing.com/history-of-meaconing/)
- [The full explainer](https://meaconing.com/)

## Sources

1. [SBG Systems, Meaconing glossary](https://www.sbg-systems.com/glossary/meaconing/)
2. [arXiv, Distributed and mobile message-level relaying of GNSS signals](https://arxiv.org/pdf/2202.11341)
3. [Inside GNSS, OSNMA: necessary but not sufficient](https://insidegnss.com/osnma-necessary-but-not-sufficient-for-gnss-security/)
4. [Detecting meaconing attacks by analysing receiver clock bias](https://www.researchgate.net/publication/265008517_Detecting_Meaconing_Attacks_by_Analysing_the_Clock_Bias_of_Gnss_Receivers)
5. [Stanford GPS Lab, Conventional navigation aids](https://web.stanford.edu/group/scpnt/gpslab/pubs/books/Chapter3ConventionalNavigation.pdf)

Disclosure: this site features Navion Terra by Ultrakinematic. See https://meaconing.com/about/
