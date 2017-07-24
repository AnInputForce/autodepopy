# 基础镜像
FROM python:2.7
# 维护者信息
MAINTAINER kang.cunhua <kangcunhua@git.com.cn> 
# app 所在目录
WORKDIR /usr/src/web/autodeploy
ADD ../ /usr/src/web/
# 安装 app 所需依赖
RUN pip install  \
	--no-cache-dir -r requirements.txt  \
	-i http://mirrors.aliyun.com/pypi/simple/ --trusted-host mirrors.aliyun.com 