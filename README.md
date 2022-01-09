# Install packages

```bash
#update mirrors to chile

sudo pacman -Syu
sudo pacman -S alsa-firmware sof-firmware alsa-ucm-conf firefox vim code dbeaver tmux python-pip bat discord xclip xsel snapd telegram-desktop bat


sudo systemctl start snapd
sudo snap install spotify

#install ohmyzsh
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"



sudo pamac update
sudo pamac build zoom



pip install virtualenvwrapper poetry
```

# ~/.zshrc

```bash
export VISUAL=vim
export EDITOR="$VISUAL"

alias dichato="ssh cgarrido@dichato.dcc.uchile.cl"
alias anakena="ssh cgarrido@anakena.dcc.uchile.cl"

alias pbcopy='xclip -selection clipboard'
alias pbpaste='xclip -selection clipboard -o'

export WORKON_HOME=~/envs
export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python3
export VIRTUALENVWRAPPER_VIRTUALENV=~/.local/bin/virtualenv
source ~/.local/bin/virtualenvwrapper.sh

export PATH="$HOME/.poetry/bin:$PATH"
```


# ~/.tmux.conf
Instalar tmp

```bash
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

```bash
set -g @plugin 'dracula/tmux'

set -g @dracula-show-weather false
set -g @dracula-show-location false
set -g @dracula-day-month true
set -g @dracula-military-time true
set -g @dracula-show-timezone false
set -g @dracula-show-flags true
set -g @dracula-show-left-icon window
set -g @dracula-show-powerline true
set -g @dracula-show-network false

# remap prefix from 'C-b' to 'C-a'
unbind C-b
set-option -g prefix C-a
bind-key C-a send-prefix

# split panes using - and |
bind | split-window -h
bind - split-window -v
unbind '"'
unbind %

# reload config file
bind r source-file ~/.tmux.conf

# switch panes using Alt-arrow without prefix
bind -n M-Left select-pane -L
bind -n M-Right select-pane -R
bind -n M-Up select-pane -U
bind -n M-Down select-pane -D

# Enable mouse control (clickable windows, panes, resizable panes)
set -g mouse on

# don't rename windows automatically
set-option -g allow-rename off


set -g @plugin 'tmux-plugins/tpm'
set -g @plugin 'tmux-plugins/tmux-sensible'
set -g @plugin 'tmux-plugins/tmux-resurrect'

# Other examples:
# set -g @plugin 'github_username/plugin_name'
# set -g @plugin 'git@github.com:user/plugin'
# set -g @plugin 'git@bitbucket.com:user/plugin'

# Initialize TMUX plugin manager (keep this line at the very bottom of tmux.conf)
run '~/.tmux/plugins/tpm/tpm'

```

# Create sshkey

```bash
ssh-keygen -t rsa -b 4096
```



# Dracula theme terminal
```bash
git clone https://github.com/dracula/xfce4-terminal.git
mkdir -p ~/.local/share/xfce4/terminal/colorschemesmv xfce4-terminal/Dracula.theme ~/.local/share/xfce4/terminal/colorschemes/.
rm -rf xfce4-terminal/
```


# Visual Studio Code

settings.json
```json
{
    "diffEditor.ignoreTrimWhitespace": false,
    "editor.renderWhitespace": "all",
    "workbench.colorTheme": "Dracula",
    "editor.rulers": [79,100],
    "[*]": {
        "indent_style": "space",
        "editor.detectIndentation": false
    },
    "[python]": {
        "editor.tabSize": 4
    },
    "[html]": {
        "editor.tabSize": 2
    },
    "editor.minimap.enabled": false,
    "editor.tokenColorCustomizations": null,

    "editor.fontFamily": "Fira Code",
    "editor.fontLigatures": true,
    "breadcrumbs.enabled": true,
    "files.associations": {
        ".pls": "SQL"
    },
    "workbench.editor.enablePreview": false,
    "launch": {
        "configurations": [],
        "compounds": []
    },
    "trailing-spaces.trimOnSave": true
}
```

Plugins:

- Docker
- Dracula Official
- Python
- Rewrap
- Trailing spaces
- Unique Lines
- Flip
- Jupyter
