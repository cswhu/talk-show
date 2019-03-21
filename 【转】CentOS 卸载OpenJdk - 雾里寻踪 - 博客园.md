【转】CentOS 卸载OpenJdk - 雾里寻踪 - 博客园
https://www.cnblogs.com/zsxfbj/archive/2010/09/22/CentOS_Unstall_OpenJDK.html



CentOS 7 - 安装Oracle JDK8 - Lloyd的专栏 - CSDN博客
https://blog.csdn.net/SanCava/article/details/82661001





yum提示another app is currently holding the yum lock;waiting for it to exit - 分享的滋味 - CSDN博客
https://blog.csdn.net/lyc_daniel/article/details/11064881







学习笔记：Centos6.5永久修改DNS的方法 - 谢育政的博客 - CSDN博客
https://blog.csdn.net/hjxzt1/article/details/73741425





# Centos如何安装 Oracle JDK8

## 卸载

安装好的CentOS会自带OpenJdk,用命令 java -version ，会有下面的信息：

java version "1.6.0"
OpenJDK  Runtime Environment (build 1.6.0-b09)
OpenJDK 64-Bit Server VM (build 1.6.0-b09, mixed mode)

最好还是先卸载掉openjdk,在安装sun公司的jdk.



先查看 rpm -qa | grep java





显示如下信息：

java-1.4.2-gcj-compat-1.4.2.0-40jpp.115
java-1.6.0-openjdk-1.6.0.0-1.7.b09.el5

卸载：

rpm -e --nodeps java-1.4.2-gcj-compat-1.4.2.0-40jpp.115
rpm -e --nodeps java-1.6.0-openjdk-1.6.0.0-1.7.b09.el5

还有一些其他的命令

rpm -qa | grep gcj

rpm -qa | grep jdk

如果出现找不到openjdk source的话，那么还可以这样卸载

 yum -y remove java java-1.4.2-gcj-compat-1.4.2.0-40jpp.115
 yum -y remove java java-1.6.0-openjdk-1.6.0.0-1.7.b09.el5

## 下载文件安装

 yum localinstall -y jdk-8u201-linux-x64.rpm





CentOS 7 - 安装Oracle JDK8 - Lloyd的专栏 - CSDN博客
https://blog.csdn.net/SanCava/article/details/82661001



## 配置环境变量
```
/usr/java/jdk1.8.0_201-amd64
# User specific environment and startup programs

export JAVA_HOME=/usr/java/jdk1.8.0_201-amd64/
export JRE_HOME=/usr/java/jdk1.8.0_201-amd64/jre
```




## 验证是否安装成功










