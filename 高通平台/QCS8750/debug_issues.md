### 一、查看设备树信息
1. **/sys/firmware/devicetree/base/soc/qcom,qupv3_2_geni_se@8c0000/spi@884000**：查看该节点信息

### 二、分析产出文件辅助调试
1. **dtc -I dtb -O dts -o fdt.dts fdt**：板子启动后位于/sys/firmware/fdt,可以用来反汇编出.dts文件查看烧录到板子上的设备树节点配置信息

### 三、串口测试
1. **stty -F /dev/ttyHS2 -a**：查看串口信息
2. **cat /dev/ttyHS1 | hexdump -C**：hex接收