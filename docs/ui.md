# ui

{{ define_function("ui", "add_checkbox", [
    ["name", "string", "Name of the checkbox"]
], "menu_element") }}

??? example
    ``` lua linenums="1"
    local check_box = ui.add_checkbox("my checkbox!")
    local check_box_enabled = check_box:get() -- get value of checkbox 
    if check_box_enabled then
        cheat.log(tostring(check_box_enabled))
    end

    check_box:set(true) -- set value of checkbox to true
    ```

---

{{ define_function("ui", "add_slider", [
    ["name", "string", "Name of the slider"],
    ["min", "number", "Minimum value of the slider"],
    ["max", "number", "Maximum value of the slider"],
], "menu_element") }}


??? example
    ``` lua linenums="1"
    local slider = ui.add_slider("my slider!", 0, 100)
    local slider_value = slider:get() -- get value of slider
    if slider_value > 30 then
        cheat.log(tostring(slider_value))
    end

    slider:set(31) -- set value of slider to 31
    ```

---

{{ define_function("ui", "add_color_picker", [
    ["name", "string", "Name of the color picker"]
], "menu_element") }}

??? example
    ``` lua linenums="1"
    local color_picker = ui.add_color_picker("my color picker!")
    local color_picker_value = color_picker:get() -- get value of color picker
    if color_picker_value.r == 255 and color_picker_value.g == 255 
    and color_picker_value.b == 255 then
        cheat.log("color is white!")
    end
    
    color_picker:set(color.new(255, 255, 255)) -- set color picker to white
    ```


---

{{ define_function("ui", "add_combo_box", [
    ["name", "string", "Name of the combo box"],
    ["elements", "table", "Array of elements"]
], "menu_element") }}

---

{{ define_function("ui", "add_multi_combo", [
    ["name", "string", "Name of the multi combo"],
    ["elements", "table", "Array of elements"]
], "menu_element") }}
