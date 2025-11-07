# Geometry

These are the fundamental shapes used in Manim.

## `Circle`

**Purpose**: Creates a circle.

**Common Use Cases**:
- Representing circular objects or areas.
- Used as a basis for other curved shapes.
- Highlighting a specific point.

**When to Use**: When you need a perfect circle. For ovals, use `Ellipse`.

### Complete Signature
```python
Circle(
    *,
    radius: float = 1.0,
    color: ManimColor = RED,
    fill_color: ManimColor = None,
    fill_opacity: float = 0.0,
    stroke_color: ManimColor = None,
    stroke_width: float = 4.0,
    stroke_opacity: float = 1.0,
    **kwargs
)
```

### Key Parameters
- `radius` (float): The radius of the circle. Default: `1.0`.
- `color` (ManimColor): A shorthand to set both `fill_color` and `stroke_color`. The default `RED` is a specific override for `Circle`.
- `fill_opacity` (float): The opacity of the circle's interior, from 0 (transparent) to 1 (opaque). Default: `0.0`.
- `stroke_width` (float): The thickness of the outline. Default: `4.0`.

**Inherits from**: `VMobject`

**Related**: `Dot`, `Ellipse`, `Arc`

---

## `Square`

**Purpose**: Creates a square.

**Common Use Cases**:
- Representing boxes, grids, or nodes.
- A fundamental building block for more complex diagrams.

**When to Use**: When you need a rectangle with equal sides.

### Complete Signature
```python
Square(
    *,
    side_length: float = 2.0,
    color: ManimColor = DEFAULT_MOBJECT_COLOR,
    fill_color: ManimColor = None,
    fill_opacity: float = 0.0,
    stroke_color: ManimColor = None,
    stroke_width: float = 4.0,
    stroke_opacity: float = 1.0,
    **kwargs
)
```

### Key Parameters
- `side_length` (float): The length of each side of the square. Default: `2.0`.

**Inherits from**: `Rectangle`

**Related**: `Rectangle`, `Polygon`

---

## `Rectangle`

**Purpose**: Creates a rectangle.

**Common Use Cases**:
- Framing content (`SurroundingRectangle`).
- Creating UI elements like buttons or panels.
- Representing rectangular areas in diagrams.

**When to Use**: For any four-sided shape with 90-degree angles where width and height may differ.

### Complete Signature
```python
Rectangle(
    *,
    width: float = 4.0,
    height: float = 2.0,
    color: ManimColor = DEFAULT_MOBJECT_COLOR,
    fill_color: ManimColor = None,
    fill_opacity: float = 0.0,
    stroke_color: ManimColor = None,
    stroke_width: float = 4.0,
    stroke_opacity: float = 1.0,
    **kwargs
)
```

### Key Parameters
- `width` (float): The width of the rectangle. Default: `4.0`.
- `height` (float): The height of the rectangle. Default: `2.0`.

**Inherits from**: `Polygon`

**Related**: `Square`, `SurroundingRectangle`

---

## `Line`

**Purpose**: Creates a straight or curved line segment between two points.

**Common Use Cases**:
- Connecting two objects.
- Forming the axes of a graph.
- Drawing diagrams and paths.

**When to Use**: To draw a connection between a start and end point.

### Complete Signature
```python
Line(
    start: Vect3 | Mobject = LEFT,
    end: Vect3 | Mobject = RIGHT,
    *,
    buff: float = 0.0,
    path_arc: float = 0.0,
    stroke_color: ManimColor = DEFAULT_VMOBJECT_STROKE_COLOR,
    stroke_width: float = 4.0,
    **kwargs
)
```

### Key Parameters
- `start` (Vect3 | Mobject): The starting point of the line. Can be a coordinate (like `LEFT` or `[1, 2, 0]`) or a mobject (connects to its center).
- `end` (Vect3 | Mobject): The ending point of the line.
- `buff` (float): Shortens the line at both ends by this amount.
- `path_arc` (float): The angle in radians to curve the line. `0` creates a straight line. A positive value curves counter-clockwise.

### Key Methods
```python
get_vector(self) -> Vect3
```
Returns the vector from the start to the end of the line.

```python
get_angle(self) -> float
```
Returns the angle of the line with respect to the positive x-axis.

**Inherits from**: `VMobject`

**Related**: `Arrow`, `DashedLine`, `Arc`

---

## `Arrow`

**Purpose**: Creates a line with a triangular tip at the end.

**Common Use Cases**:
- Indicating direction or flow (vectors).
- Pointing from one object to another.
- Annotating diagrams.

**When to Use**: When you need a `Line` that shows direction.

### Complete Signature
```python
Arrow(
    start: Vect3 | Mobject = LEFT,
    end: Vect3 | Mobject = RIGHT,
    *,
    buff: float = MED_SMALL_BUFF,
    thickness: float = 3.0,
    tip_width_ratio: float = 5,
    **kwargs
)
```

### Key Parameters
- `start` (Vect3 | Mobject): The starting point of the arrow's shaft.
- `end` (Vect3 | Mobject): The point the arrow's tip points to.
- `buff` (float): Buffer space between the start/end points and the actual start/end of the arrow.
- `thickness` (float): Controls the width of the arrow's shaft.

**Inherits from**: `Line`

**Related**: `Line`, `Vector`

---

## `Dot`

**Purpose**: Creates a small, filled circle.

**Common Use Cases**:
- Marking points on a graph or diagram.
- Representing particles or discrete items.

**When to Use**: For a small, solid circular marker. For a hollow circle, use `Circle`.

### Complete Signature
```python
Dot(
    point: Vect3 = ORIGIN,
    *,
    radius: float = DEFAULT_DOT_RADIUS,
    color: ManimColor = DEFAULT_MOBJECT_COLOR,
    **kwargs
)
```

### Key Parameters
- `point` (Vect3): The center of the dot.
- `radius` (float): The radius of the dot.
- `color` (ManimColor): The fill color of the dot.

**Inherits from**: `Circle`

**Related**: `Circle`, `SmallDot`