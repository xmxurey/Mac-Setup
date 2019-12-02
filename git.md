# 5 Git

安装
```
brew install git
```

config
```shell
git config --global user.name "Your Name Here"
git config --global user.email "your_email@youremail.com"
```

## Git Ignore (global)
新建 `~/.gitignore`
```
# Folder view configuration files
.DS_Store
```

```
git config --global core.excludesfile ~/.gitignore
```

