# dotfiles

This helps me manage my system dotfiles with `stow`

## Requirements

- Make sure git is set up

### Installing zsh

1. Install using the package manager

```
sudo apt install zsh
```

2. Verify installation running

```
zsh --version
```

3. Make default shell

```
chsh -s $(which zsh)
```

4. Log out and back to use the shell

5. Install ooh-my-zsh

- Run the command below or folow https://github.com/ohmyzsh/ohmyzsh?tab=readme-ov-file#basic-installation

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

6. Activate syntax highlighting

- Install zsh-syntax-highlighting

```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ~/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting
```

- Install catppuccin syntax highlighting

```
git clone https://github.com/catppuccin/zsh-syntax-highlighting.git
mkdir .zsh
cd zsh-syntax-highlighting/themes/
cp -v catppuccin_mocha-zsh-syntax-highlighting.zsh ~/.zsh/
```

### Installing alacritty

1. Install using package manager

```
sudo apt install alacritty
```

2. Download catppuccin theme

```
curl -LO --output-dir ~/dotfiles/.config/alacritty https://github.com/catppuccin/alacritty/raw/main/catppuccin-mocha.toml
```

### Installing tmux

1. Install using package manager

```
sudo apt install tmux
```

2. Install tpm to manage tmux packages

```
git clone https://github.com/tmux-plugins/tpm ~/dotfiles/.tmux/plugins/tpm
```

3. Download last version of FiraCode Nerd font

```
wget https://github.com/ryanoasis/nerd-fonts/releases/download/v3.2.0/FiraCode.zip
```

4. Unzip and move files move file to fonts dir

```
sudo unzip ~/Downloads/FiraCode.zip /usr/share/fonts
```

### Installing neovim

1. Install neovim

```
sudo add-apt-repository ppa:neovim-ppa/stable
sudo apt-get update
sudo apt-get install neovim
```

2. Install NVChad

```
git clone -b v2.0 https://github.com/NvChad/NvChad ~/dotfiles/.config/nvim --depth 1
```

3. Start neovim
At start it will download LSP and everything we need

```
nvim
```

### Install stow

```
sudo apt install stow
```

## Run stow

1. Go to the dotfiles and run.

```
stow
```

2. If configs already exists either backup them or

```
stow --adopt .
```

*this can lead to some issues if the files in .dotfiles are different than the ones already present*
