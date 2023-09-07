# event

{{ define_function("event", "get_bool", [
    ["key_name", "string", "Key name"],
], "boolean", True) }}
---
{{ define_function("event", "get_int", [
    ["key_name", "string", "Key name"],
], "number", True) }}
---
{{ define_function("event", "get_float", [
    ["key_name", "string", "Key name"],
], "number", True) }}
---
{{ define_function("event", "get_string", [
    ["key_name", "string", "Key name"],
], "string", True) }}