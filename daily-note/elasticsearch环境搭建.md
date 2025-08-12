# elasticsearch环境搭建


```shell
1.系统环境配置ES_HOME  
2.修改yaml配置数据和日志路径
3.重置密码
elasticsearch-reset-password.bat -u elastic
4.修改初始密码：NILHPtGtGhRiHs78PAla
curl.exe -XPUT -H 'Content-Type: application/json' -u elastic:NILHPtGtGhRiHs78PAla 'http://localhost:9200/_security/user/elastic/_password' -d'{\"password\":\"yjbsk123\"}'
5.注册服务
elasticsearch-service.bat install
6.验证密码修改是否成功
curl.exe -u elastic http://localhost:9200
7.启动服务
net start elasticsearch-service-x64
```
