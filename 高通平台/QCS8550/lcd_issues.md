1.  **modetest -M msm_drm -s 32@157:#0 -v**：测试单屏
2. **modetest -M msm_drm -s 32@157:#0 -s 57@218:#0 -v**：测试双屏
3. **cat /sys/kernel/debug/dri/0/state | grep -A5 "crtc\|connector\|DSI"**
4. **killall weston 2>/dev/null**：关闭桌面渲染终端