# Installation

## Packages

```bash
sudo pacman -S kitty firefox rofi dmenu qtile chezmoi
```
Other: btop alsa-utils glow sc libre-office spotify-launcher

## Get chezmoi config

```bash
# On desktop
chezmoi init --apply th-herve

# On laptop
chezmoi init --apply th-herve --branch laptop-main
```

## Fonts

Unzip and drop them in ~/.local/share/fonts
- FiraCode Nerd Font
- JetBrainsMono Nerd Font
- Font awsome 6 (https://fontawesome.com/download)

- sudo pacman -S noto-fonts-cjk


For rofi theme, install these [font](https://github.com/adi1090x/rofi/tree/master/fonts)


## Nvim

Once the chezmoi config is apply

```bash 
 
# Install xsel for the clipboard, ripgrep for telescope, gcc and clang for treesitter (coc.nvim ?)
sudo pacman -S xsel ripgrep gcc clang

# install vim-plug
sh -c 'curl -fLo "${XDG_DATA_HOME:-$HOME/.local/share}"/nvim/site/autoload/plug.vim --create-dirs \
       https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim'

# in nvim
:PlugInstall

```
Coc.nvim set up

```bash
# Install node
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash

export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")" [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"

nvm install --lts

nvm use --lts

# Build with yarn

sudo pacman -S yarn

cd ~/.config/nvim/plugged/coc.nvim

yarn build

yarn install
```

## Dwm

Install custom dwm config (otherwise: git clone https://git.suckless.org/dwm)

```bash
cd ~
 
# On desktop
git clone https://github.com/th-herve/dwm_config

# On laptop
git clone -b laptop-main https://github.com/th-herve/dwm_config

mv dwm_config .dwm

cd .dwm

sudo ./make.sh
```

Make a .desktop entry

```bash
cd /usr/share/xsessions

sudo nivm dwm.desktop

# In nvim:
[Desktop Entry]
Encoding=UTF-8
Name=Dwm
Comment=Dynamic window manager
Exec=/usr/local/bin/dwm
Icon=dwm
Type=XSession
```

Install other packages

```bash
sudo pacman -S upower feh playerctl xbacklight

# greenclip
wget https://github.com/erebe/greenclip/releases/download/v4.2/greenclip
# or
yay rofi-greenclip

# dmenu bluetooth
wget "https://raw.githubusercontent.com/Layerex/dmenu-bluetooth/master/dmenu-bluetooth"
sudo install dmenu-bluetooth /usr/local/bin

# If needed set up the wifi
sudo pacman -S bluez bluez-utils
sudo systemctl enable bluetooth.service
sudo systemctl start bluetooth.service
```
