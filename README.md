# conky-config

Full Lua Conky configuration

![Screenshot](screenshot.png)

## Features

- 100% lua
- all static informations are only loaded once at conky startup
- internet-dependent caching of information
- modular: everything is configurable in configuration file without editing lua code

|Category|Description|
|---|---|
|Basic informations|Date, time, hostname|
|Desktop uptime|Uptime since last wake up (or system is up)|
|Stock market live|1 customizable stock market index|
|Hardware informations|RAM, CPU usage, CPU temperature & battery statuses (or architecture if not a laptop)|
|System informations|Boot, OS, kernel & gnome versions|
|Network|Private & public IPs v4/v6 & routes|
|Storage mountPoints|Partitions informations with customizable blacklist|
|Storage raids|mdadm software raids status|
|Customization|1 customizable logo|

## Installation

Clone this repo to `~/.config/conky/JayBeeDe`

```bash
sudo apt-get install jq fonts-font-awesome lua-json lua-socket lua-sec mokutil
git clone git@github.com:JayBeeDe/conky-config.git ~/.config/conky/JayBeeDe
ln -s ~/.config/conky/JayBeeDe ~/.config/conky/default
```

Install required font dependency from third-part website:

```bash
mkdir -p "${HOME}/.local/share/fonts/"
curl -sSL "https://font.download/dl/font/ge-inspira.zip" -o "/tmp/ge-inspira.zip"
unzip "/tmp/ge-inspira.zip" -d "${HOME}/.local/share/fonts"
chmod -R +x "${HOME}/.local/share/fonts"
rm -f "/tmp/ge-inspira.zip"
```

Then start script with following command:

```bash
cd $HOME/.config/conky/default
conky --config=default.conf --alignment=top_right -x 5
```

Make ajustements, when you are satisfied and that console doesn't show any dependencies issues, you can configure it to start automatically at session start by adding the following file into `~/.config/autostart/conky.desktop`:

```ini
[Desktop Entry]
DBusActivatable=false
Exec=bash -c "cd $HOME/.config/conky/default; conky --config=default.conf --alignment=top_right -x 5 --daemonize"
Icon=Conky
Name=Conky
Name[en_US]=Conky
Name[fr_FR]=Conky
NoDisplay=false
StartupNotify=true
Terminal=false
Type=Application
Version=1.0
```
