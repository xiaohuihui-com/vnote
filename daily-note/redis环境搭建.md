# redis环境搭建
```shell
设置开机启动
1.进入redis目录
2.执行目录 将redis 注册为服务
redis-server --service-install redis.windows.conf --loglevel verbose
3、小tips：
卸载服务：redis-server --service-uninstall
开启服务：redis-server --service-start
停止服务：redis-server --service-stop
```