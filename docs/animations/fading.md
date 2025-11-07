# Fading

These animations control the visibility of mobjects.

## `FadeIn`

**Purpose**: Makes a mobject appear by smoothly increasing its opacity.

**Common Use Cases**:
- Introducing a new object to the scene without a drawing animation.
- Making an object appear from a specific direction or scale.

**When to Use**: When you want an object to simply "appear" rather than be drawn.

### Complete Signature
```python
FadeIn(
    mobject: Mobject,
    *,
    shift: np.ndarray = ORIGIN,
    scale: float = 1.0,
    run_time: float = 1.0,
    **kwargs
) -> Animation
```

### Key Parameters
- `mobject` (Mobject): The mobject to fade in.
- `shift` (Vect3): A vector indicating the direction from which the mobject should appear (e.g., `UP`, `DOWN`).
- `scale` (float): The starting scale factor. A value less than 1 makes it grow as it fades in.

**Related**: `FadeOut`, `Create`

---

## `FadeOut`

**Purpose**: Makes a mobject disappear by smoothly decreasing its opacity.

**Common Use Cases**:
- Removing an object from the scene.
- Clearing space for new objects.

**When to Use**: When you want an object to simply "disappear".

### Complete Signature
```python
FadeOut(
    mobject: Mobject,
    *,
    shift: np.ndarray = ORIGIN,
    scale: float = 1.0,
    run_time: float = 1.0,
    **kwargs
) -> Animation
```

### Key Parameters
- `mobject` (Mobject): The mobject to fade out.
- `shift` (Vect3): A vector indicating the direction towards which the mobject should move as it disappears.
- `scale` (float): The final scale factor. A value less than 1 makes it shrink as it fades out.

**Related**: `FadeIn`, `Uncreate`