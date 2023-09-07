# globals

{{ get_arguments_table([
    ["curtime",                 "number",           "Current server time in seconds"],
    ["realtime",                "number",           "Current local time in seconds"],
    ["frametime",               "number",           "Time that was used to render a last game frame in seconds"],
    ["framecount",              "number",           "Total rendered frames count"],
    ["absoluteframetime",       "number",           "Time that was used to render a last game frame in seconds"],
    ["tickcount",               "number",           "Count of ticks that server has handled"],
    ["interval_per_tick",       "number",           "Duration of a tick in seconds"],
    ["interpolation_amount",    "number",           "Amount of interpolation"],
    ["max_clients",             "number",           "Maximum number of players allowed on the server"],
]) }}

<!--
["choked_commands",         "number",           "Count of choked commands"],
["command_ack",             "number",           "Last command that server has been acknowledged of"],
["last_outgoing_command",   "number",           "Number of last command sequence number acknowledged by server"],
["last_command_ack",        "number",           "Last valid received server tick"],
["send_packet",             "boolean",          "Is packet will be sent to the server (fake lag)"]
-->