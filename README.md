# Docker 知识点

## Docker 入门

1. 查看Docker 是否存在： docker info 
2. 创建容器：docker run，参数i保证润琪中STDIN（标准输入）是开启的，参数t分配一个伪tty终端
3. 查看系统进程: ps -aux
4. 查看系统网络配置: ip a
5. docker ps 可以查看目前运行的容器， -l参数会列出最后一次运行的容器， 包括正在运行和已经停止的， -a参数可查看当前系统中容器的列表
6. 附着到容器上：docker attach， 可能需要按下回车才能进入该会话
7. 创建守护式容器：在创建容器的时候添加-d参数
8. 查看容器log：docker logs 参数t可以添加时间戳，f可以监控Docker日志
9. 查看容器内的进程 docker top
10. 在容器内部运行进程：docker exec 可新建后台进程
11. 自动重启容器：--restart 参数有 always、onfailure（可以有重启次数）
12. 获取容器更多信息 inspect ,也可以添加-f或者--format表示来选定查看结果

## Docker 镜像和仓库
1. 拉取镜像 docker pull
2. 构建镜像：sudo docker build -t="镜像名:版本" Dockerfile 位置
3. 容器端口 -p 宿主机端口:容器端口，也可以通过在端口绑定时使用/udp后缀来指定UDP端口
4. CMD 用于指定一个容器启动时要运行的命令，使用docker run命令可以覆盖CMD命令，在Dockerfile中只能指定一个CMD命令
5. ENTYPOINT 不容易被docker run命令覆盖，可以在docker run 中指定参数传递给ENTYPOINT
6. WORKDIR 用来在从镜像穿件一个新的容器时，在容器内部设置一个工作目录，ENTYPOINT和/或者CMD指定的程序会在这个目录下进行
7. ENV 用来在镜像构建过程中设置环境变量，docker run 中可以使用-e标志来传递环境变量
8. ENTRYPOINT/CMD都只能在文件中存在一次，并且最后一个生效 多个存在，只有最后一个生效，其它无效！
9. 从src复制文件到container的dest路径:ADD <src> <dest>
10. VOLUME 命令:VOLUME ["<mountpoint>"]如:VOLUME ["/data"]创建一个挂载点用于共享目录
11. ADD 多了2个功能, 下载URL和解压.  其他都一样.如果你不希望压缩文件拷贝到container后会被解压的话, 么使用COPY.如果需要自动下载URL并拷贝到container的话, 请使用ADD.



