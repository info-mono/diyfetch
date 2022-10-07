<p align="center">
  <img src="https://user-images.githubusercontent.com/43980777/188279024-8669d85b-4df9-4e48-bec8-969c42a12456.png#gh-light-mode-only">
  <img src="https://user-images.githubusercontent.com/43980777/188278675-7adca8da-83d5-4e9c-b53e-fdb337a9da11.png#gh-dark-mode-only">
</p>
<p align="center">
  <a href="https://github.com/info-mono/diyfetch/blob/main/LICENSE"><img src="https://img.shields.io/github/license/info-mono/diyfetch?labelColor=383838&color=585858&style=for-the-badge" alt="License: GPL-3.0"></a>
  <a href="https://gist.github.com/NNBnh/9ef453aba3efce26046e0d3119dab5a7#development-completed"><img src="https://img.shields.io/badge/development-completed-%23585858.svg?labelColor=383838&style=for-the-badge&logoColor=FFFFFF" alt="Development completed"></a>
</p>

## 💡 About

**DIYfetch** it the shell script template for writing adaptive fetch tool utilizing
[Gum's join command](https://github.com/charmbracelet/gum#join).

## 🚀 Setup

### 🧾 Dependencies

- [POSIX compliance shell (`sh`, `bash`, `zsh`, ...)](https://wikipedia.org/wiki/Unix_shell)
- [Gum](https://github.com/charmbracelet/gum) <sup>([installation guide](https://github.com/charmbracelet/gum#installation))</sup>

### 📥 Download

Download the [`diyfetch`](https://github.com/info-mono/diyfetch/blob/main/diyfetch) file:

```sh
curl https://raw.githubusercontent.com/info-mono/diyfetch/main/diyfetch > ~/.local/bin/diyfetch
chmod +x ~/.local/bin/diyfetch
```

> **Note** feel free to change the file name to what ever you want.

### ⚙️ Customize

Open the fetch script with your favorite editor then add, delete and change whatever you prefer.
The script contain detailed guide to customize it.

### ⌨️ Usage

Finally, run the fetch script in the terminal:

```sh
diyfetch
```

## 🖼️ Showcases

Here are some examples, you can find their script in [`examples/`](examples).

### [Insert Name](examples/insertname)

This example is inspired by [Insert Name from Neofetch themes](https://github.com/Chick2D/neofetch-themes#insert-name).

<p align="center">
  <img src="https://user-images.githubusercontent.com/43980777/188280399-86d7b41f-d6f7-4204-b72c-cc7e7cc7327c.png#gh-light-mode-only">
  <img src="https://user-images.githubusercontent.com/43980777/188280410-335dd584-ffba-4aa3-a924-c92a6369e457.png#gh-dark-mode-only">
</p>

### [Idlifetch](examples/idlifetch)

This example is inspired by [Idlifetch from Neofetch themes](https://github.com/Chick2D/neofetch-themes#idlifetch).

<p align="center">
  <img src="https://user-images.githubusercontent.com/43980777/188280960-e312ba23-5a78-43e3-8c66-ccbf57fc03a8.png#gh-light-mode-only">
  <img src="https://user-images.githubusercontent.com/43980777/188280962-15f1f512-9fbc-437f-8fa2-c618c8ff46ae.png#gh-dark-mode-only">
</p>

### [Ozozfetch](examples/ozozfetch)

This example is inspired by [Ozozfetch from Neofetch themes](https://github.com/Chick2D/neofetch-themes#ozozfetch).

<p align="center">
  <img src="https://user-images.githubusercontent.com/43980777/188281825-be3b5c2c-5abf-4146-be14-f450e6dedf5e.png#gh-light-mode-only">
  <img src="https://user-images.githubusercontent.com/43980777/188281823-5eb4a65e-8abe-4b46-b49d-23017fdff650.png#gh-dark-mode-only">
</p>

### [Fm6000](examples/fm6000)

This example is inspired by [Fetch-master 6000](https://github.com/anhsirk0/fetch-master-6000).

<p align="center">
  <img src="https://user-images.githubusercontent.com/43980777/188281315-6b3d6deb-0c14-48b7-bbfb-285435f1af57.png#gh-light-mode-only">
  <img src="https://user-images.githubusercontent.com/43980777/188281314-1be0d9f8-dd44-4042-bf2e-3dcf62de1aa3.png#gh-dark-mode-only">
</p>

### [Laundryfetch](examples/laundryfetch)

A tiny fetch I make to celebrate my No.1 victory at the local game jam.

> I buy a smart washing machine for mommy with the prize money.

<p align="center">
  <img src="https://user-images.githubusercontent.com/43980777/188282042-ad31c069-af30-4e32-8e08-5c236f8d5f4e.png#gh-light-mode-only">
  <img src="https://user-images.githubusercontent.com/43980777/188282044-16e7e66f-4bc1-4986-884d-fa0c6b41dc11.png#gh-dark-mode-only">
</p>

### [Timefetch](examples/timefetch)

Why stop at system informations. You can fetch a bunch of time related information as well!

<p align="center">
  <img src="https://user-images.githubusercontent.com/43980777/188299096-9e7e46d7-d969-43d8-84cb-8a881d10909c.png#gh-light-mode-only">
  <img src="https://user-images.githubusercontent.com/43980777/188299095-f1183747-2210-412a-952f-8d3e4109b0c6.png#gh-dark-mode-only">
</p>

> **Note** <br>
> Requirements: [`figlet`](https://www.figlet.org).

### [Weatherfetch](examples/weatherfetch)

This example utilize [`wttr.in`'s API](https://github.com/chubin/wttr.in#json-output)
with [Wego's ansi arts](https://github.com/schachmat/wego).

<p align="center">
  <img src="https://user-images.githubusercontent.com/43980777/188382367-eb23747e-033e-492e-a697-2b3122b9db50.png#gh-light-mode-only">
  <img src="https://user-images.githubusercontent.com/43980777/188382370-cea50a4d-e417-4a1f-a54e-fff22ed04dc1.png#gh-dark-mode-only">
</p>

> **Note** <br>
> Requirements: [`jq`](https://stedolan.github.io/jq).

### [Pokefetch](examples/pokefetch)

Poke~~dex~~ fetch! This example utilize [PokeAPI](https://pokeapi.co)
and [Pokemon colorscripts](https://gitlab.com/phoneybadger/pokemon-colorscripts).

<p align="center">
  <img src="https://user-images.githubusercontent.com/43980777/188299394-9e139cf7-2b4f-4f93-961e-759b265b883e.png#gh-light-mode-only">
  <img src="https://user-images.githubusercontent.com/43980777/188299392-4d10a8e9-ae9f-4fb6-8146-0f77d06c3c2f.png#gh-dark-mode-only">
  <br><br>
  <a href="https://asciinema.org/a/518810" target="_blank"><img align="center" src="https://user-images.githubusercontent.com/43980777/188304706-c50b93b4-1b88-4d7b-bd27-e0a749b791a9.gif"></a>
</p>

> **Note** <br>
> Requirements: [`jq`](https://stedolan.github.io/jq).

## 💌 Credits

Special thanks to:
- [**Neofetch Themes**](https://github.com/Chick2D/neofetch-themes) by [Chick Chan](https://github.com/Chick2D)
- [**Neofetch**](https://github.com/dylanaraps/neofetch) by [Dylan](https://github.com/dylanaraps)
- [**Pfetch**](https://github.com/dylanaraps/pfetch) also by [Dylan](https://github.com/dylanaraps)
- [**Ufetch**](https://gitlab.com/jschx/ufetch) by [Jschx](https://gitlab.com/jschx)
- [**Pure sh bible**](https://github.com/dylanaraps/pure-sh-bible) also by [Dylan](https://github.com/dylanaraps)
- [**ShellCheck**](https://www.shellcheck.net) also by [Vidar Holen](https://github.com/koalaman)

<br><br><br><br>

---

> <h1 align="center">Made with ❤️ by <a href="https://github.com/info-mono"><code>@info-mono</code></a></h1>
>
> <p align="center"><a href="https://www.buymeacoffee.com/nnbnh"><img src="https://img.shields.io/badge/buy_me_a_coffee%20-%23F7CA88.svg?logo=buy-me-a-coffee&logoColor=333333&style=for-the-badge" alt="Buy Me a Coffee"></a></p>
>
> <p align="right"><a href="https://gist.github.com/NNBnh/ad4816f847f4c6ada376cf36e6e70299" title="Easter egg">🥚</a></p>
