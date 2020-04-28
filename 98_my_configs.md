# My configs

```
apps:
  - ack
  - powertop
  - ShellCheck

gui_apps:
  - clusterssh
  - remmina
  - 'remmina-plugins-*'

flatpak_apps:
  - name: com.skype.Client
    remote: flathub
  - name: com.spotify.Client
    remote: flathub
  - name: com.slack.Slack
    remote: flathub
  - name: com.github.debauchee.barrier
    remote: flathub
  - name: com.discordapp.Discord
    remote: flathub

pip_apps:
  - name: ansible
    virtualenv_enabled: false
  - name: azure-cli
    virtualenv_enabled: true
  - name: docker-compose
    virtualenv_enabled: false
  - name: ansible-lint
    virtualenv_enabled: false
  - name: yamllint
    virtualenv_enabled: false
  - name: psutil
    virtualenv_enabled: false
  - name: niet
    virtualenv_enabled: true

gnome_shell_extensions:
  - 517         # caffeine
  - 615         # appindicator
  - 945         # cpu-power-manager

krew_plugins:
  - sniff

vscode_extensions:
  - bbenoist.vagrant
  - DavidAnson.vscode-markdownlint
  - eamodio.gitlens
  - haaaad.ansible
  - mauve.terraform
  - ms-azure-devops.azure-pipelines
  - ms-azuretools.vscode-docker
  - ms-dotnettools.csharp
  - ms-kubernetes-tools.vscode-kubernetes-tools
  - ms-mssql.mssql
  - ms-python.python
  - ms-vscode.azure-account
  - redhat.vscode-yaml
  - samuelcolvin.jinjahtml
  - streetsidesoftware.code-spell-checker
  - vscode-icons-team.vscode-icons
  - vscoss.vscode-ansible
  - yzhang.markdown-all-in-one

custom_installer:
  - desktop/apps/ctop
  - desktop/apps/google_chrome
  - desktop/apps/keeweb
  - desktop/apps/keybase
  - desktop/apps/oh_my_zsh
  - desktop/apps/qemu
  - desktop/apps/terminator
  - desktop/apps/terraform
  - desktop/apps/vagrant
  - desktop/apps/vnc
  - desktop/apps/vscode
  - desktop/apps/kubectl
  - desktop/apps/helm
  - desktop/apps/stern
  - desktop/apps/kail
  - desktop/apps/dive
  - desktop/apps/hadolint
  - desktop/apps/kubescore
  - desktop/apps/netcore_sdk
```

```
# VScode settings
{
  "files.insertFinalNewline": true,
  "files.trimFinalNewlines": true,
  "files.trimTrailingWhitespace": true,
  "editor.tabSize": 2,
  "editor.detectIndentation": false,
  "window.zoomLevel": 0,
  "workbench.colorTheme": "Visual Studio Dark",
  "workbench.iconTheme": "vscode-icons"
}
```

```
#oh-my-zsh
# If you come from bash you might have to change your $PATH.
# export PATH=$HOME/bin:/usr/local/bin:$PATH

# Path to your oh-my-zsh installation.
  export ZSH="$HOME/.oh-my-zsh"

# Set name of the theme to load. Optionally, if you set this to "random"
# it'll load a random theme each time that oh-my-zsh is loaded.
# See https://github.com/robbyrussell/oh-my-zsh/wiki/Themes
ZSH_THEME="agnoster"

# Powerlevel9k
# https://github.com/bhilburn/powerlevel9k

# Set list of themes to load
# Setting this variable when ZSH_THEME=random
# cause zsh load theme from this variable instead of
# looking in ~/.oh-my-zsh/themes/
# An empty array have no effect
# ZSH_THEME_RANDOM_CANDIDATES=( "robbyrussell" "agnoster" )

# Uncomment the following line to use case-sensitive completion.
# CASE_SENSITIVE="true"

# Uncomment the following line to use hyphen-insensitive completion. Case
# sensitive completion must be off. _ and - will be interchangeable.
# HYPHEN_INSENSITIVE="true"

# Uncomment the following line to disable bi-weekly auto-update checks.
# DISABLE_AUTO_UPDATE="true"

# Uncomment the following line to change how often to auto-update (in days).
# export UPDATE_ZSH_DAYS=13

# Uncomment the following line to disable colors in ls.
# DISABLE_LS_COLORS="true"

# Uncomment the following line to disable auto-setting terminal title.
# DISABLE_AUTO_TITLE="true"

# Uncomment the following line to enable command auto-correction.
# ENABLE_CORRECTION="true"

# Uncomment the following line to display red dots whilst waiting for completion.
# COMPLETION_WAITING_DOTS="true"

# Uncomment the following line if you want to disable marking untracked files
# under VCS as dirty. This makes repository status check for large repositories
# much, much faster.
# DISABLE_UNTRACKED_FILES_DIRTY="true"

# Uncomment the following line if you want to change the command execution time
# stamp shown in the history command output.
# The optional three formats: "mm/dd/yyyy"|"dd.mm.yyyy"|"yyyy-mm-dd"
# HIST_STAMPS="mm/dd/yyyy"

# Would you like to use another custom folder than $ZSH/custom?
# ZSH_CUSTOM=/path/to/new-custom-folder

# Which plugins would you like to load? (plugins can be found in ~/.oh-my-zsh/plugins/*)
# Custom plugins may be added to ~/.oh-my-zsh/custom/plugins/
# Example format: plugins=(rails git textmate ruby lighthouse)
# Add wisely, as too many plugins slow down shell startup.
plugins=(
  git
  zsh-autosuggestions
  docker
  ansible
{% if item != 'root' %}
  vscode
  # terraform
  vagrant
  kubectl
  kube-ps1
  # helm
{% endif %}
)

# To debug oh-my-zsh loading time, type:
# zsh -xv

source /usr/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh
export ZSH_HIGHLIGHT_HIGHLIGHTERS_DIR=/usr/share/zsh-syntax-highlighting/highlighters

source $ZSH/oh-my-zsh.sh

# User configuration

# export MANPATH="/usr/local/man:$MANPATH"

# You may need to manually set your language environment
# export LANG=en_US.UTF-8

# Preferred editor for local and remote sessions
# if [[ -n $SSH_CONNECTION ]]; then
#   export EDITOR='vim'
# else
#   export EDITOR='mvim'
# fi

# Compilation flags
# export ARCHFLAGS="-arch x86_64"

# ssh
# export SSH_KEY_PATH="~/.ssh/rsa_id"

# Set personal aliases, overriding those provided by oh-my-zsh libs,
# plugins, and themes. Aliases can be placed here, though oh-my-zsh
# users are encouraged to define aliases within the ZSH_CUSTOM folder.
# For a full list of active aliases, run `alias`.
#
# Example aliases
# alias zshconfig="mate ~/.zshrc"
# alias ohmyzsh="mate ~/.oh-my-zsh"

{% if item != 'root' %}
KUBE_PS1_SYMBOL_USE_IMG=true
KUBE_PS1_SYMBOL_ENABLE=true
KUBE_PS1_NS_ENABLE=false
KUBE_PS1_SEPARATOR=''
KUBE_PS1_DIVIDER=''
KUBE_PS1_PREFIX=''
KUBE_PS1_SUFFIX=' '
PROMPT='$(kube_ps1)'$PROMPT

export PATH="${KREW_ROOT:-$HOME/.krew}/bin:$PATH"
{% endif %}

# Virtualenv prompt
# export WORKON_HOME=~/.virtualenv
# source /usr/bin/virtualenvwrapper.sh
#

{% raw %}
prompt_end() {
  if [[ -n $CURRENT_BG ]]; then
      print -n "%{%k%F{$CURRENT_BG}%}$SEGMENT_SEPARATOR"
  else
      print -n "%{%k%}"
  fi

  print -n "%{%f%}"
  CURRENT_BG=''

  #Adds the new line and ➜ as the start character.
  printf "\n➜";
}
{% endraw %}

# Extracting Dockerfile from image
dfimageext() {
	docker history --no-trunc $1  | tac | tr -s ' ' | cut -d " " -f 5- | sed 's,^/bin/sh -c #(nop) ,,g' | sed 's,^/bin/sh -c,RUN,g' | sed 's, && ,\n  & ,g' | sed 's,\s*[0-9]*[\.]*[0-9]*[kMG]*B\s*$,,g' | head -n -1
}

# Shutting down keybase
kbdown () {
        if killall Keybase &> /dev/null
        then
                echo Shutting down Keybase GUI...
        fi
        if fusermount -uz /keybase &> /dev/null
        then
                echo Unmounting /keybase...
        fi
        if killall kbfsfuse &> /dev/null
        then
                echo Shutting down kbfsfuse...
        fi
        if killall keybase &> /dev/null
        then
                echo Shutting down keybase service...
        fi
}
```

```
#terminator config
[global_config]
  focus = system
  smart_copy = False
  title_font = Sans 10
  title_hide_sizetext = True
  title_transmit_bg_color = "#d30102"
  title_use_system_font = False
[keybindings]
[layouts]
  [[default]]
    [[[child1]]]
      parent = window0
      profile = default
      type = Terminal
    [[[window0]]]
      parent = ""
      type = Window
[plugins]
[profiles]
  [[default]]
    allow_bold = False
    background_color = "#002b36"
    cursor_color = "#eee8d5"
    font = Roboto Mono for Powerline 11
    foreground_color = "#eee8d5"
    palette = "#073642:#dc322f:#859900:#b58900:#268bd2:#d33682:#2aa198:#eee8d5:#586e75:#cb4b16:#586e75:#657b83:#839496:#6c71c4:#93a1a1:#fdf6e3"
    scrollback_infinite = True
    use_system_font = False
  [[solarized-dark]]
    background_color = "#002b36"
    cursor_color = "#eee8d5"
    font = Meslo LG M DZ for Powerline 12
    foreground_color = "#eee8d5"
    palette = "#073642:#dc322f:#859900:#b58900:#268bd2:#d33682:#2aa198:#eee8d5:#586e75:#cb4b16:#586e75:#657b83:#839496:#6c71c4:#93a1a1:#fdf6e3"
    use_system_font = False
  [[solarized-light]]
    background_color = "#eee8d5"
    cursor_color = "#002b36"
    foreground_color = "#002b36"
    palette = "#073642:#dc322f:#859900:#b58900:#268bd2:#d33682:#2aa198:#eee8d5:#002b36:#cb4b16:#586e75:#657b83:#839496:#6c71c4:#93a1a1:#fdf6e3"
```
