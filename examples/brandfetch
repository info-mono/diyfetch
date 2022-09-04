#!/bin/sh

# Prepare ------------------------------------------------------------------------------------------

title=$(gum style --bold --foreground 12 "$(figlet DIYfetch)")
subtitle=$(gum style --italic --foreground 12 'The ultimate fetch tool template')
info=$(gum join --vertical --align center "${title}" "${subtitle}")

art=$(gum style --foreground "${main_color}" '          ,~-.
         (  ʻ )-.          ,~ʻ`-.
      ,~ʻ `  ʻ ) )       _(   _) )
     ( ( [97m.--.===.--.[0m    (  `    ʻ )
      `[97m.%%.[91m###[97m|[0m888[97m.[31m:[97m`.[0m   `-ʻ`~~=~ʻ
      [97m/%%/[91m####[97m|[0m8888[97m\[31m::[97m\[0m
     [97m|%%/[91m#####[97m|[0m88888[97m\[31m::[97m|[0m
     [97m|%%|[91m#####[97m|[0m88888[97m|[31m::[97m|[0m.,-.
     [97m\%%|[91m#####[97m|[0m88888[97m|[31m::[97m/[0m    )_
      [97m\%\[91m#####[97m|[0m88888[97m/[31m:[97m/[0m ( `ʻ  )
       [97m\%\[91m####[97m|[0m8888[97m/[31m:[97m/[0m(  ,  -ʻ`-.
   ,~-. [97m`%\[91m###[97m|[0m888[97m/[31m:[97mʻ[0m(  (     ʻ) )
  (  ) )_ [97m`\[93m__[97m|[93m__[97m/ʻ[0m   `~-~=--~~=ʻ
 ( ` ʻ)  ) [93m[VVVVV][0m
(_(_.~~~ʻ   [97m\|[93m_[97m|/[0m
            [93m[XXX][0m
            [93m`"""ʻ[0m')

color=$(gum style '[0;30m   [0;31m   [0;32m   [0;33m   [0;34m   [0;35m   [0;36m   [0;37m [0m
[0;90m   [0;91m   [0;92m   [0;93m   [0;94m   [0;95m   [0;96m   [0;97m [0m')


# Display ------------------------------------------------------------------------------------------

terminal_size=$(stty size)
terminal_height=${terminal_size% *}
terminal_width=${terminal_size#* }

prompt_height=${PROMPT_HEIGHT#-1}

print_test() {
	no_color=$(printf '%b' "${1}" | sed -e 's/\x1B\[[0-9;]*[JKmsu]//g')

	[ "$(printf '%s' "${no_color}" | wc --lines)" -gt $(( terminal_height - prompt_height )) ] && return 1
	[ "$(printf '%s' "${no_color}" | wc --max-line-length)" -gt "${terminal_width}" ] && return 1

	gum style --align center --width="${terminal_width}" "${1}" ''
	printf '%b' "\033[A"

	exit 0
}


# Landscape layout
group_info_color=$(gum join --vertical --align center "${info}" '' "${color}")
print_test "$(gum join --horizontal --align center "${art}" '  ' "${group_info_color}")"

# Portrait layout
print_test "$(gum join --vertical --align center "${art}" '' "${group_info_color}")"

# Other layout
print_test "${group_info_color}"
print_test "${info}"

exit 1