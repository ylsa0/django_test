
#3.9 环境
FROM python:3.9
 
# 设置 python 环境变量
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

RUN groupadd web
RUN useradd -g web web

# 设置pypi源头为国内源
COPY pip.conf /root/.pip/pip.conf

# 在容器内/var/www/html/下创建 工作文件夹
ENV APP_HOME=/var/www/html/dj_test
RUN mkdir -p $APP_HOME
WORKDIR $APP_HOME

# 将当前目录文件拷贝一份到工作目录中（. 表示当前目录）
ADD . $APP_HOME

# 更新pip版本
RUN /usr/local/bin/python -m pip install --upgrade pip

# 利用 pip 安装依赖
RUN pip install -r requirements.txt

# Windows环境下编写的start.sh每行命令结尾有多余的字符，需移除。
RUN sed -i 's/\r//' ./start.sh

# 设置start.sh文件可执行权限
RUN chmod +x ./start.sh

# 数据迁移，并使用uwsgi启动服务
ENTRYPOINT /bin/bash ./start.sh