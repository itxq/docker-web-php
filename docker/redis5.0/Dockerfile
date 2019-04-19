FROM redis:5.0-alpine

MAINTAINER IT小强xqitw.cn <mail@xqitw.cn>

# 设置时区
ENV TZ=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
