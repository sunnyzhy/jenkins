# Publish Over SSH 配置

## 1 安装 Publish Over SSH 插件

由于以下原因，Publish Over SSH 插件现被标记为已过时:

```
The following installed plugins are deprecated:
   Publish Over SSH

Publish Over SSH 1.22:
   Password stored in plain text
   Path traversal vulnerability
   CSRF vulnerability and missing permission checks
   Stored XSS vulnerability
```

[下载 Publish Over SSH 插件](https://github.com/sunnyzhy/jenkins/blob/main/plugins/publish-over-ssh.hpi 'Publish Over SSH')

## 2 系统配置

点击 ```Manage Jenkins -> Configure System```, 在系统设置的面板里找到 ```Publish over SSH``` 部分。

1. 配置 Jenkins SSH Key
   - Passphrase: 服务器的登录密码
2. 配置 SSH Servers
   - Name: 服务器名称
   - Hostname: 服务器的主机名或 IP 地址，一般使用 IP 地址
   - Username: 服务器的登录用户名
   - Remote Directory: 服务器上的远程目录，即上传的文件在远程服务器里所存储的起始目录，必须是已存在的目录，一般配置 ```/``` 即可。
   - 点高级，勾选 ```Use password authentication, or use a different key```

配置完成之后，点击 ```Test Configuration```，如果打印 ```Success```，则说明配置成功。

## 3 配置工作任务

其他步骤略过，只介绍构建后操作。

1. 选择 ```Send build artifacts over SSH```
2. 配置 SSH Server
   - Name: 选择在系统配置里所配置的服务器名称
2. 配置 Transfer Set
   - Source files: ```**/*``` 表示当前工作目录下所有的文件夹和文件; 多个文件之间用 ```逗号(,)``` 隔开, 比如: ```dir1/dir1-1/file1,dir2/dir2-1/file2,dir3/file3```; 可以点击当前工作任务的 ```工作空间``` 来查看其目录下的所有的文件夹和文件
   - Remove prefix: 针对上面配置的 Source files 目录，移除匹配的目录。
   - Remote directory: 服务器上的远程目录，可以是已存在或不存在的目录，如果是不存在的目录，会在服务器上自动创建。
   - Exec command: 远程服务器执行的命令。

文件上传到远程服务器的最终目录:

1. 没有配置 Remove prefix: ```系统配置的 Remote directory``` + ```工作任务配置的 Remote directory``` + ```Source files```
2. 配置了 Remove prefix: ```系统配置的 Remote directory``` + ```工作任务配置的 Remote directory``` + ```(Source files - Remove prefix)```
