# ~~Mathias~~ Hontas dotfiles
> Forked from [https://github.com/mathiasbynens/dotfiles](https://github.com/mathiasbynens/dotfiles)

## Installation

### 0.5 SSH

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

### 1. Clone and run bootstrap script
```bash
git clone git@github.com:hontas/dotfiles.git && cd dotfiles && source bootstrap.sh
```

### 2. Install nvm
See updated instructions at [https://github.com/creationix/nvm](https://github.com/creationix/nvm)
```bash
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.2/install.sh | bash
```

### 3. Install Homebrew formulae

Install `homebrew` and `brew-cask`
```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
brew tap caskroom/cask
brew tap caskroom/versions
```

When setting up a new Mac, you may want to install some common [Homebrew](http://brew.sh/) formulae:
```bash
./brew.sh
```

### 4. Add sensitive settings in `~/.extra`
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

### 5. Sensible OS X defaults

When setting up a new Mac, you may want to set some sensible OS X defaults:

```bash
./.osx
```

## Update
```bash
git pull
```
To update: just run that command again.
