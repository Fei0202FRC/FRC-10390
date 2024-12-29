# FRC-10390
import wpilib

class Robot(wpilib.TimedRobot):
    def robotInit(self):
        # 初始化继电器
        self.relay = wpilib.Relay(0)  # 继电器连接到继电器端口0
        self.relay.set(wpilib.Relay.Value.kForward)  # 上电时打开指示灯

    def teleopInit(self):
        # 遥控模式初始化
        wpilib.SmartDashboard.putString("Status", "Teleop Initialized")

    def teleopPeriodic(self):
        # 遥控模式周期性代码
        pass

    def disabledInit(self):
        # 禁用模式初始化
        self.relay.set(wpilib.Relay.Value.kOff)  # 关闭指示灯

if __name__ == "__main__":
    wpilib.run(Robot)
    
