### 环境构建时的网络问题
1. **ss -tlnp | grep 1080**：查找宿主机的地址
2. **netstat -rn | awk '$1=="0.0.0.0"{print $2}'**：查找docker的地址
3. **git config --global http.proxy  http://172.17.0.1:1080**
4. **git config --global https.proxy http://172.17.0.1:1080**
5. **socat TCP-LISTEN:1080,bind=172.17.0.1,fork,reuseaddr TCP:127.0.0.1:1080 &**  ：TCP 端口转发（port forward / relay），用 socat 把一个代理端口“映射”到 Docker 可访问的地址上。