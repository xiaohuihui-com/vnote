# python 环境搭建

[toc]

## 0 uv 包管理

### 01.uv 环境配置

```shell
# windows安装
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
# 指定路径安装
powershell -ExecutionPolicy ByPass -c {$env:UV_INSTALL_DIR = "D:\uv_manager";irm https://astral.sh/uv/install.ps1 | iex}
```

```shell
# 临时镜像源安装
uv add numpy --default-index https://pypi.tuna.tsinghua.edu.cn/simple
```

```shell
# pyproject.toml 手动添加
[[tool.uv.index]]
url = "https://pypi.tuna.tsinghua.edu.cn/simple"
default = true
```
```shell
# python版本下载，临时加速镜像
uv python install 3.12 --mirror https://gitproxy.click/https://github.com/astral-sh/python-build-standalone/releases/download/ 
```

```shell
# windows永久镜像配置
$env:UV_DEFAULT_INDEX = "https://pypi.tuna.tsinghua.edu.cn/simple"
$env:UV_PYTHON_INSTALL_MIRROR = "https://gitproxy.click/https://github.com/astral-sh/python-build-standalone/releases/download/"
# PowerShell修改默认存储路径
$env:UV_CACHE_DIR = "E:\software\uv\uv_cache"
$env:UV_PYTHON_INSTALL_DIR = "E:\software\uv\uv_python"
$env:UV_TOOL_DIR = "E:\software\uv\uv_tool"
 
# cmd修改默认存储路径,立即生效
set UV_CACHE_DIR=E:\software\uv\uv_cache
set UV_PYTHON_INSTALL_DIR=E:\software\uv\uv_python
set UV_TOOL_DIR=E:\software\uv\uv_tool
set UV_PYTHON_INSTALL_MIRROR=https://gitproxy.click/https://github.com/astral-sh/python-build-standalone/releases/download/

# PowerShell永久设置
[Environment]::SetEnvironmentVariable("UV_CACHE_DIR", "E:\software\uv\uv_cache", "User")
[Environment]::SetEnvironmentVariable("UV_PYTHON_INSTALL_DIR", "E:\software\uv\uv_python", "User")
[Environment]::SetEnvironmentVariable("UV_TOOL_DIR", "E:\software\uv\uv_tool", "User")
# 解决警告
$env:UV_LINK_MODE= "copy"
# 验证
uv python dir
uv tool dir
uv cache dir
```

```shell
# C:\Users\Administrator\AppData\Roaming\uv\uv.toml 手动添加配置文件夹
python-install-mirror = "https://gitproxy.click/https://github.com/astral-sh/python-build-standalone/releases/download/"
[[index]]
url = "https://pypi.tuna.tsinghua.edu.cn/simple"
default = true
```
