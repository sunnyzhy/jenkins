# Subversion

## 1 安装 Subversion 插件

1. 点击 ```Manage Jenkins -> Manage Plugins, 打开 Plugin Manager 面板。
2. 选择 ```可选插件```，搜索 Subversion。
3. 勾选 Subversion，点击 ```Install without restart```，即可完成安装。

## 2 配置 svn 凭据

1. 点击 ```Manage Jenkins -> Manage Credentials -> 凭据 -> 域 -> 添加凭据```, 打开凭据面板。
2. 选择类型 ```Usernam with password```。
3. 配置账号、密码。

## 3 配置工作任务

其他操作略过，只介绍源码管理。

1. 选择 ```Subversion```
2. 配置 Modules
   - Repository URL:  svn 仓库地址。
   - Credentials: 选择配置的 svn 凭据。
