# entity

<!-- {{ define_function("entity", "get", [
    ["idx_or_user_id", "number", "Index or User ID of the player"],
    ["is_user_id", "boolean", "Defaults to `false`. Is `value` a user ID", true]
], "entity") }} -->

{{ define_function("entity", "local_player", [], "entity") }}
---
### **get_players**
=== "Return style"
    {{ get_function_table_and_definition("entity", "get_players", [
        ["enemies_only",    "boolean", "Whether to return only enemies"],
        ["include_dormant", "boolean", "Whether to include dormant entities or not"]
    ], "entity[]") }}

=== "Callback style"
    {{ get_function_table_and_definition("entity", "get_players", [
        ["enemies_only",    "boolean", "Whether to return only enemies"],
        ["include_dormant", "boolean", "Whether to include dormant entities or not"],
        ["callback", "function", "Callback function, that receives " + format_lua_type("entity") + " as an argument"]
    ]) }}
    ```lua linenums="1"
    entitylist.get_entities(false, false, function(entity)
        print(entity:get_origin().x, entity:get_origin().y, entity:get_origin().z)
    end)
    ```
