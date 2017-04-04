# stepper_motor
关于升降平台控制系统
硬件包括单片机/四位数码管/步进电机/驱动器/电位器/网口转串口/按钮
机械部分
现阶段：
  1.对于步进电机的控制现阶段使用的是由电位器作为位置传感器确定机械升降平台的相对位置
  2. 由单片机通过AD转换将电阻阻值最终计算为机械平台的实际位置，并有数码管显示。
  3.其他包括上位机通过网口发送控制信号，就地控制。
可以改进的地方：
  1.步进电机工作原理决定了它并不需要闭环控制。因为步进电机所转角度与驱动脉冲的个数成正比，
  即步进电机转动一周所需要的驱动脉冲数为定值，并且在正常工作状态下不存在丢步于转动过量的问题。
  2.因未使用单片机eeprom，存在数据丢失问题，即不能做到现场调零，现阶段的解决办法为将电位器高点，低点固定于程序当中。
  若电位器发生漂移，机械故障，不能较快的处理问题。
建议：
  1.去掉电位器，通过脉冲数目对步进电机转动进行精确控制，加入高低限位。
  2.使用eeprom与高低限位相配合做到，零点现场可调。
  3.软件中加入平台高度输入，做到步进电机脉冲与实际高度的匹配。
  
总结：去掉电位器，步进电机不需要闭环控制
      加入限位开关
      使用EEPROM做到零点顶点可调
