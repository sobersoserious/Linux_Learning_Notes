### 一、环境构建时的网络问题
1. **git config --global http.proxy  http://172.17.0.1:1080**
2. **git config --global https.proxy http://172.17.0.1:1080**
3. **socat TCP-LISTEN:1080,bind=172.17.0.1,fork,reuseaddr TCP:127.0.0.1:1080 &**  ：TCP 端口转发（port forward / relay），用 socat 把一个代理端口“映射”到 Docker 可访问的地址上。