## APP

- [Chome]()
- [iTerm2](https://iterm2.com/)
- [ZSH](https://ohmyz.sh/)
  - https://github.com/ohmyzsh/ohmyzsh/wiki/themes

- [LuLu](https://objective-see.org/products/lulu.html)
- [Rectangle](https://rectangleapp.com/)
- [VSCode](https://code.visualstudio.com/)
- [The Unarchiver](https://theunarchiver.com/)
- [ClashX](https://en.clashx.org/)
- [AppCleaner](https://freemacsoft.net/appcleaner/)
- [FannyWidget](https://www.fannywidget.com/)
- [Stats](https://mac-stats.com/)


## Setting

```bash
defaults write com.apple.dock springboard-columns -int 12
defaults write com.apple.dock springboard-rows -int 9
defaults write com.apple.dock ResetLaunchPad -bool TRUE
killall Dock
```

## ZSH

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

## passwd

```bash
$ pwpolicy -clearaccountpolicies
$ passwd
```

## 

```bash
# MacOS 13 清空右侧的通知弹窗 命令行
sfltool resetbtm

killall NotificationCenter
```

