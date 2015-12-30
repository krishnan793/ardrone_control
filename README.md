# ardrone_control
[Acknowledgement:This is a forked repository of mikehammer.]
I have added a new brach ardrone_control which is for ROS indigo. This branch will act as a source of python modules that can be used in any project involving AR Drone. Also this package can be used to control your ARDrone using a gamepad [Tested with: Logitech F710].
```
Action            Button No

ButtonEmergency = 0
ButtonLand      = 1
ButtonTakeoff   = 2

ButtonChangeCam = 3       # Toggle camera view
ButtonStartSendCommand = 7# Start using gamepad
ButtonStopSendCommand = 6 # Stop using gamepad

AxisRoll        = 0       # Left Analog Stick
AxisPitch       = 1
AxisYaw         = 3       # Right Analog Stick
AxisZ           = 4
```
To start using gamepad run,
```
rosrun joy joy_node
```
In an another terminal run,
```
rosrun ardrone_control joystick_controller.py
```

Tips for using the module
-------------------------
```
from drone_controller import BasicDroneController

controller = BasicDroneController()
controller.StartSendCommand()
controller.SendTakeoff()
controller.ChangeCam()
controller.SetCommand(1,0,0,0)  
controller.SendLand()
controller.StopSendCommand()
```
