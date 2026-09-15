# Errata

Known problems in hardware that has already been built, and what to do about
them. This file also lists recommended modifications: changes that fix nothing,
but improve a board you already have.

**This file is the right place to look if your board does not behave like the
schematic says it should.** Design files are only corrected in the next
revision — a fix to the source does not help someone holding a board that was
already made. So problems found after a release are written down here instead.

Each entry names the affected revision explicitly. If your board's revision is
not listed, the entry does not apply to it.

---

## Anthracite v1.0

No errata recorded yet.

The entry below is a recommended modification, not an erratum. A v1.0 board
works as designed without it.

### M-1 · R38 / R86 at 200 MΩ for less switching pop

**Affects:** Anthracite v1.0, all boards. R38 and R86 on the top board are
100 MΩ.

**What it improves:** the low thump ("pop") at the output when the pedal
switches between bypass and effect. With 100 MΩ, v1.0 already meets the pop
target set during development, by 3.2 – 4.0 dB. Raising R38 and R86 to 200 MΩ
lowered the pop by a further 4.9 – 6.3 dB. By ear, the pop was then hard to
hear without turning the gain after the pedal well up.

**How it was measured:** on a prototype with the same output-switch values as
v1.0 (R37 = R85 = 47 kΩ, R90 = 15 kΩ). Pop was taken as the peak-to-peak output
after a first-order high-pass filter at 10 Hz or 20 Hz, which removes a slow,
inaudible part of the transient. Effect to bypass: 6.0 – 6.3 dB lower. Bypass
to effect: 4.9 – 5.0 dB lower.

**Why it works:** while a JFET switch (Q8 bypass, Q17 effect) is on, a small
current flows into its gate through R38 or R86, plus the leakage of the series
diode D21 or D28. That current sets a DC level on R90, and the level dips while
the switches change over; the dip is what you hear. Doubling the resistor
roughly halves the current. Measured with a DMM, it fell from 84.0 nA to
44.5 nA.

**Change:** replace both R38 and R86 with 200 MΩ. Change both, not one: the
result above assumes both switches draw the same gate current. The prototype
used two 100 MΩ resistors in series in each position.

**Costs and cautions:**

- **Temperature.** The current through the resistor does not change with
  temperature, but the diode leakage roughly doubles every 10 °C. With 200 MΩ
  the leakage is a larger share of the gate current (about 19 % instead of
  10 % at room temperature), so pop rises more when the pedal is warm. A model
  estimate for 45 °C inside the enclosure gives about +2.8 dB with 200 MΩ,
  against about +1.7 dB with 100 MΩ. This has not been measured.
- **Switching speed.** The gate charging time set by this resistor doubles,
  from about 1.25 ms to 2.5 ms (calculated). The gate RC networks already take
  tens of milliseconds, so the switching timing is not expected to change
  noticeably.
- **Not yet checked: distortion at high level.** With half the gate current,
  a switch may recover more slowly when a large low-frequency signal drives its
  gate, which could add distortion near maximum output. This has not been
  measured.
- **Leakage around the part.** At 200 MΩ, flux residue or other surface leakage
  can bypass the resistor and cancel the improvement. To confirm the change
  worked, measure the DC voltage across R90 with a DMM before and after, with
  the pedal in the same state. It should roughly halve; on the prototype it
  went from 956 µV to 506 µV.

**In later revisions:** 200 MΩ is planned, but no revision or date is set.

---

## How to read this file

Entries are written in this form:

> ### E-1 · Short title
>
> **Affects:** which revision(s), and how to tell whether yours is one of them
> **Symptom:** what you actually observe
> **Cause:** why it happens
> **Workaround:** what to do with a board you already have
> **Fixed in:** the revision that corrects it, or "not yet"

The workaround matters more than the cause. If you own the hardware, you need
to know what to do about it; the explanation is there so you can judge whether
the workaround is safe in your situation.

Recommended modifications are numbered M-1, M-2, and so on. They say what the
change improves, how that was measured, what it costs, and whether later
revisions are expected to include it. None of them is needed for the pedal to
work as specified.

## Reporting

If you find something that belongs here, please
[open an issue](https://github.com/trope-oshw/anthracite/issues) with your
board revision and firmware version. Errata are useful only if they are found
before the next person hits the same problem.
