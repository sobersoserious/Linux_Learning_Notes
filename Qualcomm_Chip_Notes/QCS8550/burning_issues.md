# qcs8550芯片烧录问题

### 烧录命令记录：
1. **adb reboot edl**:适用于已经烧录过但想要重新烧录的场景，在宿主机运行即可
2. **lsusb**:可以通过lsusb查看板子是否进入edl模式，进入此模式意味着可以进行烧录工作
3. **adb devices**:查看板子是否烧录成功，如果烧录成功起成功重启会显示对应编号
4. **adb root**:转换为root身份
5. **adb shell**:进入板子的rootfs

### 关于烧录过程过久：
1. **解决办法**
    1. 检查**system.img**文件属性->**file system.img**
    2. 如果显示**Android sparse image**，而你用的是Linux LE firehose时就会出现卡死
    3. 正确做法是通过==simg2img system.img system_raw.img==的方式可以将**system.img**文件的还原为原始的**raw ext4 image**真实文件系统，此时修改对应的filehose文件例如：**rawprogram0.xml**将filename = "system.img"->"system_raw.img", sparse = "true"->"false"后执行
   > sudo qdl --storage ufs xbl_s_devprg_ns.melf rawprograw0.xml patch0.xml
   >> 注：具体烧录指令根据板子实际情况选择对应的文件
2. **原因**
    1. **Android sparse image**是一种传输格式，其本质是原始的**raw ext4 image**真实文件系统，他可以让刷机速度加快
    2. 通过**simg2img**工具可以褪去spase的外壳，此时修改filehouse文件指定不使用spase烧录，就可以使用原始烧录方式，避免出现不支持问题。
