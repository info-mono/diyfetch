#!/bin/sh

# Prepare ------------------------------------------------------------------------------------------

main_color=9

clock=$(gum style --bold --italic --foreground 14 "$(date +%X | figlet -f slant)")

calendar=$(gum style --border thick --border-foreground "${main_color}" --padding '0 2' "
$(cal --color=always)")

info=$(gum style --border thick --border-foreground "${main_color}" --padding '0 1' "$(date)")


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
group_clock_info=$(gum join --vertical --align center "${clock}" "${info}")
print_test "$(gum join --horizontal --align center "${group_clock_info}" '  ' "${calendar}")"

# Portrait layout
print_test "$(gum join --vertical --align center "${clock}" "${calendar}" '' "${info}")"

# Other layout
print_test "${group_clock_info}"
print_test "${info}"

exit 1