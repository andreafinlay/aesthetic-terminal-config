# ａｅｓｔｈｅｔｉｃ terminal config

An elegant, relaxing terminal experience using Hyper, Fish and Color LS

!["example"](https://github.com/andreafinlay/aesthetic-terminal-config/blob/master/assets/example.png?raw=true)

## Setup

1. Install [Hyper.js](https://hyper.is/)

2. Install [Fish](https://fishshell.com/)

3. Install [Oh My Fish](https://github.com/oh-my-fish/oh-my-fish)

## Config

#### Hyper

##### Custom plugin setup

Create `~/.hyper_plugins/local/` and clone [hyper-tabs-enhanced](https://github.com/henrikdahl/hyper-tabs-enhanced) into it.

Replace `index.js` with the index file in the */src/hyper/plugins/hyper-tabs-enhanced/* folder from this repo.

##### Main config

Hyper will have created `~/.hyper.js` by default. Replace it with the one from the */src/hyper* folder in this repo.

Fish will have installed to `~/usr/local/bin/fish` by default, but if you installed it elsewhere, make sure to modify the value of `shell` in your hyper config to point to your Fish install path.

#### Fish

By default, `~/.config/fish/` will should have been created. If not, create it.

##### OMF setup

Create `~/.config/fish/conf.d/` (if it doesn't already exist).

Copy the `omf.fish` file from the */src/fish/conf.d/* folder in this repo into `~/.config/fish/conf.d/`.

Open `~/.local/share/omf/init.fish` and add `set -x VIRTUAL_ENV_DISABLE_PROMPT 1` to the bottom of the file.

##### Main config

Create `~/.config/fish/functions/` and copy `fish_prompt.fish` and `fish_title.fish` from this repo's */src/fish/functions/* into it. 

`fish_prompt.fish` contains the main Fish theming config, based on Beau Hastings' [Kawasaki](https://github.com/hastinbe/theme-kawasaki) theme for OMF.

It's quite extensible and has plenty of options, lots of fun to play around with.

For example, I use unicode characters for my git prompt display but you could do just about anything with it.

`fish_title.fish` is used to tell *hyper-tabs-enhanced* to display the current process in the tab title.

#### Color LS

Download and install [Color LS](https://github.com/athityakumar/colorls) (requires Ruby), first installing the patched font of your choice from [Nerd Fonts](https://github.com/ryanoasis/nerd-fonts/blob/master/readme.md) - I use [Fura Code](https://github.com/ryanoasis/nerd-fonts/tree/master/patched-fonts/FiraCode).

Re-open your `~/.hyper.js` and align the font-family with whatever patched font you installed.

*NOTE*: Step 4 of the Color LS installation, adding tab completion, won't work since Fish doesn't know how to handle `.sh` files. I resolved this by creating a `~/.config/fish/config.fish` file and setting aliases for Color LS commands + flags with the syntax `alias [alias]='[command]'`, as is suggested in "Recommended configurations". I've included a couple of examples in this repo. Available flags are listed [here](https://github.com/athityakumar/colorls#flags).

Installing Color LS should have also installed [Rainbow](https://github.com/sickill/rainbow) as a dependency. Access the Rainbow config by navigating to `/Library/Ruby/Gems/2.3.0/gems/rainbow-3.0.0/` and open `lib/rainbow/x11_color_names.rb`. This contains a list of colours which are available to Color LS, in RGB. Copy the contents from the same file in the */src/colorls/rainbow* folder in this repo into that file. (There are some that I've added that I'm not using in this config so feel free to play around with them.)

Open `~/.config/colorls/dark_colors.yaml` and replace the contents with the ones from the identical file in the */src/colorls* folder in this repo. Lots of opportunity to mess around here as well as I only modified a few myself.

That's it! (I think). Let me know if it isn't working or if you have any suggestions. Enjoy!





