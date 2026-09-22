# skill-kb-workout

A Claude Agent Skill that generates functional workouts combining kettlebell training and calisthenics, using CrossFit-style formats (EMOM, AMRAP, RFT) in the style of gym-board "METCON" sessions.

## What the skill does

Given a request for a workout, routine, WOD, metcon, or gym session, the skill builds a structured session out of a standard skeleton:

1. **Warm Up** — light bodyweight/mobility movements
2. **Activation EMOM** — short technique-focused block
3. **Main EMOM/AMRAP** — the main conditioning block, rotating kettlebell and calisthenics stations
4. **Finisher** (optional) — a short bodyweight-only burnout

It always checks current equipment before programming anything, and pulls exercises from a maintained exercise bank rather than inventing movements on the fly.

## Equipment assumptions

The user currently has:
- **1 kettlebell** — a single unit, so all kettlebell work must be unilateral or alternating (never bilateral moves like a double front rack)
- **A pull-up bar**
- **Bodyweight** — always available

Sandbag and macebell are tracked but marked "Not available" until the user confirms they own one. See [references/equipment.md](references/equipment.md) for the full, current equipment table.

## File structure

```
skill-kb-workout/
├── README.md              this file
├── SKILL.md               skill definition (frontmatter + instructions Claude follows)
└── references/
    ├── equipment.md        equipment inventory (what's Available / Not available)
    └── exercises.md        exercise bank (kettlebell + calisthenics), the source of truth for exercise selection
```

- **SKILL.md** defines when the skill triggers, the workout structure, exercise design rules for a single kettlebell, and the expected output format.
- **references/equipment.md** is checked first, before any workout is built, to make sure only available tools are used.
- **references/exercises.md** is the exercise database the skill draws from when filling each block.

## How to extend the exercise bank

To teach the skill a new exercise, add a row to the relevant table in [references/exercises.md](references/exercises.md) (Kettlebell or Calisthenics section):

```
| Exercise | Pattern | Main Muscles | Notes |
```

No changes to `SKILL.md` are needed — the skill reads `exercises.md` directly every time it builds a workout.

## How to update equipment

When the user's equipment changes (new tool acquired, tool no longer available, quantity changes — e.g. a second kettlebell), update the table in [references/equipment.md](references/equipment.md): set the correct **Status**, **Quantity**, and add a note if the change affects exercise design (for example, a second kettlebell would unlock bilateral kettlebell movements).

## Example usage prompts

- "Give me a 30-minute full body metcon with the kettlebell."
- "I want a lower body EMOM, about 20 minutes."
- "Build me an upper body WOD, no more than 25 minutes total."
- "Same as yesterday's workout but one more round and less rest."
- "I just got a sandbag, can you add it to my equipment and use it next time?"
- "Add battle ropes to the exercise bank as a finisher option."
