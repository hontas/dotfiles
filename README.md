# ~~Mathias~~ Hontas dotfiles
> Forked from [https://github.com/mathiasbynens/dotfiles](https://github.com/mathiasbynens/dotfiles)

## Installation

### 0. SSH

Generate new keys
```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

If you're using macOS Sierra 10.12.2 or later, you will need to modify your ~/.ssh/config file to automatically load keys into the ssh-agent and store passphrases in your keychain
```bash
# ~/,ssh/config
Host *
 AddKeysToAgent yes
 IdentityFile ~/.ssh/id_rsa
```

Add to github
```bash
pbcopy < ~/.ssh/id_rsa.pub
```

Install `homebrew` and command line tools
```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

### 1. Clone and run bootstrap script
```bash
git clone git@github.com:hontas/dotfiles.git && cd dotfiles && source bootstrap.sh
```

### 2. Oh-my-zsh
```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

Prepend `source ~/.bashrc` to `~/.zshrc` and maybe add `nyan` to plugins :)

#### 2.1 zsh-plugins

> git nvm thefuck

1. https://github.com/rupa/z
2. https://github.com/zsh-users/zsh-autosuggestions
3. https://github.com/zsh-users/zsh-syntax-highlighting
4. `brew install howdoi thefuck`

### 3. Install nvm
See updated instructions at [https://github.com/creationix/nvm](https://github.com/creationix/nvm)
```bash
mkdir ~/.nvm
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash
```

### 4. Install Homebrew formulae

Install `homebrew` and `brew-cask`
```bash
brew tap caskroom/cask
brew tap caskroom/versions
```

When setting up a new Mac, you may want to install some common [Homebrew](http://brew.sh/) formulae:
```bash
./brew.sh
```

### 5. Add sensitive settings in `~/.extra`
Example:
```bash
# Git credentials
# Not in the repository, to prevent people from accidentally committing under my name
GIT_AUTHOR_NAME="My name"
git config --global user.name "$GIT_AUTHOR_NAME"
GIT_AUTHOR_EMAIL="mail@example.com"
git config --global user.email "$GIT_AUTHOR_EMAIL"
```

You could also use `~/.extra` to override settings, functions and aliases from my dotfiles repository.

### 6. Sensible OS X defaults

When setting up a new Mac, you may want to set some sensible OS X defaults:

```bash
./.osx
```

### 7. nano syntax highligtning

You must update nano version before `brew install nano`

```bash
curl https://raw.githubusercontent.com/scopatz/nanorc/master/install.sh | sh
```

Update ~/.nanorc with what languages you want highligting for

Might have to add `export LC_ALL=sv_SE.UTF-8` or whatever locale you need from `l /usr/share/locale`

## Update
```bash
git pull
```
To update: just run that command again.
