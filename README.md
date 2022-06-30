# mac-setup

How do I setup my macOS

## Tools and configurations

_Please follow these steps below in order._

### iTerm

iTerm2 is a replacement for Terminal and the successor to iTerm. It works on Macs with macOS 10.14 or newer. iTerm2 brings the terminal into the modern age with features you never knew you always wanted.

Download from https://iterm2.com.

### Xcode Command Line Tools

This brings you some build tools such as the Apple LLVM compiler and Make. These tools make it easy to install open source software or develop on UNIX within terminal. macOS can automatically download these tools the first time you try to build software.

See the **Other tools included in macOS** section in https://developer.apple.com/xcode/features/ for more details.

Use `xcode-select --install` to install.

Alternatively, download the **Command Line Tools for Xcode** from [Apple Developer](https://developer.apple.com/download/all/) page.

_Note: You should download the lastet non-beta version._

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

See https://github.com/tonsky/FiraCode for more details.

Run these commands below to install:

```sh
brew tap homebrew/cask-fonts
brew install --cask font-fira-code
```

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

### zsh-syntax-highlighting

Clone this tool to Oh My Zsh's plugins directory:

```sh
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

Activate the plugin in `~/.zshrc`:

```sh
plugins=( [plugins...] zsh-syntax-highlighting)
```

See https://github.com/zsh-users/zsh-syntax-highlighting for more details.

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

## License

CC0-1.0
