# Errata

Known problems in hardware that has already been built, and what to do about
them.

**This file is the right place to look if your board does not behave like the
schematic says it should.** Design files are only corrected in the next
revision — a fix to the source does not help someone holding a board that was
already made. So problems found after a release are written down here instead.

Each entry names the affected revision explicitly. If your board's revision is
not listed, the entry does not apply to it.

---

## Anthracite v1.0

No errata recorded yet.

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

## Reporting

If you find something that belongs here, please
[open an issue](https://github.com/trope-oshw/anthracite/issues) with your
board revision and firmware version. Errata are useful only if they are found
before the next person hits the same problem.
