# Configure your Development Environment

This guide takes you from a default MacOS computer to a fully-functioning PK&C development environment that will allow you to work on any and all PK&C projects.

## System Requirements

Your computer should be some sort of Apple product running OSX 10.14 or later, preferring OSX 11.0 or later. It should have a 2-core i5 processor or better, at least 8 GB of RAM, and at least 10GB of available storage space.

## First Installs

All installs will be run through the terminal. Depending on your processing power and internet connection, this next section will take between 30 and 90 minutes to complete.

If some of this software is new to you, don't worry, it is very commonly used open source software installed on all PK&C computers and will not harm your devices. During the installation process, give any passwords, sudo privileges, extra downloads, and so on requested by the software you're installing.

If you run into any issues, ask a developer and we'll find a solution and update this documentation accordingly.

### Essentials

First, you may need to update your shell to ZSH. In terminal, run `chsh -s /bin/zsh`. If after running this it says "no changes made" that's fine, it means you were already using the correct shell.

Download VSCode from Microsoft here: [https://code.visualstudio.com](https://code.visualstudio.com).

Follow this guide [https://code.visualstudio.com/docs/setup/mac](https://code.visualstudio.com/docs/setup/mac)

Install any extensions it prompts you for (e.g. Python) as well as the Live Share application.

Make sure you have a [GitHub account](https://github.com) with an SSH key enabled: [https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent](https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent).

### Python

1. Install Homebrew: [https://brew.sh](https://brew.sh). Homebrew is a package manager and will also install XCode developer tools if needed as part of the installation process.
   1. If you already have homebrew installed, instead run `brew update` and `brew upgrade`.
   2. This is the longest and slowest-running of the installations, grab a snack or stretch your legs.
2. Install pyenv using Homebrew. This will let us leave your system Python alone. In terminal, run `brew install pyenv`.
3. Install the proper version of Python via pyenv. Right now, that is 3.7.10. Run `pyenv install 3.7.10`.
4. Set this as your global Python version with `pyenv global 3.7.10`.

Add the following to your ~/.zshrc file with command `code ~/.zshrc`.

```
export PYENV_ROOT="$HOME/.pyenv"
export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init --path)"

export WORKON_HOME=~/.virtualenvs
export PROJECT_HOME=~/Code
source /Users/YOURUSERNAME/.pyenv/versions/3.7.10/bin/virtualenvwrapper.sh
```

### Node.js

Install Node.js.

Add the following Node-related stuff with `code ~/.zshrc`.

```
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
```