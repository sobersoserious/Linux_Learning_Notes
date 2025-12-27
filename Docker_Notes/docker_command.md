### 常用命令记录

1. **docker exec -it -u build 容器名 /bin/bash**:用于在已启动的容器新开一个shell终端，build可替换为root身份进入
2. **docker stop 容器名**:停止docker
3. **docker start 容器名**：开启容器
4. **docker restart 容器名**：重启容器
5. **docker rm 容器名**：删除容器，注：会将容器中修改的设置和数据全部清除，再次打开容器就是原始状态，一般不会使用