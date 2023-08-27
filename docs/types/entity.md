## Entity functions

{{ define_function("entity", "index", [], "number", True) }}
---
{{ define_function("entity", "is_bot", [], "boolean", True) }}
---
{{ define_function("entity", "is_alive", [], "boolean", True) }}
---
{{ define_function("entity", "dormant", [], "boolean", True) }}
---
{{ define_function("entity", "abs_angles", [], "vec3_t", True) }}
---
{{ define_function("entity", "abs_origin", [], "vec3_t", True) }}
---
{{ define_function("entity", "health", [], "number", True) }}
---
{{ define_function("entity", "is_armored", [], "boolean", True) }}
---
{{ define_function("entity", "flags", [], "number", True) }}
---
{{ define_function("entity", "effects", [], "number", True) }}
---
{{ define_function("entity", "eye_position", [], "vec3_t", True) }}
---
{{ define_function("entity", "ducking", [], "boolean", True) }}
---
{{ define_function("entity", "has_defuser", [], "boolean", True) }}
---
{{ define_function("entity", "team", [], "number", True) }}
---
{{ define_function("entity", "scoped", [], "boolean", True) }}
---
{{ define_function("entity", "max_speed", [], "number", True) }}
---
{{ define_function("entity", "move_state", [], "number", True) }}
---
{{ define_function("entity", "move_type", [], "number", True) }}
---
{{ define_function("entity", "velocity_modifier", [], "number", True) }}
---
{{ define_function("entity", "spotted", [], "boolean", True) }}

## Getting props

{{ define_function("entity", "prop", [
    ["table_name", "string", "Table name"],
    ["netvar_name", "string", "Netvar name"]
], "[`prop`](#prop)", True)}}

### prop_t

{{ define_function("prop", "get", [], "any", True, 4)}}
{{ define_function("prop", "set", [
    ["value", "any", "Value to set"]
], "", True, 4)}}

<!-- 
---
{{ define_function("entity", "is_weapon", [], "boolean", True) }}
---
{{ define_function("entity", "is_dormant", [], "boolean", True) }}
---
{{ define_function("entity", "get_index", [], "number", True) }}
---
{{ define_function("entity", "get_origin", [], "vec3_t", True) }}
Returns abs origin of the entity

---
{{ define_function("entity", "get_class_id", [], "number", True) }}
---
{{ define_function("entity", "get_class_name", [], "string", True) }}
---
## Getting FFI pointer
To get entity pointer you can use `entity[0]`  
Also you can use `entity[OFFSET]` to get the address pointing to specified offset of the entity
Hexadecimal and decimal number are both supported
!!! example
    This example will print money of all players
    ```lua linenums="1"
    entitylist.get_entities("CCSPlayer", false, function(entity)
        local origin = entity:get_origin()
        local origin2 = render.world_to_screen(origin)
        local money = ffi.cast("int*", entity[0x117B8])[0] --m_iAccount: 0x117B8

        if origin2 ~= nil then
            render.text(tostring(money), 0, origin2)
        end
    end)
    ``` -->
