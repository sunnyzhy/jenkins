# Profile

## 源码管理

一定要提前安装好相应的源码管理插件，如 Subversion

## Maven 安装

打开 ```Manage Jenkins -> System Configuration -> Tools -> Maven 安装```，新增 Maven，然后配置 MAVEN_HOME 为 Maven 的安装目录。

## Maven 配置

打开 ```Manage Jenkins -> System Configuration -> Tools -> Maven 配置```，配置默认的 settings.xml 和全局的 settings.xml。

## JDK 安装

jenkins 的版本是高版本，但是项目使用的版本是 jdk8。在这样的情况下，就需要配置 jdk：

打开 ```Manage Jenkins -> System Configuration -> Tools -> JDK 安装```，新增 JDK，然后配置 JAVA_HOME 为 jdk8 的安装目录。

