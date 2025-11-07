# Grouping

## `VGroup`

**Purpose**: Groups multiple `VMobject`s together so they can be treated as a single unit.

**Common Use Cases**:
- Applying transformations (like `shift`, `scale`, `rotate`) to multiple objects at once.
- Animating a collection of objects with `LaggedStart`.
- Organizing complex scenes.

**When to Use**: Any time you have a collection of shapes, lines, or text that should logically stick together and be manipulated as one. For non-vectorized mobjects, use `Group`.

### Complete Signature
```python
VGroup(
    *vmobjects: VMobject,
    **kwargs
)
```

### Key Parameters
- `vmobjects` (VMobject): The `VMobject`s to include in the group.

### Key Methods
```python
arrange(self, direction: Vect3 = RIGHT, center: bool = True, **kwargs) -> Self
```
Arranges submobjects in a line along the specified `direction`.

**Inherits from**: `VMobject`, `Group`

**Related**: `Group`