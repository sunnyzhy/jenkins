# 简介

jenkins 的版本是高版本，但是项目使用的版本是 jdk8。在这样的情况下，就需要配置 jdk：

打开 ```Manage Jenkins -> System Configuration -> Tools -> JDK 安装```，新增 JDK，然后配置 JAVA_HOME 为 jdk8 的安装目录。

