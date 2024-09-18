# The changes I make to my usual Fedora Fresh Installs
## Install the fish shell
```fish
dnf install fish tmux kitty
chsh -s $(user) fish
```
Also check out my [fish dots](https://github.com/tiza-develops/fish-dots)
## Remove ~bloat~ unnecesary applications
### GNOME Spin
```fish
dnf rm loupe snapshot gnome-abrt gnome-maps gnome-terminal gnome-boxes evince totem baobab rhythmbox gnome-contacts gnome-weather gnome-maps mediawriter libreoffice-core simple-scan gnome-system-monitor gnome-disk-utility yelp gnome software gnome-text-editor gnome-tour gnome-calendar
```

## Remove and tidy repositories
### Remove non vital repositories and copr repos
```fish
    dnf copr remove phracek/PyCharm
```
### Remove fedora flatpak remote
```fish
flatpak remote-delete fedora
```
## Install rmpfussion
```fish
sudo dnf install https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
```
The main reason I do this is to get proprietary codecs for ffmpeg and mpv!
```fish
dnf swap ffmpeg-free ffmpeg --allowerasing
```
## Now that we removed a lot of applications, let's install better ones!
```fish
dnf install mpv btop gnome-tweaks
# Install, in that order: Extension Manager, Solanum, Errands, Komikku, Papers and Foliate
flatpak install flathub com.mattjakeman.ExtensionManager io.bassi.Amberol org.gnome.Solanum io.github.mrvladus.List info.febvre.Komikku org.gnome.Papers com.github.johnfactotum.Foliate
```

## Install fonts, themes and icons!
```fish
dnf install papirus-icon-theme
bash -c  "$(curl -fsSL https://raw.githubusercontent.com/officialrajdeepsingh/nerd-fonts-installer/main/install.sh)"
```
