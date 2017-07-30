# 基础镜像
FROM python:2.7-slim
# 维护者信息
MAINTAINER kang.cunhua <kangcunhua@git.com.cn> 
# app 所在目录
WORKDIR /usr/src/web
ADD . /usr/src/web
# 安装 app 所需依赖,做一些清理工作
RUN	buildDeps='gcc'; \ 
	deveDeps='mysql-client'; \ 
	set -x \
	&& cp /etc/apt/sources.list /etc/apt/sources.list.backup \
	&& mv sources.list /etc/apt/sources.list \
	&& apt-get update && apt-get install -y libmysqlclient-dev $buildDeps $deveDeps \
	# When using Python 2.7, please install IPython 5.x LTS Long Term Support version.
	&& pip install --no-cache-dir -r requirements.txt ipython==5.4.1 \
	-i http://mirrors.aliyun.com/pypi/simple/ --trusted-host mirrors.aliyun.com  \
	&& rm -rf requirements.txt \
	# 移除gcc
	&& apt-get purge -y --auto-remove $buildDeps