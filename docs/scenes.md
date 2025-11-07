# Scenes

This category covers the main environment in which animations are created and played.

## `Scene`

**Purpose**: The base class for all animations; it represents the screen and timeline.

**Common Use Cases**:
- Creating any Manim animation by subclassing it.
- Using its methods to control the flow of the animation.

**When to Use**: 
Always. Every animation script requires a class that inherits from `Scene`.

### Key Methods

```python
play(self, *proto_animations: Animation | _AnimationBuilder, run_time: float | None = None, rate_func: Callable[[float], float] | None = None, lag_ratio: float | None = None) -> None
```
Plays one or more animations. This is the primary method for creating movement and change in your scene. It waits for the animations to complete before proceeding.
- `proto_animations`: One or more animation objects (e.g., `Create(my_mobject)`, `my_mobject.animate.shift(UP)`).
- `run_time`: The duration of the animation in seconds. If not specified, it defaults to the `run_time` of the animation object, which is typically 1 second.
- `rate_func`: A function that controls the speed of the animation over its duration (e.g., `smooth`, `linear`).

```python
wait(self, duration: float | None = None, stop_condition: Callable[[], bool] | None = None) -> None
```
Pauses the scene for a specified duration.
- `duration`: Time to wait in seconds. Defaults to `1.0`.

```python
add(self, *mobjects: Mobject) -> None
```
Adds one or more mobjects to the scene, making them visible in subsequent frames. Mobjects added this way are static until animated.

```python
remove(self, *mobjects: Mobject) -> None
```
Removes one or more mobjects from the scene, making them invisible.