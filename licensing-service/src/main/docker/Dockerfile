# 这是 Docker运行时使用的Linux Docker镜像。此安装对Java应用程序进行了优化
FROM openjdk:8-jdk-alpine
# 安装 nc（netcat），可以使用这个实用工具ping依赖服务，以查看它们是否已启动
RUN  apk update && apk upgrade && apk add netcat-openbsd
RUN mkdir -p /usr/local/licensingservice
# Docker ADD 命令将可执行JAR从本地文件系统复制到Docker镜像
ADD @project.build.finalName@.jar /usr/local/licensingservice/
# 添加一个自定义BASH shell脚本，它将监视服务依赖项，然后启动该服 务
ADD run.sh run.sh
RUN chmod +x run.sh
CMD ./run.sh
