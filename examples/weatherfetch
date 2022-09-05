#!/bin/sh

# Prepare ------------------------------------------------------------------------------------------

main_color=6

data=$(curl -fsLS "https://wttr.in/$*?format=j1")

location=$(curl -fsLS "https://wttr.in/$*?format=%l")
description=$(echo "${data}" | jq --raw-output .weather[0].hourly[7].weatherDesc[0].value)
humidity=$(echo "${data}" | jq --raw-output .weather[0].hourly[7].humidity)
temperature=$(echo "${data}" | jq --raw-output .weather[0].hourly[7].tempC)
temperature_feels=$(echo "${data}" | jq --raw-output .weather[0].hourly[7].FeelsLikeC)
wind_speed=$(echo "${data}" | jq --raw-output .weather[0].hourly[7].windspeedKmph)
precipitation=$(echo "${data}" | jq --raw-output .weather[0].hourly[7].precipMM)
pressure=$(echo "${data}" | jq --raw-output .weather[0].hourly[7].pressure)

case "$(echo "${data}" | jq --raw-output .weather[0].hourly[7].winddir16Point)" in
	N)   wind_direction='↓' ;;
	NNE) wind_direction='↓' ;;
	NE)  wind_direction='↙' ;;
	ENE) wind_direction='↙' ;;
	E)   wind_direction='←' ;;
	ESE) wind_direction='←' ;;
	SE)  wind_direction='↖' ;;
	SSE) wind_direction='↖' ;;
	S)   wind_direction='↑' ;;
	SSW) wind_direction='↑' ;;
	SW)  wind_direction='↗' ;;
	WSW) wind_direction='↗' ;;
	W)   wind_direction='→' ;;
	WNW) wind_direction='→' ;;
	NW)  wind_direction='↘' ;;
	NNW) wind_direction='↘' ;;
esac

info="[1;38;5;${main_color}m${location}[0m
----------------
[1;38;5;${main_color}mDescription:[0m ${description}
[1;38;5;${main_color}mHumidity:[0m ${humidity}%
[1;38;5;${main_color}mTemperature:[0m ${temperature}(${temperature_feels})°C
[1;38;5;${main_color}mWind:[0m${wind_direction} ${wind_speed}km/h
[1;38;5;${main_color}mPrecipitation:[0m ${precipitation}mm
[1;38;5;${main_color}mPressure:[0m ${pressure}hPa"

case "${description}" in
'Cloudy'*) art_raw='
[38;5;250m     .--.    [0m
[38;5;250m  .-(    ).  [0m
[38;5;250m (___.__)__) [0m
' ;;
'Fog'*) art_raw='
[38;5;251m _ - _ - _ - [0m
[38;5;251m  _ - _ - _  [0m
[38;5;251m _ - _ - _ - [0m
             ' ;;
'Heavy rain'*) art_raw='[38;5;240;1m     .-.     [0m
[38;5;240;1m    (   ).   [0m
[38;5;240;1m   (___(__)  [0m
[38;5;21;1m  ‚ʻ‚ʻ‚ʻ‚ʻ   [0m
[38;5;21;1m  ‚ʻ‚ʻ‚ʻ‚ʻ   [0m' ;;
'Heavy showers'*) art_raw='[38;5;226m _`/""[38;5;240;1m.-.    [0m
[38;5;226m  ,\_[38;5;240;1m(   ).  [0m
[38;5;226m   /[38;5;240;1m(___(__) [0m
[38;5;21;1m   ‚ʻ‚ʻ‚ʻ‚ʻ  [0m
[38;5;21;1m   ‚ʻ‚ʻ‚ʻ‚ʻ  [0m' ;;
'Heavy snow showers'*) art_raw='[38;5;226m _`/""[38;5;240;1m.-.    [0m
[38;5;226m  ,\_[38;5;240;1m(   ).  [0m
[38;5;226m   /[38;5;240;1m(___(__) [0m
[38;5;255;1m    * * * *  [0m
[38;5;255;1m   * * * *   [0m' ;;
'Heavy snow'*) art_raw='[38;5;240;1m     .-.     [0m
[38;5;240;1m    (   ).   [0m
[38;5;240;1m   (___(__)  [0m
[38;5;255;1m   * * * *   [0m
[38;5;255;1m  * * * *    [0m' ;;
'Light rain'*) art_raw='[38;5;250m     .-.     [0m
[38;5;250m    (   ).   [0m
[38;5;250m   (___(__)  [0m
[38;5;111m    ʻ ʻ ʻ ʻ  [0m
[38;5;111m   ʻ ʻ ʻ ʻ   [0m' ;;
'Light showers'*) art_raw='[38;5;226m _`/""[38;5;250m.-.    [0m
[38;5;226m  ,\_[38;5;250m(   ).  [0m
[38;5;226m   /[38;5;250m(___(__) [0m
[38;5;111m     ʻ ʻ ʻ ʻ [0m
[38;5;111m    ʻ ʻ ʻ ʻ  [0m' ;;
'Light sleet showers'*) art_raw='[38;5;226m _`/""[38;5;250m.-.    [0m
[38;5;226m  ,\_[38;5;250m(   ).  [0m
[38;5;226m   /[38;5;250m(___(__) [0m
[38;5;111m     ʻ [38;5;255m*[38;5;111m ʻ [38;5;255m* [0m
[38;5;255m    *[38;5;111m ʻ [38;5;255m*[38;5;111m ʻ  [0m' ;;
'Light sleet'*) art_raw='[38;5;250m     .-.     [0m
[38;5;250m    (   ).   [0m
[38;5;250m   (___(__)  [0m
[38;5;111m    ʻ [38;5;255m*[38;5;111m ʻ [38;5;255m*  [0m
[38;5;255m   *[38;5;111m ʻ [38;5;255m*[38;5;111m ʻ   [0m' ;;
'Light snow showers'*) art_raw='[38;5;226m _`/""[38;5;250m.-.    [0m
[38;5;226m  ,\_[38;5;250m(   ).  [0m
[38;5;226m   /[38;5;250m(___(__) [0m
[38;5;255m     *  *  * [0m
[38;5;255m    *  *  *  [0m' ;;
'Light snow'*) art_raw='[38;5;250m     .-.     [0m
[38;5;250m    (   ).   [0m
[38;5;250m   (___(__)  [0m
[38;5;255m    *  *  *  [0m
[38;5;255m   *  *  *   [0m' ;;
'Partly cloudy'*) art_raw='[38;5;226m   \  /[0m      
[38;5;226m _ /""[38;5;250m.-.    [0m
[38;5;226m   \_[38;5;250m(   ).  [0m
[38;5;226m   /[38;5;250m(___(__) [0m
             ' ;;
'Sunny'*) art_raw='[38;5;226m    \   /    [0m
[38;5;226m     .-.     [0m
[38;5;226m  ‒ (   ) ‒  [0m
[38;5;226m     `-᾿     [0m
[38;5;226m    /   \    [0m' ;;
'Thundery heavy rain'*) art_raw='[38;5;240;1m     .-.     [0m
[38;5;240;1m    (   ).   [0m
[38;5;240;1m   (___(__)  [0m
[38;5;21;1m  ‚ʻ[38;5;228;5m⚡[38;5;21;25mʻ‚[38;5;228;5m⚡[38;5;21;25m‚ʻ   [0m
[38;5;21;1m  ‚ʻ‚ʻ[38;5;228;5m⚡[38;5;21;25mʻ‚ʻ   [0m' ;;
'Thundery showers'*) art_raw='[38;5;226m _`/""[38;5;250m.-.    [0m
[38;5;226m  ,\_[38;5;250m(   ).  [0m
[38;5;226m   /[38;5;250m(___(__) [0m
[38;5;228;5m    ⚡[38;5;111;25mʻ ʻ[38;5;228;5m⚡[38;5;111;25mʻ ʻ [0m
[38;5;111m    ʻ ʻ ʻ ʻ  [0m' ;;
'Thundery snow showers'*) art_raw='[38;5;226m _`/""[38;5;250m.-.    [0m
[38;5;226m  ,\_[38;5;250m(   ).  [0m
[38;5;226m   /[38;5;250m(___(__) [0m
[38;5;255m     *[38;5;228;5m⚡[38;5;255;25m *[38;5;228;5m⚡[38;5;255;25m * [0m
[38;5;255m    *  *  *  [0m' ;;
'Very cloudy'*) art_raw='
[38;5;240;1m     .--.    [0m
[38;5;240;1m  .-(    ).  [0m
[38;5;240;1m (___.__)__) [0m
             ' ;;
*) art_raw='    .-.
     __)
    (
     `-᾿
      •      ' ;;
esac

art=$(gum style "${art_raw}")


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
	printf '%b' "[A"

	exit 0
}


# Landscape layout
print_test "$(gum join --horizontal --align center "${art}" '  ' "${info}")"

# Portrait layout
print_test "$(gum join --vertical --align center "${art}" '' "${info}")"

# Other layout
print_test "${info}"

exit 1