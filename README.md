# sop-builder

Turn something you just finished into a documented, repeatable procedure, then decide whether it belongs as an SOP, a skill, or a scheduled routine.

An original skill by Silicon Valley Academy.

## What it does

Most SOP tools interview you about a process. This one reads the work that just happened: the commands run, the order, the thing that broke and how it got fixed, the decision points where a different input would have changed the path. Reconstructing from evidence beats reconstructing from memory, because people narrate the happy path accurately and forget the parts that make a procedure hard.

Then it answers the question worth more than the document itself: who should be running this?

| Signal | Home |
|---|---|
| Needs human judgment, physical action, or an account only you can access | An SOP you follow |
| Claude could run it end to end given the same inputs | A skill, so it fires instead of being remembered |
| Runs on a clock and nobody should have to remember it | A scheduled routine |
| Mostly Claude with one human gate | A skill plus a written approval step |

The SOP it writes includes the trigger, preconditions, exact steps, decision points as "if X then Y", failure modes with specific fixes, and a done check you can observe rather than assume.

## Install

Paste this into Claude Code:

```
Install the sop-builder skill from github.com/sva-admin/sop-builder
```

It triggers on "sop", "document this process", "make this repeatable", "how do I hand this off", or right after finishing a multi-step task that worked and will recur.

## Learn free

Learn free at https://loop.sv-academy.org/tutorials

---

More skills: https://github.com/sva-admin/claude-skills
Silicon Valley Academy: https://sv-academy.org
