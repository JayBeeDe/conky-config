# conky-scripts

Lua script for conky script

## Installation

Clone this repo to `~/.config/conky/default`

```bash
sudo apt-get install lua-json lua-socket
git clone git@github.com:JayBeeDe/conky-scripts.git ~/.config/conky/default
```

Then start script with following command:

```bash
conky --config=$HOME/.config/conky/default/default.conf --alignment=top_right -x 5
```

Make ajustements, when you are satisfied and that console doesn't show any dependencies issues, you can configure it to start automatically at session start by adding the following file into `~/.config/autostart/conky.desktop`:

```ini
[Desktop Entry]
DBusActivatable=false
Exec=bash -c "conky --config=$HOME/.conky/default/default.conf --alignment=top_right -x 5 --daemonize 2>&1 >/dev/null"
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
