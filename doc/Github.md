## Setting

```bash
git config --global user.email "huchaoclaw@gmail.com"
git config --global user.name "Huchao Claw"

git config --global user.email "weihuchao@gmail.com"
git config --global user.name "Huchao Wei"

git remote -v
git remote set-url origin git@github.com:huchaoclaw/GettingStarted.git

gaa && gcmsg update && ggpush
git add . && git commit -m update && git push

git config pull.rebase false
```

### Windows

```bash
cd /d/Code/GettingStarted
git status
git diff
git add . && git commit -m update && git push
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