# dotfiles

个人 shell 配置备份。换电脑时 `git clone` + `./install.sh` 即可恢复工作环境。

## 文件说明

| 文件 | 用途 |
|------|------|
| `zshrc` | zsh 主配置（Oh My Zsh 主题、插件、alias、PATH） |
| `install.sh` | 将 `zshrc` 复制到 `~/.zshrc` 的安装脚本 |

## 安装

```bash
git clone git@github.com:longxinjun-ai/dotfiles.git ~/dotfiles
cd ~/dotfiles
./install.sh
source ~/.zshrc
```

## 依赖（新机器需先安装）

| 工具 | 安装 | 作用 |
|------|------|------|
| [Oh My Zsh](https://ohmyzsh.sh/) | 官方安装脚本 | zsh 框架与主题 |
| fzf | `brew install fzf` | 模糊搜索（历史/文件/目录） |
| zoxide | `brew install zoxide` | 智能目录跳转 |
| bat | `brew install bat` | 带高亮的 cat 替代 |
| eza | `brew install eza` | 现代 ls 替代 |
| zsh-autosuggestions | `brew install zsh-autosuggestions` | 命令自动建议 |
| zsh-syntax-highlighting | `brew install zsh-syntax-highlighting` | 命令语法高亮 |

## Alias 一览

| alias | 实际命令 | 作用 |
|-------|----------|------|
| `ls` | `eza --group-directories-first` | 列出文件，目录优先显示 |
| `ll` | `eza -la --group-directories-first` | 详细列表（含隐藏文件） |
| `cat` | `bat --paging=never` | 带语法高亮查看文件，不分页 |

## 快捷键（fzf）

| 按键 | 作用 |
|------|------|
| `Ctrl-R` | 模糊搜索命令历史 |
| `Ctrl-T` | 模糊搜索文件 |
| `Alt-C` | 模糊跳转到目录 |

## 其他配置

- **主题**：Oh My Zsh `robbyrussell`
- **插件**：`git`（Oh My Zsh 内置）
- **PATH**：追加 `$HOME/.npm-global/bin`（OpenCode CLI）
- **BAT_THEME**：`ansi`

## 更新流程

改配置后同步到 GitHub：

```bash
# 1. 编辑仓库里的源文件
vim ~/dotfiles/zshrc

# 2. 安装到本机并生效
./install.sh && source ~/.zshrc

# 3. 提交推送
git add . && git commit -m "update: 描述改了什么" && git push
```
