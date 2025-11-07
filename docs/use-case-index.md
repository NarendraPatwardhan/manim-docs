# Index by Use Case

**"I want to..."**

*   **...draw a shape or path on screen.**
    *   Use `self.play(Create(my_shape))`
*   **...write text or a formula.**
    *   Use `self.play(Write(my_text))`
*   **...make an object appear instantly.**
    *   Use `self.add(my_object)`
*   **...make an object fade in or out.**
    *   Use `self.play(FadeIn(my_object))` or `self.play(FadeOut(my_object))`
*   **...move an object.**
    *   Use `self.play(my_object.animate.shift(direction))`
    *   Use `self.play(my_object.animate.move_to(new_location))`
*   **...change an object's color.**
    *   Use `self.play(my_object.animate.set_color(NEW_COLOR))`
*   **...scale an object.**
    *   Use `self.play(my_object.animate.scale(2))`
*   **...morph one shape into another.**
    *   Use `self.play(Transform(shape1, shape2))` if `shape1` should become `shape2`.
    *   Use `self.play(ReplacementTransform(shape1, shape2))` if `shape1` should be replaced by `shape2`.
*   **...run multiple animations at the same time.**
    *   Put them in the same `play` call: `self.play(Animation1(...), Animation2(...))`
*   **...run animations one after the other.**
    *   Put them in separate `play` calls: `self.play(Animation1(...))`, `self.play(Animation2(...))`
    *   Or use `Succession`: `self.play(Succession(Animation1(...), Animation2(...)))`
*   **...create a "ripple" effect for a group of objects.**
    *   Use `LaggedStart`: `self.play(LaggedStart(*(Create(obj) for obj in my_group)))`
*   **...draw attention to an object.**
    *   Use `self.play(Indicate(my_object))` for a quick bounce and color change.
    *   Use `self.play(Flash(my_object))` for a burst of lines.
*   **...connect an animation to a changing number.**
    *   Use a `ValueTracker` and an updater function.
*   **...pause the animation.**
    *   Use `self.wait(duration_in_seconds)`