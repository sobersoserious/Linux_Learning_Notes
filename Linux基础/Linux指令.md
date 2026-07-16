### 一、解压缩相关：
1. **unzip**：文件名 -d 目录名：解压文件到指定目录

### 二、网络相关：
1. **env | grep -i proxy**：查看当前关于代理环境的配置
2. **/etc/resolv.conf**：关于DNS的配置信息，但一般是软链接，不能直接在文件修改
3. **/etc/hosts**：本地静态域名解析表，绕过 DNS，直接指定域名对应哪个 IP
4. **resolvectl status**：查看本机真实的DNS域名
5. **ss -lntp | grep 1080**：查看监听1080端口的设备，1080就是自己vpn的端口信息
6. **socat TCP-LISTEN:1080,bind=172.17.0.1,fork,reuseaddr TCP:127.0.0.1:1080 &**  ：TCP 端口转发，用 socat 把一个代理端口“映射”到 Docker 可访问的地址上，前提是docker配置好了代理信息
7. **docker网络路径**：容器 172.17.0.2 ---> docker0 172.17.0.1 ---> 宿主机 NAT ---> 宿主机 wlp2s0 192.168.1.177 ---> 路由器 192.168.1.1 ---> 网络      但是他用不了宿主机代理，所以需要监听
8. **git config --global http.proxy <u>http://xxx.xx.x.x:1080</u>**：配置用户git全局代理
9. **git config --global --unset http.proxy git config --global --unset https.proxy**：取消用户git全局代理