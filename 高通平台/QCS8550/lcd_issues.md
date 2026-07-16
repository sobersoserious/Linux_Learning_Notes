### 一、测试指令
1.  **modetest -M msm_drm -s 32@157:#0 -v**：测试单屏
2. **modetest -M msm_drm -s 32@157:#0 -s 57@218:#0 -v**：测试双屏
3. **killall weston 2>/dev/null**：关闭桌面渲染终端
4. **modetest -M msm_drm -c**：查看对应屏幕的connector ID
5. **modetest -M msm_drm -e**：查看可用encoder，possible crtcs为0x01则只能选择第0个CRTC,0xff则都可以使用
6. **cat /sys/kernel/debug/dri/0/state**：查看当前所有的crtc和connector，并实时显示目前占用的设备

### 二、移植流程
1. 配置panel参数文件
2. 将文件加入common设备树中
3. 在板级设备树文件中加入节点，内容包括时钟，电源，引脚配置，背光变化值
4. 更改默认pinctrl设置
5. 更改默认屏幕：qcom,dsi-default-panel = <&>;
6. disable掉无关节点配置
7. 注释或禁用bootloader中配置的自启动屏幕，（可通过源码false）
8. 禁用“splash 接管”，相关节点：splash_memory