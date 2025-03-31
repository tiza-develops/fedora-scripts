# The changes I make to my usual Fedora Fresh Installs
First of all, check out my [fish dots](https://github.com/tiza-develops/fish-dots)

## Remove and tidy repositories
### Remove non vital repositories and copr repos
```fish
    dnf copr remove phracek/PyCharm
```
```fish
    sudo rm -rf /etc/yum.repos.d/google-chrome.repo
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
Install via packages mpv, gnome and a ebook reader
```fish
dnf install mpv btop gnome-tweaks foliate
```
Install via flatpak Extension Manager, Amberol, Solanum, Errands, Komikku and Blanket
```fish
flatpak install flathub com.mattjakeman.ExtensionManager io.bassi.Amberol org.gnome.Solanum io.github.mrvladus.List info.febvre.Komikku com.rafaelmardojai.Blanket
```

## Install zen-browser or ungoogled chromium
```fish
dnf copr enable wojnilowicz/ungoogled-chromium
```
```fish
sudo dnf copr enable sneexy/zen-browser
```
