```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
echo 'eval "$(/usr/local/bin/brew shellenv zsh)"' >> ~/.zshrc
eval "$(/usr/local/bin/brew shellenv zsh)"
source ~/.zshrc

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

## Xcode

```bash
# https://xcodereleases.com/
Xcode 15.2 Last For MacOS 13.5+
# 解压后拖到应用中
```

## ffmpeg

```bash
brew install ffmpeg
```
