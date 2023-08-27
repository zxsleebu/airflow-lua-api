# cheat

{{ define_function("cheat", "is_menu_visible", [], "boolean") }}
---
{{ define_function("cheat", "add_callback", [
    ["event", "string", "Event name. Look [here](/events/) for event list"],
    ["callback", "function", "Callback function"]
]) }}
---
{{ define_function("cheat", "log", [
    ["text", "string", "Text to print to console"]
]) }}
---
{{ define_function("cheat", "color_log", [
    ["text", "string", "Text to print to console"],
    ["color", "color_t", "Color of the text"]
]) }}
---
{{ define_function("cheat", "screen_size", [], "vec2_t") }}
