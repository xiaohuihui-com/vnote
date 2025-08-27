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
```