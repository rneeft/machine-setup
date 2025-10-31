# Ubuntu - System setup

## First update
```bash
sudo apt update && sudo apt upgrade -y
```

## Desktop
``` bash
sudo apt install gnome-shell-extension-manager
sudo apt install gnome-tweaks -y
``` 

I like to use the following extensions:
- [Blur my shell](https://github.com/aunetx/blur-my-shell)
- [Vitals](https://github.com/corecoding/Vitals/issues)
- [GSConnect](https://github.com/GSConnect/gnome-shell-extension-gsconnect)
- [moveclock](https://github.com/kuvaus/moveclock/)
- [Compiz alike magic lamp effect](https://github.com/hermes83/compiz-alike-magic-lamp-effect)

## Terminal
Making your terminal good and beautiful. Big shout-out to [LinuxScoop](https://www.youtube.com/watch?v=NRGzYzgWFwM)
### install fish and set as default
```bash
sudo apt install fish -y
chsh -s /usr/bin/fish
``` 

Start `fish` and `exit` out of it.

### Installing Oh-My-Posh
```bash
curl -s https://ohmyposh.dev/install.sh | bash -s
```

### New font
```bash
mkdir -p $HOME/.local/share/fonts
wget https://github.com/ryanoasis/nerd-fonts/releases/download/v3.2.1/FiraCode.zip -O $HOME/Downloads/firacode.zip
unzip $HOME/Downloads/firacode.zip -d $HOME/.local/share/fonts
fc-cache -f -v
```
Inside Tweak set the Monospace Text to `FiraCode Nerd Font Mono Retina` and size to `11`. Then relaunch the terminal.

### Download and install oh-my-posh themes
```bash
mkdir ~/.poshthemes
wget https://github.com/JanDeDobbeleer/oh-my-posh/releases/latest/download/themes.zip -O ~/.poshthemes/themes.zip
unzip ~/.poshthemes/themes.zip -d ~/.poshthemes
chmod u+rw ~/.poshthemes/*.json
rm ~/.poshthemes/themes.zip
```

### Wrap it up
```bash
fish_add_path $HOME/.local/bin
gnome-text-editor $HOME/.config/fish/config.fish
``` 

Add the following line at the top: 
``` 
oh-my-posh init fish --config $HOME/.poshthemes/montys.omp.json | source
```

Add the colour scheme of your linking:

```bash
bash -c  "$(wget -qO- https://git.io/vQgMr)" 
```

- Everforest Light Hard
- Everforest Dark Hard

## Software Development

### Git
```bash
sudo add-apt-repository ppa:git-core/ppa
sudo apt update
sudo apt install git
git config --global user.name "Rick Neeft"
git config --global user.email "rick.neeft@outlook.com"
```

### Dotnet
```bash
wget https://dot.net/v1/dotnet-install.sh -O dotnet-install.sh
chmod +x ./dotnet-install.sh
./dotnet-install.sh --version latest
```
``` bash
dotnet workload install aspire
dotnet workload install maui-android
fish_add_path $HOME/.dotnet
fish_add_path $HOME/.dotnet/tools

export PATH=$PATH:$DOTNET_ROOT:$DOTNET_ROOT/tools
dotnet --info
```

## VMWare Workstation pro

- Download VMWare from the website
```bash
tar -cf vmmon.tar vmmon-only
``` 
```bash
tar -cf vmnet.tar vmnet-only
``` 
```bash
sudo cp -v vmmon.tar vmnet.tar /usr/lib/vmware/modules/source/
``` 
```bash
sudo vmware-modconfig --console --install-all
```

## Software

```bash
sudo snap install brave
sudo snap install spotify
sudo snap install rider --classic
sudo snap install code --classic
sudo snap install datagrip --classic
sudo snap install clion --classic
sudo snap install onlyoffice-desktopeditors
```

[Docker Engine](https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository)

