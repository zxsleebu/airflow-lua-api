# config

## Functions

{{ define_function("config", "read", [
    ["key", "string", "Key to read"],
], "menu_element") }}

??? example
    ``` lua linenums="1"
    local hide_shots = config.read("binds.hide_shots.enable")
    cheat.log(hide_shots:get()) -- read the value
    hide_shots:set(true) -- set the value
    ```

---

## General infomation
To obtain vars enable developer mode in scripts tab, hover over element and you will see popup with the var.
![Information how to get var keys](/assets/scripts-general-information.png)