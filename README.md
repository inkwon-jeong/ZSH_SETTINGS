# ZSH_SETTINGS

### export

```
export ADB_HOME=/Users/{user_name}/Library/Android/sdk/platform-tools
export PATH=${ADB_HOME}:$PATH
export ANDROID_SDK_ROOT=$HOME/Library/Android/sdk
export PATH=$PATH:$ANDROID_SDK_ROOT/emulator
export PATH=$PATH:$ANDROID_SDK_ROOT/platform-tools
```

### theme

```
ZSH_THEME="dpoggi"
```

### plugins

```
plugins=(
  git
  zsh-syntax-highlighting
  zsh-autosuggestions
)
```

### zsh highlight

```
typeset -A ZSH_HIGHLIGHT_STYLES
ZSH_HIGHLIGHT_STYLES[command]='fg=magenta,bold'
ZSH_HIGHLIGHT_STYLES[path]='fg=cyan'
ZSH_HIGHLIGHT_STYLES[builtin]='fg=green'
ZSH_HIGHLIGHT_STYLES[single-hyphen-option]='fg=yellow'
ZSH_HIGHLIGHT_STYLES[double-hyphen-option]='fg=yellow'

typeset -A ZSH_HIGHLIGHT_PATTERNS
ZSH_HIGHLIGHT_HIGHLIGHTERS=(main brackets pattern cursor)
ZSH_HIGHLIGHT_PATTERNS+=('git ^*[[:blank:]]*' 'fg=cyan')
```

### scm_breeze

```
[ -s "/Users/inkwon.jeong/.scm_breeze/scm_breeze.sh" ] && source "/Users/inkwon.jeong/.scm_breeze/scm_breeze.sh"
```

### gpg

```
export GPG_TTY=$(tty)
```

### alias

```
alias gsync="git fetch -p && for branch in \$((git branch -vv | grep -e gone ; git branch -vv | grep -ve origin) | awk '{if(\$1 == \"*\") print \$2; else print \$1;}'); do git branch -D \$branch; done"
alias gradle-all-deps='./gradlew dependencies $(./gradlew -q projects | grep -Fe ---\ Project | sed -Ee "s/^.+--- Project '"'([^']+)'/\1:dependencies/"'")'
alias gradle-all-projects='./gradlew -q projects | grep -Fe ---\ Project | sed -Ee "s/^.+--- Project '"'([^']+)'/\1:dependencies/"'"'
```

