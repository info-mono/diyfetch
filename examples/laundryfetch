#!/bin/sh

# Prepare ------------------------------------------------------------------------------------------

main_color=15

info=$(gum style --border normal --padding '0 1' --width 30 --italic --foreground "${main_color}" \
"USER:   ${USER}@$(hostname)
UPTIME: $(uptime -p | cut -c 4- | cut -d ',' -f -2)")

art=$(gum style --foreground "${main_color}" '▄▄▄▄▄▄▄
█▄█▄███
█▀  ▄▀█
█ ▄██ █
██▄▄▄██')

color=$(gum style '[0;90mﰨ   [0;91mﰨ   [0;92mﰨ   [0;93mﰨ   [0;94mﰨ   [0;95mﰨ   [0;96mﰨ   [0;97mﰨ [0m')


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


# Landscape layout
group_info_color=$(gum join --vertical --align center "${info}" "${color}")
print_test "$(gum join --horizontal --align center "${art}" '  ' "${group_info_color}")"

# Portrait layout
print_test "$(gum join --vertical --align center "${art}" '' "${group_info_color}")"

# Other layout
print_test "${group_info_color}"
print_test "${info}"

exit 1