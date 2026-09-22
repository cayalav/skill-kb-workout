---
name: kb-workout-generator
description: >-
  Generates personalized functional workouts combining kettlebell training and calisthenics, using CrossFit-style formats like EMOM, AMRAP and RFT. ALWAYS use this skill when the user asks for a workout, routine, WOD, metcon, gym session, or mentions words like "workout", "training", "today's session", "upper body/lower body/full body day", even if they don't explicitly mention kettlebell or EMOM/AMRAP format. Also use it when the user asks for variations, progressions, or to adapt a previous workout.
---

# Kettlebell + Calisthenics Workout Generator

This skill generates structured functional workouts in the style of gym-board "METCON" sessions, combining kettlebell training with bodyweight calisthenics.

## User's available equipment

Before building any workout, read `references/equipment.md`. That file is the source of truth for what equipment is currently available (kettlebell count/weight, sandbag, macebell, pull-up bar, etc.) — only use tools marked "Available" there, and treat everything else as off-limits unless the user explicitly says otherwise in the conversation.

If the user mentions acquiring new equipment (a sandbag, a second kettlebell, a different KB weight, etc.), help them update the "Status"/"Quantity"/"Notes" fields in that table rather than just noting it for this conversation only — that way the change persists for future sessions.

**Important:** if `equipment.md` shows only a single kettlebell (any weight), keep all kettlebell exercises unilateral or arm-alternating — never bilateral/double moves like "double front rack" — unless the equipment file lists more than one unit.

## Exercise bank

Read `references/exercises.md`. That file contains the full table of available exercises (kettlebell and calisthenics), with movement pattern, muscles worked, and coaching notes. Use it as the source of truth when selecting and rotating exercises in each block — don't invent exercises that aren't listed there unless the user explicitly mentions them.

If the user mentions learning a new exercise or asks to "add X to the skill", help them add a row to that table following the existing format (Exercise | Pattern | Muscles | Notes), instead of improvising how to include it each time.

## Standard workout structure

Always follow this skeleton, matching gym-board style classes (BSF/CrossFit style):

1. **WARM UP** (x3 rounds, 3-4 light exercises, bodyweight, ~5 min total): general activation, no kettlebell or very light KB movements (halo, pass-around). Always specify the round count explicitly (e.g. "x3 rounds") in the output — don't leave it implicit.
2. **ACTIVATION BLOCK** — short EMOM (x4-6 min): 1-2 exercises, technique and mobility focus, moderate intensity.
3. **MAIN BLOCK** — long EMOM (must be a multiple of the station count, typically 15-25 min) or AMRAP (8-15 min): 4-6 exercises rotating stations, combining kettlebell and calisthenics. Always include a rest station ("REST") as the last one if it's a multi-round EMOM — and count it as a station when checking that total duration divides evenly.
4. **FINISHER** (optional) — short AMRAP (5-8 min) or burnout, usually kettlebell-free (bodyweight only) to close out with accumulated fatigue.

## Exercise design rules

- Check `references/equipment.md` first to know how many kettlebells are available and at what weight(s). With a single unit, use unilateral exercises (snatch, clean, press, one-arm swing) or alternating ones (even reps split between both arms), never bilateral/double. If a second unit is available, bilateral variations (double KB front squat, double press, etc.) become valid options.
- Alternate movement patterns between stations: press (vertical/horizontal), hinge (swing/deadlift), squat (goblet/front), pull (row/pull-up), core, and locomotion/cardio (burpees, mountain climbers, jumping jacks).
- If the user asks for "upper body": prioritize press, pull, core, without fully excluding squat/hinge as a cardio transition.
- If they ask for "lower body": prioritize squat, hinge, lunges; use press/pull only as a transition.
- If they ask for "full body": distribute evenly.
- Calibrate rep difficulty to a realistic EMOM pace (reps should be comfortably completable in <45sec within the minute, leaving room for rest).
- **The main EMOM's total duration must be an exact multiple of its number of stations** (each station = 1 minute). E.g. 4 exercises + a REST station = 5 stations, so valid durations are 15', 20', 25'... — never something like 18' or 22' that cuts the last round short. If dropping REST to fit a duration, 4 stations alone gives valid durations of 16', 20', 24'... Always double-check this division before finalizing the workout.

## Output format

Present it in plain text, mirroring the gym-board style:

```
METCON — [AREA/GOAL]

WARM UP (x3 rounds)
- ...
- ...

EMOM x[N] (activation)
1) ...
2) ...

EMOM [N]' (main block)
1) ...
2) ...
3) ...
4) ...
5) REST

AMRAP [N]' (finisher) — optional
- ...
- ...
```

After the workout table, add a brief note (2-3 lines) with suggested weight/intensity (pulled from `equipment.md`) and which exercises are with or without kettlebell.

## Interaction notes

- If the user doesn't specify body area or duration, briefly ask before generating the full workout (area: legs/upper body/full body; approximate duration).
- If the user asks for progression from a previous workout (more reps, more rounds, less rest), scale it proportionally without changing the base structure.
- If the user mentions new equipment (sandbag, macebell, a second or different-weight kettlebell), update `references/equipment.md` first, then incorporate it into future rotations — no need to rewrite this file.