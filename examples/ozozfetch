#!/bin/sh

# Prepare ------------------------------------------------------------------------------------------

main_color=2

info=$(gum style "[38;5;${main_color}m [0;1;38;5;${main_color}m${USER}[0m@[1;38;5;${main_color}m$(hostname)[0m
├─ [38;5;${main_color}m [0m <your_model>
│  ├─ [38;5;${main_color}m [0m <your_cpu>
│  ├─ [38;5;${main_color}m﬙ [0m <your_gpu>
│  ├─ [38;5;${main_color}m [0m <your_disk>
│  ├─ [38;5;${main_color}m塞[0m <your_memory>
│  └─ [38;5;${main_color}m神[0m $(uptime -p | cut -c 4-)
└─ [38;5;${main_color}m [0m <your_os>
   ├─ [38;5;${main_color}m [0m <your_wm>
   ├─ [38;5;${main_color}m [0m <your_packages>
   ├─ [38;5;${main_color}m [0m <your_terminal>
   └─ [38;5;${main_color}m [0m $(basename "${SHELL}")")

art=$(gum style '       [32m&&[0m
      [32m&&&&&[0m
    [32m&&&[33m\/[32m& &&&[0m
   [32m&&[33m|,/  |/[32m& &&[0m
    [32m&&[33m/   /  /_[32m&  &&[0m
      [33m\  {  |_____/_[32m&[0m
      [33m{  / /          [32m&&&[0m
      [33m.`. \{___\________\/_\}[0m
       [33m\} \}\{       \[0m
       [33m}\{\{         \____[32m&[0m
      [33m\{\}\{           `[32m&[33m\[32m&&[0m
      [33m{{}             [32m&&[0m
[33m, -=-~{ .-^- _[0m
      [33m`.[0m')

color=$(gum style '[0;30m███[0;31m███[0;32m███[0;33m███[0;34m███[0;35m███[0;36m███[0;37m███[0m
[0;1;90m███[0;1;91m███[0;1;92m███[0;1;93m███[0;1;94m███[0;1;95m███[0;1;96m███[0;1;97m███[0m')


# Display ------------------------------------------------------------------------------------------

terminal_size=$(stty size)
terminal_height=${terminal_size% *}
terminal_width=${terminal_size#* }

prompt_height=${PROMPT_HEIGHT:-1}

print_test() {
	no_color=$(printf '%b' "${1}" | sed -e 's/\x1B\[[0-9;]*[JKmsu]//g')

	[ "$(printf '%s' "${no_color}" | wc --lines)" -gt $(( terminal_height - prompt_height )) ] && return 1
	[ "$(printf '%s' "${no_color}" | wc --max-line-length)" -gt "${terminal_width}" ] && return 1

	gum style --align center --width="${terminal_width}" "${1}" ''
	printf '%b' "\033[A"

	exit 0
}


# Default layout
group_info_color=$(gum join --vertical --align center "${info}" '' "${color}")
print_test "$(gum join --horizontal --align center "${art}" '    ' "${group_info_color}")"

# Other layout
print_test "$(gum join --horizontal --align center "${art}" '    ' "${info}")"
print_test "${group_info_color}"
print_test "${info}"

exit 1