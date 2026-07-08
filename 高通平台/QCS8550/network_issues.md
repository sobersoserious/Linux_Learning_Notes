### 开发板上网络配置问题
1. **ip link show**：查看板子上所有网络
2. **vi /.../wpa_supplicant.conf**:编辑wifi网络配置文件ssid="WIFI名称",psk="WIFI密码"
3. **wpa_supplicant -B -i wlan0 -c /.../wpa_supplicant.conf**:启动wpa_supplicant,-i指定网络接口，-B指定后台运行，-c指定配置文件路径
4. **udhcpc -i wlan0**:客户端通过DHCP获取IP地址