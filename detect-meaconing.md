# Detecting meaconing in real time

Source: https://meaconing.com/detect-meaconing/ · Last reviewed: 7 October 2026 · By the meaconing.com editorial team
Site: https://meaconing.com/ · Sister site: https://gnssdenial.com/

Meaconing is very hard to detect in real time with GNSS checks alone, because the signals are genuine and consistent. The reliable method is comparing GNSS against **independent absolute navigation** such as terrain referencing, scene matching and inertial motion.

## Afterwards is easy. During is hard.

After the event, analysts can often reconstruct a meaconing attack from logs. The hard part is catching it while it happens, from inside the aircraft, with only the receiver's own view.

## An illustrative incident, second by second

This is an illustrative scenario, not a recorded event. It shows what a drone and its ground station experience.

| Time | What happens |
|---|---|
| T+0 s | **Normal flight.** The drone navigates by GNSS on a survey line. Everything is genuinely fine. |
| T+4 s | **Meaconer switches on.** A relay on a hilltop 2 km away starts re-sending the sky at low power. Nothing visible changes yet. |
| T+10 s | **Power creeps up.** The copy rises gently above the real signal. Signal-strength readings move a little, within normal flight variation. |
| T+14 s | **Capture.** The receiver's tracking slides from the real signal to the copy. Its clock estimate jumps by a few microseconds, and the clock filter smooths that over. |
| T+20 s | **Wrong position, clean fix.** The receiver now reports the hilltop. Eleven satellites, valid signatures, integrity check passed. |
| T+45 s | **The autopilot "corrects".** It believes it has drifted 2 km and steers to fix an error that doesn't exist, flying away from its real route. |
| T+3 min | **Failsafe makes it worse.** Return-to-home and geofencing both rely on the same false position. The drone heads for a "home" computed from the attacker's location. |

At T+20 s the ground station shows a 3D fix, 11 satellites in use, HDOP 0.8, OSNMA authentication PASS, RAIM integrity PASS and a plausible map. In reality the drone is 2 km from where every indicator says it is.

## Which checks catch meaconing as it happens?

Most anti-spoofing tools were designed to catch forged signals. Against a genuine signal replayed, most of them have little to grab onto.

| Check | How it works | Catches meaconing in real time? |
|---|---|---|
| Integrity monitoring (RAIM) | Flags a satellite that disagrees with the rest. | No. All satellites arrive through the same relay and agree. |
| Signal authentication (OSNMA, Chimera) | Verifies a cryptographic signature in the message. | No. The signatures are real. |
| Multi-constellation, multi-frequency | Compares GPS, Galileo, BeiDou and several bands. | Partly. A wideband relay copies every band at once. |
| Signal-strength monitoring | Watches for signals that are suspiciously strong. | Sometimes. A careful attacker keeps power close to normal. |
| Clock-jump monitoring | Watches for sudden steps in the receiver's clock. | Sometimes. A gradual takeover hides inside normal clock noise. |
| Direction finding (antenna arrays) | Detects that every signal comes from one direction. | Often. Heavy, costly and rare on small drones. |
| Inertial sensors only | Compares GNSS with measured motion. | Sometimes. Small-drone sensors drift quickly and get pulled along by the GNSS. |
| Independent absolute navigation | Compares GNSS with terrain, imagery and inertial motion. | Yes. The terrain below doesn't match the reported position. |

## Tell-tale signs for operators

- **Position stuck in place.** GNSS reports almost no movement while airspeed and motor data say the vehicle is flying.
- **A suspiciously fixed location.** Several vehicles report the same point, often a hilltop, building or vessel.
- **Small clock or time jumps.** The receiver's time steps by microseconds, or log timestamps don't match other systems.
- **Every satellite equally strong.** Real satellites vary with elevation. A relay makes them look similar.
- **Map vs camera mismatch.** The video feed shows a road or coastline that shouldn't be there.
- **Failsafes acting oddly.** Geofence alarms, or return-to-home heading in an unexpected direction.

## Quick answers

### Can meaconing be detected in real time?

It is very hard with GNSS checks alone, because the signals are genuine and consistent. Clues like clock jumps or uniform signal strength can be hidden by a careful attacker. The reliable method is comparing GNSS with independent absolute navigation such as terrain referencing and scene matching.

### Why doesn't the relay delay show up as an error?

The relay adds the same delay to every satellite's signal. A receiver already solves for its own clock error, so it treats the delay as its clock running late and reports a clean position fix.

### What are the signs of meaconing?

Position stuck in place while the vehicle is moving, several vehicles reporting the same fixed point, small clock or time jumps, every satellite looking equally strong, a map that disagrees with the camera, and failsafes behaving oddly.

## Keep reading

- [Does OSNMA stop meaconing?](https://meaconing.com/osnma-and-meaconing/)
- [Meaconing and drones](https://meaconing.com/meaconing-and-drones/)
- [What is meaconing?](https://meaconing.com/what-is-meaconing/)
- [The full explainer](https://meaconing.com/)

## Sources

1. [Detecting meaconing attacks by analysing receiver clock bias](https://www.researchgate.net/publication/265008517_Detecting_Meaconing_Attacks_by_Analysing_the_Clock_Bias_of_Gnss_Receivers)
2. [Sensors, Machine learning spoofing detection on real meaconing data](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7070933/)
3. [NAVIGATION (ION), Multipath situation under meaconing](https://navi.ion.org/content/73/1/navi.738)
4. [Inside GNSS, OSNMA: necessary but not sufficient](https://insidegnss.com/osnma-necessary-but-not-sufficient-for-gnss-security/)
5. [arXiv, Distributed and mobile message-level relaying of GNSS signals](https://arxiv.org/pdf/2202.11341)

Disclosure: this site features Navion Terra by Ultrakinematic. See https://meaconing.com/about/
