# Quick Reference

## Core Components Overview

Manim animations are built from three fundamental components:

*   **`Mobject`**: The visual objects that appear on screen (e.g., shapes, text, graphs).
*   **`Animation`**: Instructions for how `Mobject`s should change over time (e.g., appear, transform, move).
*   **`Scene`**: The canvas where `Mobject`s are placed and `Animation`s are played out.

## Most Important Classes by Category

*   **Scenes**: `Scene`
*   **Mobjects (Shapes)**: `Circle`, `Square`, `Line`, `Arrow`, `Dot`, `Polygon`
*   **Mobjects (Text & Math)**: `Text`, `Tex`, `MathTex`
*   **Mobjects (Grouping)**: `VGroup`
*   **Animations (Creation)**: `Create`, `Write`, `DrawBorderThenFill`
*   **Animations (Transformation)**: `Transform`, `ReplacementTransform`, `ApplyMethod`
*   **Animations (Visibility)**: `FadeIn`, `FadeOut`
*   **Animations (Composition)**: `AnimationGroup`, `Succession`, `LaggedStart`
*   **Utilities**: `ValueTracker`, rate functions (`smooth`, `linear`, `there_and_back`)

## Typical Scene Structure

Almost every Manim script follows this structure. You create a class that inherits from `Scene` and define your animation sequence inside the `construct` method.

```python
from manimlib import *

class MyAwesomeAnimation(Scene):
    def construct(self):
        # 1. Create Mobjects
        circle = Circle()
        square = Square()

        # 2. Add Mobjects to the scene
        self.add(circle)

        # 3. Animate Mobjects using self.play()
        self.play(Transform(circle, square))
        self.play(FadeOut(square))

        # 4. Wait for a moment
        self.wait(1)
```

## Essential Workflow

1.  **Define a Scene**: Create a class inheriting from `Scene`.
2.  **Create Mobjects**: Inside `construct`, instantiate shapes, text, or other visual elements (`Circle`, `Text`, etc.).
3.  **Position Mobjects**: Use methods like `.move_to()`, `.next_to()`, and `.to_edge()` to place your mobjects.
4.  **Animate Mobjects**: Call `self.play()` and pass in one or more `Animation` classes (e.g., `self.play(Create(my_shape))`).
5.  **Use `.animate` for simplicity**: For simple property changes, use the `.animate` syntax: `self.play(my_mobject.animate.shift(UP))`.