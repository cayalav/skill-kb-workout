# Equipment Tracker

This file tracks the equipment actually available to build workouts with. It is the source of truth for what the skill is allowed to program — only tools marked **Available** should appear in a generated session.

| Tool | Status | Quantity | Notes |
|---|---|---|---|
| Kettlebell | Available | 1 (12kg) | Single unit — no pairs, so all kettlebell exercises must be unilateral or alternating (never bilateral moves like double front rack or double swing) |
| Sandbag | Not available | 0 | Don't program sandbag work until the user confirms they have one |
| Macebell | Not available | 0 | Don't program macebell work until the user confirms they have one |
| Pull-up bar | Available | 1 | Fixed bar; enables pull-ups and hanging core work |
| Bodyweight | Available | — | Always available; no equipment required |

## How the skill uses this file

Before building any workout, the skill reads this table and filters `references/exercises.md` down to exercises that only require tools marked **Available**. Exercises tied to "Not available" equipment (sandbag, macebell) are excluded from rotations even if they're listed in the exercise bank, unless the user explicitly says they now have that equipment for that session.

## How to update this file

When the user's equipment changes (gets a new tool, loses access to one, adds a second kettlebell, etc.):

1. Update the **Status** column (Available / Not available).
2. Update **Quantity** if relevant (e.g., a second 12kg kettlebell would unlock bilateral movements).
3. Add a short note if the change affects exercise design rules (e.g., "2x 12kg kettlebell available → bilateral exercises now allowed").

No changes to `SKILL.md` are needed — the skill reads this file directly each time it builds a workout.
