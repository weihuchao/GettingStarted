# MacOS 

- googlechrome
- iTerm2
- ZSH
- LuLu
- Rectangle
- VSCode
  - https://github.com/ohmyzsh/ohmyzsh/wiki/themes

```bash
defaults write com.apple.dock springboard-columns -int 12
defaults write com.apple.dock springboard-rows -int 9
defaults write com.apple.dock ResetLaunchPad -bool TRUE
killall Dock
```
## Homebrew

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
brew install wget

time curl -Lo /dev/null https://formulae.brew.sh
time curl -Lo /dev/null https://mirrors.ustc.edu.cn
time curl -Lo /dev/null https://mirrors.tuna.tsinghua.edu.cn

curl -o /dev/null -s -w '建立连接: %{time_connect}s\n开始传输: %{time_starttransfer}s\n总共耗时: %{time_total}s\n' https://formulae.brew.sh
curl -o /dev/null -s -w '建立连接: %{time_connect}s\n开始传输: %{time_starttransfer}s\n总共耗时: %{time_total}s\n' https://mirrors.ustc.edu.cn
curl -o /dev/null -s -w '建立连接: %{time_connect}s\n开始传输: %{time_starttransfer}s\n总共耗时: %{time_total}s\n' https://mirrors.tuna.tsinghua.edu.cn

brew install doggo
doggo formulae.brew.sh
doggo mirrors.ustc.edu.cn
doggo mirrors.tuna.tsinghua.edu.cn

brew install mtr
sudo mtr -rw formulae.brew.sh
```

# GettingStarted

```bash
curl -fsSL https://openclaw.ai/install.sh | bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
echo 'eval "$(/usr/local/bin/brew shellenv zsh)"' >> ~/.zshrc
eval "$(/usr/local/bin/brew shellenv zsh)"
source ~/.zshrc
```

## Github

```bash
git config --global user.email "huchaoclaw@gmail.com"
git config --global user.name "Huchao Claw"
git remote -v
git remote set-url origin git@github.com:huchaoclaw/GettingStarted.git
gaa && gcmsg update && ggpush
```

```bash
# https://github.com/settings/keys
# https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#generating-a-new-ssh-key
mkdir -p ~/.ssh
ssh-keygen -t ed25519 -C "huchaoclaw@gmail.com" -f ~/.ssh/github
touch ~/.ssh/config

# Here Document（Heredoc）
cat <<EOF >> ~/.ssh/config
Host github.com
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/github
EOF

ssh-add --apple-use-keychain ~/.ssh/github
```

## Fast Node Manager

```bash
# https://github.com/Schniz/fnm
curl -fsSL https://fnm.vercel.app/install | bash

cat <<EOF >> ~/.zshrc
# FNM（Fast Node Manager）
eval "\$(fnm env --use-on-cd --shell zsh)"
EOF

安装: fnm install <版本号> 或 fnm install --lts (LTS版本)
切换: fnm use <版本号>
查看: fnm ls (已安装) 或 fnm ls-remote (远程)
默认: fnm default <版本号>
卸载: fnm uninstall <版本号> 

fnm install 24.14.0 --lts
```

## pyenv

```bash
brew install pyenv

echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
echo '[[ -d $PYENV_ROOT/bin ]] && export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(pyenv init - zsh)"' >> ~/.zshrc

# Install Python build dependencies
brew install openssl readline sqlite3 xz tcl-tk@8 libb2 zstd zlib pkgconfig

pyenv install -l
pyenv install 3.12

pyenv versions
pyenv version
pyenv global <version>

```

## pyenv-virtualenv

```bash
brew install pyenv-virtualenv
echo 'eval "$(pyenv virtualenv-init -)"' >> ~/.zshrc

pyenv virtualenv 2.7.10 my-virtual-env-2.7.10

pyenv activate <name>
pyenv deactivate

pyenv uninstall my-virtual-env
pyenv virtualenv-delete my-virtual-env
```