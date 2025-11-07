# Common Patterns

## Animating with `.animate`

For simple transformations like moving, scaling, or color-changing, the `.animate` syntax is a powerful and readable shortcut. Instead of creating a `Transform` object manually, you call `.animate` on your mobject and then call the method you want to animate.

**How it works**: `my_mobject.animate.shift(UP)` creates a copy of `my_mobject`, applies `.shift(UP)` to the copy to create a `target`, and then generates a `MoveToTarget` animation from the original to the target.

**Example**:
```python
# Instead of this:
target_square = square.copy().shift(UP).set_color(BLUE)
self.play(Transform(square, target_square))

# You can do this:
self.play(square.animate.shift(UP).set_color(BLUE))
```

## Positioning Mobjects

Mobjects have several methods for precise positioning relative to other objects or the screen.

- `.move_to(point_or_mobject)`: Moves the mobject's center to a specific point or another mobject's center.
- `.next_to(other_mobject, direction, buff=0.25)`: Places the mobject next to another one in a given direction (e.g., `UP`, `RIGHT`).
- `.to_edge(edge, buff=0.5)`: Aligns the mobject to an edge of the screen (e.g., `UP`, `LEFT`).
- `.to_corner(corner, buff=0.5)`: Aligns the mobject to a corner of the screen (e.g., `UL`, `DR`).
- `.center()`: Moves the mobject to the center of the screen, `(0, 0, 0)`.

## Using Updaters with `ValueTracker`

For animations that need to run continuously or respond to a changing value, updaters are essential. An updater is a function that is called on every frame.

**Pattern**:
1.  Create a `ValueTracker` to hold the value you want to animate.
2.  Create a mobject whose properties depend on this value.
3.  Add an updater function to the mobject using `.add_updater()`. The function should read the value from the `ValueTracker` and update the mobject.
4.  Animate the `ValueTracker` using `self.play(my_tracker.animate.set_value(new_value))`.

**Example**:
```python
# Animate a line rotating based on a value
angle_tracker = ValueTracker(0)
line = Line(ORIGIN, RIGHT * 2)
line.add_updater(
    lambda m: m.set_angle(angle_tracker.get_value())
)
self.add(line)
self.play(angle_tracker.animate.set_value(PI)) # Rotates 180 degrees
```

## Common Gotchas

- **`Transform` vs. `ReplacementTransform`**: `Transform` modifies the original mobject. `ReplacementTransform` swaps it for the target. If your object "disappears" after a transform, you probably wanted `ReplacementTransform`.
- **Modifying an object vs. Animating it**: Calling a method like `my_mobject.shift(UP)` teleports the object instantly. To animate the change, you must wrap it in an animation, like `self.play(my_mobject.animate.shift(UP))`.
- **Forgetting to `add`**: If you want an object to be on screen before it is animated, you must first `self.add(my_mobject)` and then `self.wait()` or `self.play(...)`.