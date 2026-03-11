# MacOS 

- googlechrome
- iTerm2
- ZSH
- LuLu
- Rectangle
- VSCode


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
```

```bash
# https://github.com/settings/keys
# https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#generating-a-new-ssh-key
mkdir -p ~/.ssh
ssh-keygen -t ed25519 -C "huchaoclaw@gmail.com" -f ~/.ssh/github
touch ~/.ssh/config

Host github.com
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/github

ssh-add --apple-use-keychain ~/.ssh/github
```