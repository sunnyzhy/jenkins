## This account either does not hava the privilege to logon as a service or the account was unable to be verified

打开 ```控制面板 -> 系统和安全 -> 管理工具 -> 本地安全策略 -> 本地策略 --> 用户权限分配 --> 作为服务登录```，添加当前登录用户。

## Service 'Jenkins' (Jenkins) failed to start. verify that you have sufficient privileges to start

打开 ```计算机管理 -> 服务-> jekins -> 右键属性 -> 登录```，选择 ```本地系统用户登录``` 即可。

## 无法登录

如果出现以下情况，就可能导致无法登录：

- 忘记管理员admin账号密码
- 管理员admin账号登录权限丢失/全局角色被删除(一般都是操作不当引起的)

### 解决方案

#### 没有改过 admin 密码

1. 进入 ```.jenkins/secrets``` 目录，打开initialAdminPassword 文件，复制密码；

2. 访问Jenkins页面，输入管理员admin，以及刚才复制的默认初始密码；

3. 登录管理员admin账号之后便可更改所有用户密码及权限。

#### 改过 admin 密码但是忘记了

1. 打开 ```.jenkins``` 安装目录下的 ```config.xml``` 文件，并备份
2. 注释以下代码（不同版本可能略有不同），并保存文件
   ```
   <!--
   <useSecurity>true</useSecurity>
   <authorizationStrategy class="hudson.security.FullControlOnceLoggedInAuthorizationStrategy">
     <denyAnonymousReadAccess>true</denyAnonymousReadAccess>
   </authorizationStrategy>
   <securityRealm class="hudson.security.HudsonPrivateSecurityRealm">
     <disableSignup>true</disableSignup>
     <enableCaptcha>false</enableCaptcha>
   </securityRealm>
   -->
   ```
3. 重启Jenkins服务

