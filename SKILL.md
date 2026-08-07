---
name: sop-builder
description: Turn something you just finished into a documented, repeatable procedure, then decide whether it should live as an SOP, a skill, or a scheduled routine. Trigger on "sop", "document this process", "make this repeatable", "write this up so I can do it again", "turn what we just did into a procedure", "how do I hand this off", or after finishing a multi-step task that worked and will recur. The source is the completed work itself, not an interview about it.
---

# SOP Builder

## Objective

Capture a procedure that already worked so it can be run again by you, by someone else, or by Claude, without rediscovering it. Then answer the question that decides its real value: **who should be running this?**

## Prefer the transcript over the interview

The strongest source is the task that just happened. Read what was actually done: the commands run, the order, the thing that failed and how it was fixed, the decision points where a different input would have changed the path. Reconstruct from evidence.

Interviewing the user is the fallback for procedures done in the past or outside this session. When you must ask, ask about **failure modes and decision points**, not about the happy path. People narrate the happy path accurately and forget the parts that actually make a procedure hard.

## The routing question (the most valuable part)

After drafting, decide out loud where this belongs. Getting this right is worth more than the document:

| Signal | Home |
|---|---|
| Needs human judgment, physical action, or an account only the user can access | **SOP**, a doc the user follows |
| Claude could run it end to end given the same inputs | **Skill**, so it fires automatically instead of being remembered |
| Runs on a clock or a trigger and nobody should have to remember it | **Routine**, on a scheduler (cron, a scheduled-tasks MCP, or your CI) |
| Mostly Claude with one human gate | **Skill plus a written approval step** |

Say the recommendation explicitly. A procedure that has been run three or more times and needs no human judgment has outgrown being a document, and leaving it as one is a small ongoing tax. Offer to build the skill.

## The SOP itself

Save to `docs/sops/<slug>.md` for general procedures, or `docs/projects/<project>/sops/<slug>.md` when it is project-specific. Any notes folder or wiki works; keep the location consistent so SOPs stay findable. Frontmatter: `title`, `type: sop`, `created`, `runs` (how many times it has been executed, starting at 1), `owner`.

It needs: the **trigger** (what situation starts this), **preconditions** (what must be true first, including access and credentials), the **steps** in order with the actual commands or clicks, **decision points** written as "if X then Y" rather than prose, **failure modes** with the specific fix for each, and a **done check** that is observable rather than assumed.

Write for someone competent who has never done this before. Name the exact file, the exact command, the exact button. "Configure the settings" is not a step.

## Done looks like

- Someone could follow it without asking a clarifying question.
- Every step that can fail says how it fails and what to do about it.
- The done check is something you can observe, not something you assume.
- The routing recommendation is stated, with a reason.

## Verify before saving

Walk the steps against what actually happened and look for the gap between them. The most common defect is a skipped step that felt obvious in the moment: an environment variable that was already set, a directory that already existed, an approval that was already granted. Those are exactly what break the procedure for the next person, including future you.

## Anti-patterns

- Documenting the happy path only, so the first real failure sends someone back to square one.
- Writing an SOP for something that should obviously be a skill, which quietly guarantees it will not get run.
- Vague verbs (configure, set up, handle) where a specific command belongs.
- Padding with context nobody executing the procedure needs.
