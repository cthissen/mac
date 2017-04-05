# macOS Sierra v. 10.12 Setup 

*12/29/16*

[View a more detailed explanation of these steps here.](https://www.taniarascia.com/setting-up-a-brand-new-mac-for-development/)

## Preferences

- **Keyboard > Text >** Disable "Correct spelling automatically".
- **Security and Privacy > Firewall >** On
- **Security and Privacy > General >** App Store and identified developers
- **File Sharing >** Off
- **Users & Groups > Login Items >** Spectacle, Flux

### Disable Game center deamon
```shell
defaults write com.apple.gamed Disabled -bool true
```

### Show Library folder

```shell
chflags nohidden ~/Library
```

### Show hidden files

This can also be done by pressing `command` + `shift` + `.`.

```shell
defaults write com.apple.finder AppleShowAllFiles YES
```

### Show path bar

```shell
defaults write com.apple.finder ShowPathbar -bool true
```

### Show status bar

```shell
defaults write com.apple.finder ShowStatusBar -bool true
```

## Homebrew

```shell
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

### Mac App Store

```shell
brew install mas
```

#### Sign in

```shell
mas signin email@email.com
```

### Brewfile

```shell
touch Brewfile
```

```shell
# to run: brew bundle install 
tap 'caskroom/cask'
tap 'caskroom/fonts'

'rsync'

cask 'flux'
cask 'firefox'
cask 'google-chrome'
cask 'google-drive'
cask 'font-inconsolata'
cask '1password'
cask 'dropbox'
cask 'spotify'
cask 'skype'

mas 'Slack', id: 803453959
mas 'Sip', id: 507257563 
```

## Python
pip install virtualenv
pip install virtualenvwrapper
export WORKON_HOME=~/Envs
source /usr/local/bin/virtualenvwrapper.sh
pip install ipython

## GitHub

### Config - `~/.gitconfig`


```shell
[user]
	name = First Last
	email = email@email.com
[github]
	user = username
[alias]
	a = add
	ca = commit -a
	cam = commit -am
	s = status
	pom = push origin master
	pog = push origin gh-pages
	puom = pull origin master
	puog = pull origin gh-pages
	cob = checkout -b
[credential]
	helper = osxkeychain
```


## SSH

### Config - `~./ssh/config`

```shell
Host example
    HostName example.com
    User example-user
    IdentityFile key.pem
```

### Generate SSH key

```shell
ssh-keygen -t rsa -b 4096 -C "email@email.com"
```

## Bash

### Config - `~/.bash_profile`

```shell
alias brewup='brew update; brew upgrade; brew prune; brew cleanup; brew doctor'
```

```shell
source ~/.bash_profile
```

## Node Package Manager

### Gulp

```shell
npm install --global gulp-cli
```

## Ruby Version Manager

### Download rvm

```shell
\curl -sSL https://get.rvm.io | bash -s stable
```

### Install Ruby version

```shell
rvm install 2.3.3
```

```shell
gem install bundler
```

