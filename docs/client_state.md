
# client_state

{{ get_arguments_table([
    ["choked_commands",         "number",           "Count of choked commands"],
    ["command_ack",             "number",           "Last command that server has been acknowledged of"],
    ["last_outgoing_command",   "number",           "Number of last command sequence number acknowledged by server"],
    ["last_command_ack",        "number",           "Last valid received server tick"],
]) }}

<!--
["choked_commands",         "number",           "Count of choked commands"],
["command_ack",             "number",           "Last command that server has been acknowledged of"],
["last_outgoing_command",   "number",           "Number of last command sequence number acknowledged by server"],
["last_command_ack",        "number",           "Last valid received server tick"],
["send_packet",             "boolean",          "Is packet will be sent to the server (fake lag)"]
-->