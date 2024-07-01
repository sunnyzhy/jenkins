## This account either does not hava the privilege to logon as a service or the account was unable to be verified

打开 ```控制面板 -> 系统和安全 -> 管理工具 -> 本地安全策略 -> 本地策略 --> 用户权限分配 --> 作为服务登录```，添加当前登录用户。

## Service 'Jenkins' (Jenkins) failed to start. verify that you have sufficient privileges to start

打开 ```计算机管理 -> 服务-> jekins -> 右键属性 -> 登录```，选择 ```本地系统用户登录``` 即可。
