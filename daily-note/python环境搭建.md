# python环境搭建
[toc]




## 0 uv包管理
### 01.uv环境配置
```shell
# windows安装
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
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
# windows永久镜像配置
 $env:UV_DEFAULT_INDEX = "https://pypi.tuna.tsinghua.edu.cn/simple"
 $env:UV_PYTHON_INSTALL_MIRROR = "https://ghfast.top/https://github.com/astral-sh/python-build-standalone/releases/download"
# 修改默认存储路径 
 $env:UV_CACHE_DIR = "E:\software\uv\uv_cache"
 $env:UV_PYTHON_INSTALL_DIR = "E:\software\uv\uv_python"
 $env:UV_TOOL_DIR = "E:\software\uv\uv_tool"
# 解决警告
 $env:UV_LINK_MODE= "copy"
```

```shell
# C:\Users\Administrator\AppData\Roaming\uv\uv.toml 手动添加配置文件夹
[[index]]
url = "https://pypi.tuna.tsinghua.edu.cn/simple"
default = true
```

