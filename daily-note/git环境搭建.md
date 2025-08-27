# git环境搭建



## 1. 检查是否已有 SSH 密钥

打开终端（如：Windows Terminal、PowerShell、Git Bash、macOS/Linux Shell），运行：

```bash
ls -al ~/.ssh/
```
查看是否存在以下文件：

- id_rsa 和 id_rsa.pub（RSA 密钥）
- 或 id_ed25519 和 id_ed25519.pub（推荐，更安全）
>✅ 如果没有这些文件，请继续下一步生成密钥。
>❌ 如果已有密钥但不想保留，可先备份并删除。

```shell
ssh-keygen -t ed25519 -C "1162242058@qq.com"
# 启动 SSH Agent
eval "$(ssh-agent -s)"
# 添加你的私钥到 Agent
ssh-add ~/.ssh/id_ed25519
# Windows（Git Bash）
cat ~/.ssh/id_ed25519.pub
# 或使用 clip 命令直接复制到剪贴板
cat ~/.ssh/id_ed25519.pub | clip
# 测试
ssh -T git@github.com
```
```shell
git remote remove origin
git remote add origin 
git add .
git status
git commit -m "update"
git push -u origin main # 第一次push不知道上游分支是哪个，所以要加-u
git config --global push.autoSetupRemote true # git 2.37+版本可以自动设置上游分支
```