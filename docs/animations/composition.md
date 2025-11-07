# Composition

These classes combine multiple animations to run them together.

## `AnimationGroup`

**Purpose**: Plays multiple animations simultaneously.

**Common Use Cases**:
- Fading in one object while another transforms.
- Creating a complex scene change involving many objects at once.

**When to Use**: Whenever you pass more than one animation into a single `self.play()` call, you are implicitly using `AnimationGroup`.

### Complete Signature
```python
AnimationGroup(
    *animations: Animation,
    *,
    run_time: float = -1,
    lag_ratio: float = 0.0,
    **kwargs
)
```

### Key Parameters
- `animations` (Animation): A list of animation objects to play together.
- `run_time` (float): The total run time for the group. If `-1`, it defaults to the longest animation's run time.
- `lag_ratio` (float): A delay factor between the start of each animation in the group. Default is `0.0` (all start together).

**Related**: `Succession`, `LaggedStart`

---

## `Succession`

**Purpose**: Plays multiple animations one after another in a single `play` call.

**Common Use Cases**:
- Creating a sequence of quick, related animations without multiple `play` calls.
- Chaining animations where the end of one is the start of the next.

**When to Use**: When you want to run animations back-to-back within the duration of a single `play` call. This is different from using multiple `play` calls, which pauses the script between each call.

### Complete Signature
```python
Succession(
    *animations: Animation,
    *,
    lag_ratio: float = 1.0,
    **kwargs
)
```

### Key Parameters
- `animations` (Animation): The animation objects to play in sequence.
- `lag_ratio` (float): Set to `1.0` by default, which means each animation starts only after the previous one has finished.

**Related**: `AnimationGroup`

---

## `LaggedStart`

**Purpose**: Plays a group of animations with a small delay between the start of each one.

**Common Use Cases**:
- Creating a "ripple" or "cascade" effect when animating the parts of a `VGroup`.
- Making the appearance of multiple objects feel more organic and less robotic.

**When to Use**: When you have many similar animations and want them to start one after another in quick succession, not all at once.

### Complete Signature
```python
LaggedStart(
    *animations: Animation,
    *,
    lag_ratio: float = 0.05,
    **kwargs
)
```

### Key Parameters
- `animations` (Animation): The animation objects to play.
- `lag_ratio` (float): The delay between the start times of consecutive animations, as a fraction of one animation's duration. Default is `0.05`.

**Related**: `AnimationGroup`