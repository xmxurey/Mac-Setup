# 3 Homebrew
Homebrew 自称是mac丢失的包管理工具。

## 安装
```shell
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
告诉系统使用Homebrew安装的应用
```shell
echo 'export PATH="/usr/local/sbin:$PATH"' >> ~/.zshrc
```

确认一切正常
```shell
brew doctor
```

## 使用 
* 安装软件, Homebrew叫Formula
```shell
brew install <formula>
```
* 更新
```shell
brew upgrade <formula>
```

```
brew install wget \
    git \
    ack \
    tree
```

## Homebrew-Cask

* 搜索
```
brew cask search <package>
```

Quick Look Plugins
```shell
brew cask install \
    qlcolorcode \
    qlstephen \
    qlmarkdown \
    quicklook-json \
    quicklook-csv \
    betterzip
```

App Suggestions
```
brew cask install \
    alfred \
    google-chrome \
    flux \
    1password \
    iterm2 \
    emacs \
    iina \
```
