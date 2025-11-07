# Core Concepts

## What is a Mobject?

A **Mobject** (short for Mathematical Object) is the fundamental building block for everything you see on screen. Shapes, lines, text, and even complex graphs are all types of Mobjects.

*   They have properties you can change, like `color`, `opacity`, position, and scale.
*   They can be combined into groups using `Group` or `VGroup`.
*   Most mobjects you'll use are `VMobject`s (Vectorized Mobjects), which are defined by points and curves. This means they can be scaled infinitely without losing quality and can be smoothly transformed.

## What is an Animation?

An **Animation** is a command that tells a `Mobject` how to change over a period of time. You don't create an animation and then run it; instead, you pass an `Animation` instance directly into the `Scene.play()` method.

*   Examples include `Create` (to draw a mobject), `Transform` (to morph one mobject into another), and `FadeIn` (to make a mobject appear).
*   Animations have a default `run_time` of 1 second, which can be overridden in `self.play(..., run_time=2)`.
*   Multiple animations can be played simultaneously by passing them all into the same `self.play()` call.

## What is a Scene?

A **Scene** is the canvas and timeline for your animation. Your script will consist of one or more classes that inherit from `Scene`.

*   The main logic of your animation is written in the `construct` method.
*   The `Scene` object keeps track of all mobjects that are currently on screen.
*   It provides the essential methods for controlling the animation timeline: `play()`, `wait()`, `add()`, and `remove()`.

## How They Work Together

You create `Mobject`s, add them to the `Scene`, and then use `Animation`s inside `self.play()` to bring them to life. The `Scene` orchestrates the rendering of each frame as the animations progress.