# MobileRobot-Openloopcontrol
## Aim:

To develop a python control code to move the mobilerobot along the predefined path.

## Equipments Required:
1. RoboMaster EP core
2. Python 3.7

## Procedure

### Step1: 
import the required modules : time, robomaster - robot & camera 
### Step2:
Initialize the robomaster to create the objrct to access the robomaster and specify the connection type here access point
### Step3:
Connect the robomaster using the created object using chassis
### Step4:
Create objects to access the LED & Camera and start the video stream
### Step5:
Measure the track and convert into units, that is 1unit = 1metre and specifiy the direction axis,speed and rotation based on the position of the robomaster after each successful statement 
### Step6:
Also change LED colors after each statement to know that each statement has been completed
### Step7:
After the robomaster has completed traversing through the track end the video streaming and close the robot object

## Program
~~~
from robomaster import robot
import time
from robomaster import camera

if _name=='__main_':
    ep_robot=robot.Robot()
    ep_robot.initialize(conn_type="ap")

    ep_chassis = ep_robot.chassis
    ep_led = ep_robot.led
    ep_camera = ep_robot.camera
    print("Video streaming started.....")
    ep_camera.start_video_stream(display=True, resolution = camera.STREAM_360P)
    
    ep_led.set_led(comp = "all",r=255,g=0,b=0,effect="on")
    ep_chassis.move(x=2.8,y=0,z=0,xy_speed=0.75).wait_for_completed()
    ep_chassis.move(x=0,y=0,z=45,xy_speed=0.75).wait_for_completed()
    ep_led.set_led(comp = "all",r=0,g=0,b=255,effect="on")

    ep_chassis.move(x=0.5,y=0,z=0,xy_speed=0.75).wait_for_completed()
    ep_led.set_led(comp = "all",r=0,g=255,b=0,effect="on")
    ep_chassis.move(x=0,y=0,z=45,xy_speed=0.75).wait_for_completed()
    ep_led.set_led(comp = "all",r=255,g=0,b=255,effect="on")

    ep_chassis.move(x=0.5,y=0,z=0,xy_speed=0.75).wait_for_completed()
    ep_led.set_led(comp = "all",r=255,g=204,b=0,effect="on")
    ep_chassis.move(x=0,y=0,z=45,xy_speed=0.75).wait_for_completed()
    ep_led.set_led(comp = "all",r=0,g=204,b=255,effect="on")

    ep_chassis.move(x=0.5,y=0,z=0,xy_speed=0.75)wait_for_completed()
    ep_led.set_led(comp = "all",r=0,g=192,b=0,effect="on")
    ep_chassis.move(x=0,y=0,z=45,xy_speed=0.75).wait_for_completed()
    ep_led.set_led(comp = "all",r=255,g=0,b=255,effect="on")

    ep_chassis.move(x=0.9,y=0,z=0,xy_speed=0.75).wait_for_completed()
    ep_led.set_led(comp = "all",r=0,g=255,b=255,effect="on")
    ep_chassis.move(x=0,y=0,z=-35,xy_speed=0.75).wait_for_completed()
    ep_led.set_led(comp = "all",r=255,g=0,b=255,effect="on")

    ep_chassis.move(x=1.9,y=0,z=0,xy_speed=0.75).wait_for_completed()
    ep_led.set_led(comp = "all",r=0,g=0,b=255,effect="on")
    ep_chassis.move(x=0,y=0,z=35,xy_speed=0.75).wait_for_copleted()
    ep_led.set_led(comp = "all",r=0,g=192,b=0,effect="on")

    ep_chassis.move(x=1.44,y=0,z=0,xy_speed=0.75).wait_for_completed()
    ep_led.set_led(comp = "all",r=0,g=255,b=255,effect="on")
    ep_chassis.move(x=0,y=0,z=10,xy_speed=0.75).wait_for_completed()
    ep_led.set_led(comp = "all",r=255,g=0,b=255,effect="on")

    ep_chassis.move(x=0,y=-2.1,z=0,xy_speed=0.75).wait_for_completed()
    ep_led.set_led(comp = "all",r=0,g=192,b=0,effect="on")
    ep_chassis.move(x=0,y=0,z=-10,xy_speed=0.75).wait_for_completed()
    ep_led.set_led(comp = "all",r=0,g=0,b=255,effect="on")

    ep_chassis.move(x=-0.55,y=0,z=0,xy_speed=0.75).wait_for_completed()
    ep_led.set_led(comp = "all",r=255,g=0,b=255,effect="on")
    ep_chassis.move(x=0,y=0,z=180,xy_speed=0.75).wait_for_completed()
    ep_led.set_led(comp = "all",r=0,g=204,b=255,effect="on")
    time.sleep(4)

    ep_camera.stop_video_stream()
    print("Stopped video streaming.....")
    ep_robot.close()
~~~
## MobileRobot Movement Image:

![robo](./img/robomaster.png)

## MobileRobot Movement Video:

Youtube Link : https://youtu.be/7Jd60ljt67c


## Result:
Thus the python program code is developed to move the mobilerobot in the predefined path.


```
Mobile Robotics Laboratory
Department of Artificial Intelligence and Data Science/ Machine Learning
Saveetha Engineering College
```
