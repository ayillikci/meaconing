# Meaconing and drones

Source: https://meaconing.com/meaconing-and-drones/ · Last reviewed: 7 October 2026 · By the meaconing.com editorial team
Site: https://meaconing.com/ · Sister site: https://gnssdenial.com/

Drones are more exposed than airliners. They have no one on board, most rely on GNSS as their only absolute position, and their autopilots and failsafes trust it. Airliners add trained pilots, navigation-grade inertial systems, ground radio aids and air traffic control.

## Piloted aircraft cope with skill, and lots of backup

Crewed aircraft meet GNSS interference every day and keep flying safely. They have trained people on board, layers of independent instruments, ground infrastructure and air traffic control behind them.

- **Human instinct and judgement.** Two trained pilots notice when something doesn't add up: "The screen says we're over the sea, but the coast is right there."
- **Inertial reference systems.** Airliners carry high-grade inertial systems. Modern units drift about 0.6 nautical miles per hour without any satellite help.
- **Ground radio aids.** VOR, DME and ILS stations give position and approach guidance that don't depend on satellites.
- **Air traffic control radar.** Controllers see the aircraft on radar and can give headings and warnings.
- **Procedures and training.** Industry and regulator guidance, briefings on known hotspots, and checklists for GNSS loss.
- **A window.** Coastlines, runways and cities give an instant reality check in good weather.

## How does an autonomous platform handle it?

| Layer of protection | Crewed aircraft | Typical autonomous drone |
|---|---|---|
| Who notices? | Pilots on board, cross-checking constantly | Nobody on board. An operator, if any, watches a plausible-looking map from far away. |
| Backup position | Navigation-grade inertial systems | Small, low-cost motion sensors that drift quickly without correction |
| Ground radio aids | VOR, DME and ILS along routes and at airports | Usually none, and few reach low altitudes or remote areas |
| Outside help | Air traffic control and radar | Often beyond controlled airspace and radar cover |
| Reaction | Judgement, procedures, diversion | Autopilot logic that trusts GNSS by design |
| Failsafe | Crew decides where to go | Return-to-home steers by the same corrupted position |
| Against meaconing | Humans spot implausible positions | Every automated check passes, so the drone carries on |

Drones are already being lost to electronic warfare in large numbers. In 2023 the Royal United Services Institute estimated Ukraine was losing about 10,000 drones a month, mostly to electronic warfare that targets navigation and control links.

## Every class of drone is exposed, from hand-launched to MALE

Military and civil operators often group uncrewed aircraft by size using NATO's classes. All of them rely on GNSS, and the larger they are, the more is at stake when it lies.

| NATO class | Weight | Typical use |
|---|---|---|
| Class I, micro | Under 2 kg | Quadcopters for inspection, filming and short-range scouting |
| Class I, mini | 2-20 kg | Survey, mapping, delivery trials and hand-launched reconnaissance |
| Class I, small | 20-150 kg | Long-range fixed-wing and VTOL survey, border and pipeline patrol |
| Class II, tactical | 150-600 kg | Runway or catapult launched, many hours aloft for surveillance |
| Class III, MALE | Over 600 kg | Medium-altitude, long-endurance aircraft flying for a day or more |

## How drone operators can protect themselves

- Fit navigation that does not depend on GNSS for absolute position, and cross-check GNSS against it.
- Avoid relying on GNSS alone for return-to-home and geofencing.
- Log receiver data so incidents can be analysed afterwards.

## Disclosure: Navion Terra

One example of GNSS-independent navigation is Navion Terra by Ultrakinematic, a resilient navigation system for drones from small multirotors up to the MALE class. It fuses inertial, visual, scene-matching and terrain-referenced navigation, and outputs position with a confidence estimate at 100-250 Hz. This site features Navion Terra and links to its maker, so treat this paragraph as vendor information. See the [full description on the home page](https://meaconing.com/#navion).

## Quick answers

### Are drones more at risk than airliners?

Yes. Airliners have trained pilots, navigation-grade inertial systems, ground radio aids and air traffic control. Most drones rely on GNSS as their only absolute position, have no one on board, and run autopilots and failsafes that trust GNSS.

### How can drone operators protect against meaconing?

Fit navigation that does not depend on GNSS for absolute position, cross-check GNSS against it, avoid relying on GNSS alone for return-to-home and geofencing, and log receiver data so incidents can be analysed.

### What is Navion Terra?

Navion Terra by Ultrakinematic is a resilient navigation system for drones from small multirotors up to the MALE class. It fuses inertial, visual, scene-matching and terrain-referenced navigation, rejects jammed, spoofed or meaconed GNSS, and outputs position with a confidence estimate at 100-250 Hz.

## Keep reading

- [Detecting meaconing in real time](https://meaconing.com/detect-meaconing/)
- [What is meaconing?](https://meaconing.com/what-is-meaconing/)
- [Does OSNMA stop meaconing?](https://meaconing.com/osnma-and-meaconing/)
- [The full explainer](https://meaconing.com/)

## Sources

1. [Forbes on RUSI "Meatgrinder" report: 10,000 drones a month (2023)](https://www.forbes.com/sites/davidhambling/2023/05/22/ukraine-drones-losses-are-10000-per-month/)
2. [Unmanned Airspace, Ukrainian drone losses (RUSI)](https://www.unmannedairspace.info/counter-uas-systems-and-policies/ukrainian-drone-losses-at-10000-a-month-new-research-from-rusi/)
3. [SKYbrary, Inertial Reference System](https://skybrary.aero/articles/inertial-reference-system-irs)
4. [IATA, Safety risk assessment: GNSS interference](https://ic.iata.org/sites/default/files/iata_sih_document_attachment/IATA%20Safety%20Risk%20Assessment%20-%20GNSS%20Interference%20V5.pdf)
5. [Ultrakinematic, Navion Terra](https://ultrakinematic.com)

Disclosure: this site features Navion Terra by Ultrakinematic. See https://meaconing.com/about/
