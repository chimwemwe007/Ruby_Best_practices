# Ruby installation instructions

#### Select your platform
1. [MacOS](#macOS)
2. [Ubuntu](#ubuntu)
3. [Windows](#windows)

#### Tools on Unix based systems
There are several tools that can be used to install Ruby on your local machine. The most popular are:

- rbenv
- RVM
- asdf

We will go with rbenv because it does not override any of the system shell scripts like RVM and it allows us to compile older Ruby versions that will fail with RVM.

#### MacOS
Firstly read [this](#toolsonunixbasedsystems), then run the following commands in your terminal:
```bash
brew install rbenv ruby-build
# Add rbenv to bash so that it loads every time you open a terminal
echo 'if which rbenv > /dev/null; then eval "$(rbenv init -)"; fi' >> ~/.bash_profile
source ~/.bash_profile

# Install Ruby
rbenv install 3.0.1
rbenv global 3.0.1
ruby -v
```

This example shows how to install `Ruby 3.0.1` which was the latest version in April 2021, but you can check to see if there is a newer version [here](https://www.ruby-lang.org/en/downloads/releases/). We also assumed that you have [homebrew](https://brew.sh) already installed on your Mac.

Note:
If you are using a shell other than bash, for example zsh, you should change the first line to use `zshrc` like this:
```
echo 'if which rbenv > /dev/null; then eval "$(rbenv init -)"; fi' >> ~/.zshrc
```
or any other config file of your shell.

#### Ubuntu
Firstly read [this](#toolsonunixbasedsystems), then run the following commands in your terminal:
```
git clone https://github.com/rbenv/rbenv.git ~/.rbenv
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(rbenv init -)"' >> ~/.bashrc
exec $SHELL

git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
echo 'export PATH="$HOME/.rbenv/plugins/ruby-build/bin:$PATH"' >> ~/.bashrc
exec $SHELL

rbenv install 3.0.1
rbenv global 3.0.1
ruby -v
```
This example shows how to install `Ruby 3.0.1` which was the latest version in April 2021, but you can check to see if there is a newer version [here](https://www.ruby-lang.org/en/downloads/releases/).

Here is an useful article  that can help you with the installation: [Install ruby on Ubuntu 20.04 with rbenv](https://linuxtut.com/install-ruby-on-ubuntu-20.04-with-rbenv-e419f/).

#### Windows
Installing Ruby on Windows is a little more difficult than installing it on another OS. We would recommend using [WSL](https://docs.microsoft.com/en-us/windows/wsl/about), but you can also try to install Ruby directly on your OS with [rubyinstaller](https://rubyinstaller.org).

##### Note:
`WSL only works on 64-bit installations of Windows.`

If you are using a 54-bit version of Windows 10, we recommend following [this](https://gorails.com/setup/windows/10) article to install Ruby.

If you can not use WSL then you should follow these steps:
1. Download the last version of [RubyInstaller](https://rubyinstaller.org/downloads/).
2. Run RubyInstaller and follow the steps described [here](https://stackify.com/install-ruby-on-windows-everything-you-need-to-get-going/).

If you are familiar with [docker](https://www.docker.com), you could also use it.

------

_If you spot any bugs or issues in this activity, you can [open an issue with your proposed change](https://github.com/microverseinc/curriculum-transversal-skills/blob/main/git-github/articles/open_issue.md)._
