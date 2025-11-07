# Creation

These animations are for bringing mobjects onto the screen.

## `Create` / `ShowCreation`

**Purpose**: Draws a `VMobject` onto the screen, as if with a pen.

**Common Use Cases**:
- Drawing shapes like circles, squares, and lines.
- Revealing graphs and paths.

**When to Use**: When you want to show the "drawing" of a vector-based object. For text or formulas, `Write` is usually better.

### Complete Signature
```python
Create(
    mobject: Mobject,
    *,
    run_time: float = 1.0,
    lag_ratio: float = 1.0,
    **kwargs
) -> Animation
```

### Key Parameters
- `mobject` (Mobject): The `VMobject` to be created.
- `lag_ratio` (float): If the mobject has parts, this controls the delay between drawing each part. A `lag_ratio` of `1.0` means parts are drawn sequentially. A `lag_ratio` of `0.0` means they are drawn simultaneously.

**Related**: `Write`, `DrawBorderThenFill`, `Uncreate` (reverse animation)

---

## `Write`

**Purpose**: Animates the appearance of text or mathematical formulas in a way that looks like writing.

**Common Use Cases**:
- Revealing `Text`, `Tex`, or `MathTex` mobjects.

**When to Use**: This is the standard animation for making text appear.

### Complete Signature
```python
Write(
    vmobject: VMobject,
    *,
    run_time: float = -1,
    lag_ratio: float = -1,
    rate_func: Callable = linear,
    **kwargs
) -> Animation
```

### Key Parameters
- `vmobject` (`Text` or `Tex`): The text mobject to write.
- `run_time` (float): If `-1`, the run time is automatically calculated based on the number of characters.
- `lag_ratio` (float): If `-1`, the lag ratio is automatically calculated.

**Inherits from**: `DrawBorderThenFill`

**Related**: `Create`, `AddTextWordByWord`