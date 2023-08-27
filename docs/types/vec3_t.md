{{ get_arguments_table([
    ["x", "number"],
    ["y", "number"],
    ["z", "number"],
]) }}

{{ define_function("vec3", "length", [], "number", True) }}
---
{{ define_function("vec3", "distance_to", [
    ["vec", "vec3_t", "Vector to calculate distance to"]
], "number", True) }}
