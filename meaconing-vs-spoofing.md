# Meaconing vs GPS spoofing

Source: https://meaconing.com/meaconing-vs-spoofing/ · Last reviewed: 7 October 2026 · By the meaconing.com editorial team
Site: https://meaconing.com/ · Sister site: https://gnssdenial.com/

**Spoofing forges, meaconing copies.** A spoofer builds fake satellite signals from scratch. A meaconer re-sends real ones. Meaconing is a special type of spoofing, and it is harder to catch because the messages, codes and digital signatures are all genuine.

## Spoofing forges. Meaconing copies.

A spoofer has to build fake satellite signals from scratch. That takes skill, and the result can contain small mistakes that a careful receiver might catch.

A meaconer doesn't make anything up. It listens to the real satellites with one antenna and re-transmits what it hears from another, a little louder. The only false part is **where and when** the signal is coming from. A receiver locked onto the copy computes the position of the attacker's listening antenna, not its own.

## Side-by-side comparison

| What the receiver gets | Real sky | Spoofing | Meaconing |
|---|---|---|---|
| Signal origin | Satellites | Attacker's generator | Satellites, re-sent by attacker |
| Message content | Genuine | Forged | Genuine |
| Digital signature | Valid | Fails, if checked | Valid |
| Satellites agree? | Yes | Usually | Yes |
| Position computed | Your own | Attacker's choice | Attacker's antenna |
| Skill needed | None | High | Low to moderate |

## Where jamming fits

Jamming is different from both. A jammer blasts noise on GNSS frequencies so the receiver hears nothing at all. You notice jamming, because the receiver has nothing to work with. Spoofing and meaconing are harder to notice, because the receiver keeps working and reports a wrong position.

## Eight things that break satellite navigation

| Threat | What happens | Would you notice? |
|---|---|---|
| Jamming | A transmitter blasts noise so the receiver hears nothing. | You notice |
| Spoofing | A transmitter fakes satellite signals and gradually walks the receiver to a false position or time. | Hard to notice |
| Meaconing | An attacker records real signals and replays them. The content is genuine, so it passes authenticity checks. | Hardest to notice |
| Blockage | Tunnels, buildings, forests and roofs cut the line of sight to the satellites. | You notice |
| Multipath | Signals bounce off glass and concrete, so the receiver measures the wrong distances. | Sometimes |
| Space weather | Solar storms disturb the upper atmosphere and make signals flicker or fade. | Sometimes |
| System faults | The satellite systems themselves can fail. Galileo's public service was down for about six days in July 2019. | Sometimes |
| Accidental interference | Faulty electronics and illegal in-vehicle "privacy jammers" leak noise onto GNSS bands. | Sometimes |

For incident data covering every GNSS threat, see the sister site [gnssdenial.com](https://gnssdenial.com).

## Quick answers

### Is meaconing the same as GPS spoofing?

It is a type of spoofing, but a special one. Ordinary spoofing creates fake signals. Meaconing re-sends genuine ones. That is why it passes authenticity checks that can reveal ordinary spoofing.

### Is a replay attack the same as meaconing?

A replay attack, recording signals and playing them back later, is a form of meaconing. Meaconing also includes live relaying, where the copy is re-sent within microseconds.

### What is the difference between jamming and spoofing?

Jamming broadcasts noise on GNSS frequencies so receivers cannot hear satellites. Spoofing broadcasts fake GNSS signals to make a receiver report a false position or time.

### Which is harder to detect, spoofing or meaconing?

Meaconing. Its signals are genuine, its digital signatures are valid, and all satellites agree, so most checks designed to catch forged signals have little to grab onto.

## Keep reading

- [What is meaconing?](https://meaconing.com/what-is-meaconing/)
- [Does OSNMA stop meaconing?](https://meaconing.com/osnma-and-meaconing/)
- [Detecting meaconing in real time](https://meaconing.com/detect-meaconing/)
- [The full explainer](https://meaconing.com/)

## Sources

1. [SBG Systems, Meaconing glossary](https://www.sbg-systems.com/glossary/meaconing/)
2. [Inside GNSS, OSNMA: necessary but not sufficient](https://insidegnss.com/osnma-necessary-but-not-sufficient-for-gnss-security/)
3. [arXiv, Distributed and mobile message-level relaying of GNSS signals](https://arxiv.org/pdf/2202.11341)
4. [IATA, Safety risk assessment: GNSS interference](https://ic.iata.org/sites/default/files/iata_sih_document_attachment/IATA%20Safety%20Risk%20Assessment%20-%20GNSS%20Interference%20V5.pdf)
5. [OPSGROUP, GPS Spoofing Workgroup Final Report (2024)](https://ops.group/dashboard/wp-content/uploads/2024/09/GPS-Spoofing-Final-Report-OPSGROUP-WG-OG24.pdf)

Disclosure: this site features Navion Terra by Ultrakinematic. See https://meaconing.com/about/
