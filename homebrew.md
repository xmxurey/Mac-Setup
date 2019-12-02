# 3 Homebrew

Homebrew 自称是mac丢失的包管理工具。

## 安装

```text
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

告诉系统使用Homebrew安装的应用

```text
echo 'export PATH="/usr/local/sbin:$PATH"' >> ~/.zshrc
```

确认一切正常

```text
brew doctor
```

## 使用

* 安装软件, Homebrew叫Formula

  ```text
  brew install <formula>
  ```

* 更新

  ```text
  brew upgrade <formula>
  ```

```text
brew install wget \
    git \
    ack \
    tree
```

## Homebrew-Cask

* 搜索

  ```text
  brew cask search <package>
  ```

Quick Look Plugins

```text
brew cask install \
    qlcolorcode \
    qlstephen \
    qlmarkdown \
    quicklook-json \
    quicklook-csv \
    betterzip
```

App Suggestions

```text
brew cask install \
    alfred \
    google-chrome \
    flux \
    1password \
    iterm2 \
    emacs \
    iina \
```

