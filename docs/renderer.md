# renderer
## Functions

<!--
{{ define_function("render", "setup_texture", [
    ["filename", "string", "Path to the texture"],
], "texture_t") }}
!!! warning
    If you specify a texture that does not exist, return value will be `nil`.
??? example
    ``` lua linenums="1"
    local texture = render.setup_texture("C:/Nixware/example.png")
    register_callback("paint", function()
        render.texture(texture, vec2_t.new(100, 100), vec2_t.new(200, 200))
    end)
    ```
---
-->
{{ define_function("renderer", "create_font", [
    ["filename", "string", "Path to the font"],
    ["size",     "number", "Font size"],
    ["flags",    "number", "Font flags"],
], "font_t") }}
!!! warning
    If you specify a font that does not exist, return value will be `nil`.
??? info "Font flags"
    ``` lua
    1   -- Disable hinting. This generally generates 'blurrier' bitmap glyphs when the glyph are rendered in any of the anti-aliased modes.
    2   -- Disable auto-hinter.
    4   -- Indicates that the auto-hinter is preferred over the font's native hinter.ImGuiFreeTypeBuilderFlags_LightHinting = 1 << 3,   // A lighter hinting    algorithm for gray-level modes. Many generated glyphs are fuzzier but better resemble their original shape. This is achieved by snapping glyphs to the pixel   grid only vertically (Y-axis), as is done by Microsoft's ClearType and Adobe's proprietary font renderer. This preserves inter-glyph spacing in horizontal    text.
    8   -- Strong hinting algorithm that should only be used for monochrome output.
    16  -- Styling: Should we artificially embolden the font?
    32  -- Styling: Should we slant the font, emulating italic style?
    64  -- Disable anti-aliasing. Combine this with MonoHinting for best results!
    ```
<!-- ??? example
    ``` lua linenums="1"
    local font = render.setup_font("C:/Windows/Fonts/verdana.ttf", 32, 0)
    register_callback("paint", function()
        render.text("hello from nixware lua api!", font, vec2_t.new(100, 100), color_t.new(1, 1, 1, 1))
    end)
    ``` -->
---
{{ define_function("renderer", "text_size", [
    ["text", "string", "Text size of which will be calculated"],
    ["font", "font_t", "Font object"],
    ["size", "number", "Font size", true],
], "vec2_t") }}
!!! warning
    If you specify a font that does not exist, return value will be `nil`.
---
<!-- {{ define_function("render", "world_to_screen", [
    ["pos", "vec3_t", "World position"],
], "vec3_t") }}
!!! warning
    If world position is not on the screen, return value will be `nil`.
??? example
    ``` lua linenums="1"
    register_callback("paint", function()
        local w2s = render.world_to_screen(vec3_t.new(0, 0, 0))
        if w2s then
            render.circle_fade(w2s, 20, color_t.new(1, 0.25, 0.25, 0.5), color_t.new(0, 0, 0, 1))
        end
    end)
    ```
--- -->
## Draw functions
<!--
{{ define_function("render", "texture", [
    ["texture",     "texture_t",    "Texture object"],
    ["from",        "vec2_t",       "Start position of the texture"],
    ["to",          "vec2_t",       "End position of the texture"],
    ["color",       "color_t",      "Texture color", true],
]) }}
---
-->
{{ define_function("renderer", "text", [
    ["pos",     "vec2_t",  "Position of where text will be rendered"],
    ["text",    "string",  "Text to render"],
    ["font",    "font_t",  "Font object, or `0` = default font, or `1` = pixel font"],
    ["color",   "color_t", "Text color", true],
    ["size",    "number",  "Text size", true],
]) }}
<!-- ---
{{ define_function("render", "line", [
    ["from",      "vec2_t",  "Start position of the line"],
    ["to",        "vec2_t",  "End position of the line"],
    ["color",     "color_t", "Color of the line"],
    ["thickness", "number",  "Thickness of the line", true],
]) }} -->
---
{{ define_function("renderer", "rect", [
    ["from",     "vec2_t",  "Start position of the rectangle"],
    ["to",       "vec2_t",  "End position of the rectangle"],
    ["color",    "color_t", "Color of the rectangle"],
    ["rounding", "number",  "Rounding of the rectangle"],
    ["corner_flags",  "number",  "[Corner flags](#corner-flags)"],
]) }}
---
{{ define_function("renderer", "filled_rect", [
    ["from",     "vec2_t",  "Start position of a rectangle"],
    ["to",       "vec2_t",  "End position of the rectangle"],
    ["color",    "color_t", "Color of the rectangle"],
    ["rounding", "number",  "Rounding of the rectangle"],
    ["corner_flags",  "number",  "[Corner flags](#corner-flags)"],
]) }}
---
{{ define_function("renderer", "filled_rect_gradient", [
    ["from",          "vec2_t",  "Start position of a rectangle"],
    ["to",            "vec2_t",  "Font object"],
    ["col_top_left",  "color_t", "Color of the top left corner"],
    ["col_top_right", "color_t", "Color of the top right corner"],
    ["col_bot_right", "color_t", "Color of the bottom right corner"],
    ["col_bot_left",  "color_t", "Color of the bottom left corner"],
    ["rounding",      "number",  "Rounding of the rectangle"],
    ["corner_flags",  "number",  "[Corner flags](#corner-flags)"],
]) }}
<!-- ["rounding",    "number",   "Rounding of the rectangle", true], -->
---
{{ define_function("renderer", "circle", [
    ["pos",      "vec2_t",  "Position of the circle"],
    ["color",    "color_t", "Color of the circle"],
    ["radius",   "number",  "Radius of the circle"],
    ["segments", "number",  "Count of the circle segments"],
]) }}
<!-- ["thickness","number",  "Thickness of the circle", true], -->
---
{{ define_function("renderer", "filled_circle", [
    ["pos",      "vec2_t",  "Position of the circle"],
    ["color",    "color_t", "Color of the circle"],
    ["radius",   "number",  "Radius of the circle"],
    ["segments", "number",  "Count of the circle segments"],
]) }}
<!-- ---
{{ define_function("render", "circle_fade", [
    ["pos",         "vec2_t",   "Position of the circle"],
    ["radius",      "number",   "Radius of the circle"],
    ["color_in",    "color_t",  "Color of the center of the circle"],
    ["color_out",   "color_t",  "Color of the edge of the circle"],
]) }}
---
{{ define_function("render", "filled_polygon", [
    ["points",  "vec2_t[]", "Array of screen positions"],
    ["color",   "color_t",  "Color of the polygon"],
]) }}
---
{{ define_function("render", "poly_line", [
    ["points",  "vec2_t[]", "Array of screen positions"],
    ["color",   "color_t",  "Color of the polyline"],
]) }} -->

## Corner flags

``` lua
16 -- top left
32 -- top right
64 -- bottom left
128 -- bottom right
240 -- every corner
48 -- top
192 -- bottom
80 -- left
160 -- right  
```


<!-- ``` lua linenums="1"
for i = 10, 60 do
    renderer.setup_font("C:/windows/fonts/tahomabd.ttf", i, 0)
end
register_callback("paint", function()
    renderer.rect_filled(vec2_t.new(100, 100), vec2_t.new(200, 200), color_t.new(1, 1, 1, 1))
end)
``` -->

