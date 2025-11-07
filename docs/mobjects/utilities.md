# Utilities

## `ValueTracker`

**Purpose**: A container for a numerical value that can be animated and tracked. It is not visible on screen.

**Common Use Cases**:
- Driving animations that depend on a changing parameter.
- Creating updaters that link one mobject's properties to the value of the `ValueTracker`.
- Animating a number changing over time.

**When to Use**: When you need to animate a parameter itself, not just a mobject's properties. For example, to smoothly change the angle of a line in an animation, you would animate a `ValueTracker` for the angle and use an updater to apply that angle to the line.

### Complete Signature
```python
ValueTracker(
    value: float | complex | np.ndarray = 0,
    **kwargs
)
```

### Key Methods
```python
get_value(self) -> float | complex | np.ndarray
```
Returns the current value.

```python
set_value(self, value: float | complex | np.ndarray) -> Self
```
Sets the current value.

### Example Pattern
```python
# In your construct method:
value = ValueTracker(0)
line = Line(LEFT, RIGHT)
line.add_updater(lambda m: m.set_angle(value.get_value()))
self.play(value.animate.set_value(PI / 2))
```

**Inherits from**: `Mobject`