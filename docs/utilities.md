# Utilities

## Rate Functions

Rate functions control the speed of an animation over its `run_time`. They take a time proportion `t` (from 0 to 1) and return an alpha value (usually 0 to 1) representing the animation's progress. They are passed to `play` via the `rate_func` argument.

## `smooth`

**Purpose**: The default rate function. Starts slow, speeds up in the middle, and ends slow.
**When to Use**: For most natural-looking movements.

## `linear`

**Purpose**: A constant speed throughout the animation.
**When to Use**: For mechanical or uniform processes.

## `rush_into`

**Purpose**: Starts fast and slows down at the end.
**When to Use**: For objects quickly arriving at a destination.

## `rush_from`

**Purpose**: Starts slow and speeds up at the end.
**When to Use**: For objects quickly departing from a location.

## `there_and_back`

**Purpose**: Animates forward for the first half of the duration and backward for the second half.
**When to Use**: For "wiggling" or "bouncing" effects, like in the `Indicate` animation.