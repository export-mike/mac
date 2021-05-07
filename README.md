# Mac Setup

`https://brew.sh/`

create a Brewfile
```
tap "homebrew/bundle"
tap "homebrew/cask"
tap "homebrew/cask-drivers"
tap "homebrew/cask-versions"
tap "homebrew/core"
brew "fzf"
brew "gnupg"
brew "go"
brew "grc"
brew "jq"
brew "nvm"
brew "pgcli"
brew "the_silver_searcher"
cask "adoptopenjdk8"
cask "android-sdk"
cask "android-studio"
cask "google-chrome"
cask "google-cloud-sdk"
cask "iterm2"
cask "rectangle"
cask "slack"
cask "sonos"
cask "spotify"
cask "visual-studio-code"
cask "docker"
cask "notable"
```

`brew bundle`

.zshrc
```
# vars
export GITHUB_ORG=<ENTER_GITHUB_ORG_HERE>
export GOPATH=$HOME/go
export GOBIN=$HOME/go/bin
export GOPRIVATE=github.com/$GITHUB_ORG
export GPG_TTY=$(tty)
export NVM_DIR="$HOME/.nvm"
  [ -s "/usr/local/opt/nvm/nvm.sh" ] && . "/usr/local/opt/nvm/nvm.sh"  # This loads nvm
  [ -s "/usr/local/opt/nvm/etc/bash_completion.d/nvm" ] && . "/usr/local/opt/nvm/etc/bash_completion.d/nvm"  # This loads nvm bash_completion
export ANDROID_SDK_ROOT="$HOME/Library/Android/sdk"

# path
export PATH=$PATH:$GOPATH
export PATH=$PATH:$GOBIN
export PATH=$PATH:/Users/$(whoami)/.yarn/bin
export GRADLE_HOME=/usr/local/opt/gradle
export PATH=$GRADLE_HOME/bin:$PATH
export ANDROID_HOME=/usr/local/opt/android-sdk
export PATH=$ANDROID_HOME/tools:$PATH
export PATH=$ANDROID_HOME/platform-tools:$PATH
export PATH=$ANDROID_HOME/build-tools/19.1.0:$PATH
# tools
[ -f ~/.fzf.zsh ] && source ~/.fzf.zsh
[ -s "/opt/homebrew/opt/nvm/nvm.sh" ] && . "/opt/homebrew/opt/nvm/nvm.sh" # This loads nvm
[ -s "/opt/homebrew/opt/nvm/etc/bash_completion.d/nvm" ] && . "/opt/homebrew/opt/nvm/etc/bash_completion.d/nvm"  # This loads nvm bash_completion
if [ -f '/opt/homebrew/Caskroom/google-cloud-sdk/latest/google-cloud-sdk/completion.zsh.inc' ]; then . '/opt/homebrew/Caskroom/google-cloud-sdk/latest/google-cloud-sdk/completion.zsh.inc'; fi
if [ -f '/opt/homebrew/Caskroom/google-cloud-sdk/latest/google-cloud-sdk/path.zsh.inc' ]; then . '/opt/homebrew/Caskroom/google-cloud-sdk/latest/google-cloud-sdk/path.zsh.inc'; fi


# aliases
function pubfinder() {
    brew install $(brew search $1 | fzf | tr '\n' ' ')
}

function src() {
    source ~/.zshrc
}


function gits() {
    folder=/Users/$(whoami)/go/src/github.com/$GITHUB_ORG
    repo=`ls $folder | fzf`
    cd $folder/$repo
}

function goget() {
  GO111MODULE=off go get github.com/$1
}

source $HOME/scripts/db

# aliases
alias r=gits
alias gfmt=gofumpt
alias pip=pip3
alias python=python3
alias gt='go test -v ./...' # gt -run <Name_OF_TEST>
alias ze='code ~/.zshrc'
```


Node.js

```nvm install 16```

```nvm install 14```

```nvm alias default 14```


```sdkmanager --licenses```

```npm i -g yarn```
