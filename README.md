# Profile

**vue 环境无须单独安装 node 或 nvm，使用 Jenkins 的 NodeJS 插件即可。**

## 插件安装

一定要提前安装好相应的插件，如：

- 源码管理插件，如 Subversion
- Maven
- Java SE Development Kit (JDK) 
- NodeJS

## Maven 配置

打开 ```Manage Jenkins -> System Configuration -> Tools -> Maven 配置```，配置默认的 settings.xml 和全局的 settings.xml。

## Maven 安装

打开 ```Manage Jenkins -> System Configuration -> Tools -> Maven 安装```，新增 Maven，然后配置 MAVEN_HOME 为 Maven 的安装目录。

## JDK 安装

jenkins 的版本是高版本，但是项目使用的版本是 jdk8。在这样的情况下，就需要配置 jdk：

打开 ```Manage Jenkins -> System Configuration -> Tools -> JDK 安装```，新增 JDK，然后配置 JAVA_HOME 为 jdk8 的安装目录。

## NodeJS 安装

打开 ```Manage Jenkins -> System Configuration -> Tools -> NodeJS 安装```，新增 NodeJS，然后配置相应的 ```别名、版本以及相应版本 NodeJS 的安装目录```。

**注：可配置多个 NodeJS 版本，用于不同的编译环境。**

## 配置源

### 配置全局 Maven settings.xml

打开 ```Manage Jenkins -> System Configuration -> Managed files -> Add a new config -> Global Maven settings.xml -> Edit Configuration File```，在 Content 里配置 Maven 源。

### 配置 Maven settings.xml

打开 ```Manage Jenkins -> System Configuration -> Managed files -> Add a new config -> Maven settings.xml -> Edit Configuration File```，在 Content 里配置 Maven 源。

### 配置 npm 源

打开 ```Manage Jenkins -> System Configuration -> Managed files -> Add a new config -> Npm config file -> Edit Configuration File```，在 Content 里配置 ```registry = https://registry.npmmirror.com```。
