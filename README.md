# GettingStarted

```bash
curl -fsSL https://openclaw.ai/install.sh | bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
echo 'eval "$(/usr/local/bin/brew shellenv zsh)"' >> ~/.zshrc
eval "$(/usr/local/bin/brew shellenv zsh)"
source ~/.zshrc
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