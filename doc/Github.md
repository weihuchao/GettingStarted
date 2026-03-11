## Setting

```bash
git config --global user.email "huchaoclaw@gmail.com"
git config --global user.name "Huchao Claw"
git remote -v
git remote set-url origin git@github.com:huchaoclaw/GettingStarted.git
gaa && gcmsg update && ggpush
```

## Keys

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