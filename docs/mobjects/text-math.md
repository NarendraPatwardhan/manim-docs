# Text & Math

Manim provides powerful tools for rendering text and mathematical equations using either Pango (for plain text) or a full LaTeX installation (for math).

## `Text`

**Purpose**: Renders plain text strings quickly using the Pango library.

**Common Use Cases**:
- Displaying titles, labels, and sentences.
- Any text that does not require mathematical typesetting.

**When to Use**: Use for all non-mathematical text. It's much faster to render than `Tex`. For math, use `Tex` or `MathTex`.

### Complete Signature
```python
Text(
    text: str,
    *,
    font: str = "",
    font_size: int = 48,
    color: ManimColor = DEFAULT_MOBJECT_COLOR,
    **kwargs
)
```

### Key Parameters
- `text` (str): The string to be rendered.
- `font` (str): The font family to use (e.g., "Arial", "Consolas").
- `font_size` (int): The font size.
- `color` (ManimColor): The color of the text.

**Related**: `Tex`, `MathTex`

---

## `Tex` / `MathTex`

**Purpose**: Renders strings using a LaTeX installation, ideal for mathematical formulas and symbols.

**Common Use Cases**:
- Displaying complex mathematical equations.
- Using specific LaTeX symbols or packages.
- Typesetting text with the quality of LaTeX.

**When to Use**: When you need to display anything with mathematical notation. `MathTex` is a convenient alias that automatically wraps the string in a math environment.

### Comparison
- **`Text`**: Fast, uses Pango, for plain text. Cannot render LaTeX math.
- **`Tex` / `MathTex`**: Slower, requires a full LaTeX installation, for high-quality math and text typesetting.

### Complete Signature
```python
Tex(
    *tex_strings: str,
    font_size: int = 48,
    color: ManimColor = DEFAULT_MOBJECT_COLOR,
    isolate: Selector = [],
    tex_to_color_map: dict = {},
    **kwargs
)
```

### Key Parameters
- `tex_strings` (str): One or more strings to be rendered. They will be concatenated.
- `font_size` (int): The font size.
- `isolate` (list): A list of substrings to treat as separate mobjects, allowing them to be colored or animated independently.
- `tex_to_color_map` (dict): A dictionary mapping substrings to colors (e.g., `{"x": RED}`).

**Related**: `Text`, `SingleStringMathTex`