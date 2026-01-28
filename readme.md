# mac-setup

How do I setup my macOS

## Essential tools and configurations

_Please follow these steps below in order._

### iTerm

iTerm2 is a replacement for Terminal and the successor to iTerm. It works on Macs with macOS 10.14 or newer. iTerm2 brings the terminal into the modern age with features you never knew you always wanted.

Download it from https://iterm2.com.

### Warp

Warp is a modern, Rust-based terminal with AI built in so you and your team can build great software, faster.

Download it from https://warp.dev.

### Xcode Command Line Tools

This brings you some build tools such as the Apple LLVM compiler and Make. These tools make it easy to install open source software or develop on UNIX within terminal. macOS can automatically download these tools the first time you try to build software.

See the **Other tools included in macOS** section in https://developer.apple.com/xcode/features/ for more details.

Use `xcode-select --install` to install.

Alternatively, download the **Command Line Tools for Xcode** from [Apple Developer](https://developer.apple.com/download/all/) page.

_Note: You should download the latest non-beta version._

### Z shell

Zsh is a shell designed for interactive use, although it is also a powerful scripting language. Many of the useful features of bash, ksh, and tcsh were incorporated into zsh; many original features were added.

Apple replaced `bash` with `zsh` as the default shell since macOS Catalina.

See https://support.apple.com/en-us/HT208050.

### Oh My Zsh

It's a delightful, open source, community-driven framework for managing your Zsh configuration.

Follow https://ohmyz.sh to install.

### Enable syntax for Vim

```sh
echo "syntax on" >> ~/.vimrc
```

### Homebrew

It's a free and open-source software package management system that simplifies the installation of software.

Follow https://brew.sh to install.

### Fira Code

It's a free monospaced font containing ligatures for common programming multi-charactor combinations.

Run these commands below to install:

```sh
brew tap homebrew/cask-fonts
brew install --cask font-fira-code
```

See https://github.com/tonsky/FiraCode for more details.

### Pure

It's a pretty, minimal and fast ZSH prompt.

Run these commands below to install:

```sh
brew install pure
```

If you're not using ZSH from Homebrew (`brew install zsh` and `$(brew --prefix)/bin/zsh`), you must also add the site-functions to your `fpath` in `$HOME/.zshrc`:

```sh
fpath+=("$(brew --prefix)/share/zsh/site-functions")
```

Initialize the prompt system (if not so already) and choose `pure`:

```sh
# .zshrc
autoload -U promptinit; promptinit
prompt pure
```

You can find some other installation methods and its documentation from https://github.com/sindresorhus/pure.

### zplug

A next-generation plugin manager for zsh.

```sh
brew install zplug
```

In order to use zplug, please add the following to your `.zshrc`:

```sh
export ZPLUG_HOME=/opt/homebrew/opt/zplug
source $ZPLUG_HOME/init.zsh
```

See https://github.com/zplug/zplug for more details.

### zsh-syntax-highlighting

This provides syntax highlighting for the shell zsh. It enables highlighting of commands whilst they are typed at a zsh prompt into an interactive terminal.

Install the plugin with `zplug`:

```sh
zplug add "zsh-users/zsh-syntax-highlighting"
```

See https://github.com/zsh-users/zsh-syntax-highlighting for more details.

### bat

A cat(1) clone with syntax highlighting and Git integration.

```sh
brew install bat
```

### autojump

`autojump` is a faster way to navigate your filesystem. It works by maintaining a database of the directories you use the most from the command line.

_Directories must be visited first before they can be jumped to._

Homebrew is the recommanded installation method for macOS:

```sh
brew install autojump
```

Activate the plugin in `~/.zshrc`:

```sh
plugins=( [plugins...] autojump)
```

See https://github.com/wting/autojump for more details.

## Git

### .gitconfig

```conf
[gpg]
	program = gpg
[commit]
	gpgsign = true
[alias]
	br = branch
	ci = commit
	co = checkout
	cp = cherry-pick
	dc = clean -dfX
	lg = log --color --graph --pretty=format:'%Cred%h%Creset %C(bold blue)%an%Creset%C(yellow)%d%Creset %s %Cgreen(%cr)' --abbrev-commit
	ll = log --color --no-merges --author-date-order --pretty=format:'%Cred%h%Creset %C(bold blue)%an%Creset%C(yellow)%d%Creset %s %Cgreen(%cr)' --abbrev-commit
	sco = sparse-checkout
	st = status
[core]
	excludesfile = /Users/litomore/.gitignore-global
[pull]
	ff = only
[filter "lfs"]
	required = true
	clean = git-lfs clean -- %f
	smudge = git-lfs smudge -- %f
	process = git-lfs filter-process
[remote "origin"]
	prune = true
[pager]
	branch = false
[diff "lockb"]
	textconv = bun
	binary = true
```

## Recommended tools and configurations

- [Alfred](https://www.alfredapp.com) - Alfred is an award-winning app for macOS which boosts your efficiency with hotkeys, keywords, text expansion and more.
- [Raycast](https://raycast.com) - A collection of powerful productivity tools all within an extendable launcher. Fast, ergonomic and reliable.
- [GitHub Desktop](https://desktop.github.com) - Focus on what matters instead of fighting with Git. Whether you're new to Git or a seasoned user, GitHub Desktop simplifies your development workflow.
- [Magnet](https://apps.apple.com/us/app/magnet/id441258766) - Every time you multitask with many apps open, you need all the windows arranged accordingly. Magnet makes this process swift and easy.
- [Userscripts](https://github.com/quoid/userscripts) - Userscripts is an open source Safari extension that lets you save and run arbitrary bits of JavaScript (and CSS) code for the websites you visit.

## License

CC0-1.0
