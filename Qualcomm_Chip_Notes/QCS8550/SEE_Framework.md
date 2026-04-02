# 配置流程：

#### 一、固件内添加DSP侧SEE驱动
#### 二、固件内配置传感器引脚
#### 三、AP侧屏蔽控制器和引脚配置
#### 四、AP侧添加.json文件
#### 五、ssc_sensor_info列出所有可用传感器(测试验证)


# .Json文件配置：
### 一、config
1. **hw_platform**：平台名称
2. **soc_id**：平台id

### 二、icm4x6xx_0
1. **is_dri**：是否开启中断
2. **hw_id**：多sensor实例编号，单sensor设置为0
3. **res_idx**：量程选择
4. **sync_stream**：是否和其他sensor同步输出

### 三、icm4x6xx_0_platform
#### .config
1. **bus_type**：0为I2C，1为SPI
2. **bus_instance**：控制器选择
3. **slave_config**：如果为I2C则填7为地址，如果为SPI则为CS片选: 0->CS0, 1->CS1
4. **min/max_bus_speed_khz**：总线速率限制
5. **reg_addr_type**：寄存器地址长度,0->8bit, 1->16bit
6. **dri_irq_num**：中断号
7. **irq_trigger_type**：中断属性，3为上升沿，4为下降沿
8. **viddo_rail**：供电rail名称
#### .orient
1. sensor坐标映射
#### .gyro/.accel
1. **corr_mat**：轴间误差校正
2. **bias**：offset补偿（零偏）
#### .temp
1. **scale**：温度缩放因子
#### .md
1. **thresh**：运动检测阈值
2. **disable**：是否关闭运动检测算法
3. **win**：在多长时间内统计加速度变化
#### .placement
1. 传感器在设备中的位置



