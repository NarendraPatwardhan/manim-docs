# Transformation

These animations morph one mobject into another.

## `Transform`

**Purpose**: Smoothly transforms one mobject into the shape, position, and style of a target mobject.

**Common Use Cases**:
- Morphing one shape into another (e.g., a circle into a square).
- Moving, scaling, and rotating a mobject to a new state in one smooth animation.

**When to Use**: When you want to show a continuous change from a starting state to an ending state for the *same conceptual object*. The original mobject is modified in place.

### Complete Signature
```python
Transform(
    mobject: Mobject,
    target_mobject: Mobject,
    *,
    run_time: float = 1.0,
    path_arc: float = 0.0,
    **kwargs
) -> Animation
```

### Key Parameters
- `mobject` (Mobject): The mobject to be transformed.
- `target_mobject` (Mobject): A mobject defining the target state. The `mobject` will be modified to match this target.
- `path_arc` (float): Angle in radians for arcing the path of the transformation.

**Related**: `ReplacementTransform`, `ApplyMethod`

---

## `ReplacementTransform`

**Purpose**: Transforms a starting mobject into a target mobject, then removes the starting mobject and adds the target mobject to the scene.

**Common Use Cases**:
- Showing an object being replaced by a new one (e.g., `f(x)` becomes `f'(x)`).
- Morphing between two distinct objects where you want the final object to persist on screen.

**When to Use**:
- Use `ReplacementTransform` when the conceptual object changes (e.g., a variable `x` is replaced by the number `3`).
- Use `Transform` when the conceptual object remains the same but its properties change (e.g., a square moves and changes color).

### Complete Signature
```python
ReplacementTransform(
    mobject: Mobject,
    target_mobject: Mobject,
    *,
    run_time: float = 1.0,
    **kwargs
) -> Animation
```

**Inherits from**: `Transform`

**Related**: `Transform`