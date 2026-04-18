### 常见调试工具和方法
1. **adb push 本地文件 板子路径**:用于宿主机发送文件给开发板
2. **adb pull 板子文件 本地路径**:用于开发板发送文件给宿主机(注：两个指令都是在宿主机上执行)

### lcd调试时出现drm被占用的问题
1. **killall weston 2>/dev/null**: 杀死weston占用的/dev/dri/card0,释放drm master，后续才能进行正常测试

### 串口调试工具screen
1. **sudo screen /dev/ttyUSB0 115200**:开启串口打印工具，接到/dev/ttyUSB0口，波特率为115200
2. **sudo screen -L -Logfile serial.log /dev/ttyUSB0 115200**:-L：开启日志功能 -Logfile serial.log：指定日志文件名

### 安卓自带抓取log工具指令
1. **adb shell logcat -b all**:查看系统实时log信息(但是只能在系统运行时查看，无法实时查看开机和关机的log)
2. **adb shell logcat -b all -c**:清空所有缓存区log信息，如果不想抓取老旧的log信息可以使用。
3. **adb shell logcat -b all > logcat.txt**:把系统的log信息重定向到logcat.txt文件中，用于保存记录log信息

### 交叉编译器相关问题
1. **source /usr/local/rb-perf-x86_64/environment-setup-aarch64-oe-linux**:source <交叉编译器的绝对路径>:可以让目前这个终端能够进行交叉编译
2. **$CC <文件名> -o <编译结果名>**:执行source后交叉编译命令示例。*CC*：环境变量，一般指针对C文件的交叉编译器，类似还有*CXX*:针对CPP文件的交叉编译器。可以通过echo $环境变量名 :查看环境变量内容
3. **$CC <文件名> -o <编译结果名> -I/usr/.../libdrm -ldrm**:如果出现缺少某个头文件，可以使用这个方法,示例：-I<路径> 添加头文件搜索路径 -l<库名> 链接libdrm库