# Exercise Bank

This file is the exercise database used by the skill to build workouts. Each row describes: **Exercise | Tool | Movement Pattern | Main Muscles | Notes**

To add a new exercise, simply add a row to the relevant table following the same format. No need to touch the rest of the skill — it will automatically be picked up in future rotations.

---

## Kettlebell (see equipment.md for current weight/quantity)

| Exercise | Pattern | Main Muscles | Notes |
|---|---|---|---|
| Kettlebell Snatch | Vertical press / power | Shoulder, glutes, core, lats | Prioritize technique over speed; alternate arm each set |
| Kettlebell Clean | Power / transition | Forearm, lats, glutes | Base movement for the clean + press |
| Kettlebell Clean + Press | Vertical press | Shoulder, triceps, core, glutes | Combines hip power with an overhead push |
| Kettlebell Push Press | Vertical press | Shoulder, triceps, legs (drive) | Uses leg drive to assist the press |
| Kettlebell Strict Press | Vertical press | Shoulder, triceps, core (anti-lateral flexion) | No leg drive, slower and more controlled |
| Kettlebell High Pull | Vertical pull | Trapezius, rear delt, lats | Keep elbow high and close to the body |
| Kettlebell Swing (one-hand) | Hinge / hip | Glutes, hamstrings, core | Power comes from the hips, not the arm |
| Kettlebell Goblet Squat | Squat | Quads, glutes, core | Kettlebell held at chest with both hands |
| Kettlebell Front Squat (one-arm rack) | Squat | Quads, glutes, core (anti-rotation) | Unilateral version of the front squat |
| Kettlebell Deadlift | Hinge | Hamstrings, glutes, lower back | Build technique before adding speed |
| Kettlebell Single-leg Deadlift | Unilateral hinge | Hamstrings, glutes, core, balance | Requires more stability; reduce weight if needed |
| Kettlebell Deadlift + Push Up | Combo (hinge + horizontal press) | Hamstrings, glutes, chest, triceps | Deadlift the kettlebell off the floor, then push up with hands on the ground |
| Kettlebell Single-leg DL + Press | Combo (unilateral hinge + vertical press) | Hamstrings, glutes, shoulder, core | High-coordination move, start with low reps |
| Kettlebell Halo | Mobility / warm-up | Shoulder, core (rotation) | Great for warm-up, circle the kettlebell around the head |
| Kettlebell Pass-around | Mobility / warm-up | Shoulder, core | Pass the kettlebell hand to hand around the body or legs |
| Kettlebell Reverse Lunge (loaded) | Unilateral squat | Quads, glutes, hamstrings | Adds load to the basic lunge |
| Kettlebell Renegade Row (one-arm, alternating support) | Horizontal pull | Lats, rhomboids, core (anti-rotation) | Plank position, row the kettlebell while the other arm supports |

## Calisthenics / Bodyweight

| Exercise | Pattern | Main Muscles | Notes |
|---|---|---|---|
| Push Up (standard) | Horizontal press | Chest, triceps, front delt | Base movement of the push block |
| Diamond Push Up | Horizontal press | Triceps, chest (inner) | Hands close together, harder on triceps |
| Pull Up | Vertical pull | Lats, biceps, core | Requires a fixed bar |
| Inverted Row | Horizontal pull | Lats, rhomboids, biceps | More accessible alternative to the pull-up |
| Bodyweight Squat | Squat | Quads, glutes | Base movement of the leg block |
| Reverse Lunge (unloaded) | Unilateral squat | Quads, glutes, hamstrings | Good warm-up exercise |
| Switch Lunge (jump/switch lunge) | Unilateral squat / power | Quads, glutes, hamstrings | Adds a power and cardio component |
| Burpee | Full body / cardio | Chest, legs, shoulder, core | Classic conditioning exercise |
| Plank Burpee | Full body / cardio | Core, chest, legs | Burpee variant starting/ending in a plank |
| Mountain Climbers | Core / cardio | Core, shoulder, hip flexors | Good warm-up or finisher exercise |
| Jumping Jacks | Cardio / full body | Full body, cardiovascular | Classic warm-up move |
| Plank | Core (isometric) | Core, shoulder (stability) | Useful as a transition or finisher |

---

## How the skill uses this table

- **Warm-up**: calisthenics exercises tagged "mobility/warm-up" or low-impact "cardio" (halo, pass-around, jumping jacks, mountain climbers, unloaded squats).
- **Main EMOM/AMRAP blocks**: rotates between patterns (press, hinge, squat, pull, core/cardio) combining kettlebell and calisthenics based on the requested body area (upper body → prioritize press/pull/core; lower body → prioritize squat/hinge).
- **Finisher**: usually calisthenics only (cardio/full body pattern), kettlebell-free, to close out with accumulated fatigue.

## How to add new exercises

When you learn a new exercise, add a row to the relevant table (Kettlebell or Calisthenics) with:
1. Exercise name
2. Movement pattern (vertical/horizontal press, hinge, squat, vertical/horizontal pull, core, cardio/full body, mobility)
3. Main muscles worked
4. Execution notes or relevant coaching cues

No need to modify SKILL.md — the skill will read this table directly every time it builds a new workout.