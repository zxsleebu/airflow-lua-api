# cheat

{{ define_function("cheat", "is_menu_visible", [], "boolean") }}
---
{{ define_function("cheat", "add_callback", [
    ["name", "string", "Callback name. Look [here](/callbacks/) for callbacks list"],
    ["callback", "function", "Callback function"]
]) }}
---
{{ define_function("cheat", "add_event_callback", [
    ["event", "string", "Game event name."],
    ["callback", "function", "Callback function. Receives " + format_lua_type("event") + " in the first argument."]
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
---
{{ define_function("cheat", "get_username", [], "string") }}
---
{{ define_function("cheat", "get_build", [], "string") }}

