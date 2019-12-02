# 5 Git

安装

```text
brew install git
```

config

```text
git config --global user.name "Your Name Here"
git config --global user.email "your_email@youremail.com"
```

## Git Ignore \(global\)

新建 `~/.gitignore`

```text
# Folder view configuration files
.DS_Store
```

```text
git config --global core.excludesfile ~/.gitignore
```

