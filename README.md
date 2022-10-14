# MobileRobot-Openloopcontrol
## Aim:

To develop a python control code to move the mobilerobot along the predefined path.

## Equipments Required:
1. RoboMaster EP core
2. Python 3.7

## Procedure

## Step1:

Initiate the MobileRobot.

## Step2:

Connect your PC with the MobileRobot through WiFi.

## Step3:

Open battery_level.py file and check the battery.

## Step4:

Open the other python files and program the movements of the robot using python.

## Step5:

Execute the python program and record the movements.

## Program:

```python
#Developed by: yuvabharathi
#Register no: 22002787

rom robomaster import robot
import time
from robomaster import camera

if _name_ == '_main_':
    ep_robot = robot.Robot()
    ep_robot.initialize(conn_type="ap")

    ep_chassis = ep_robot.chassis

    '''
    x = x-axis movement distance,( meters) [-5,5]
    y = y-axis movement distance,( meters) [-5,5]
    z = rotation about z axis ( degree)[-180,180]
    xy_speed = xy axis movement speed,( unit meter/second) [0.5,2]
    # '''

    ep_camera = ep_robot.camera
    ep_led = ep_robot.led

    print("Camera streaming started...")
    ep_camera.start_video_stream(display=True, resolution=camera.STREAM_360P)  

    ep_led.set_led(comp="all",r=255,g=0,b=0,effect="on")   
    time.sleep(2)
    


    ep_chassis.move(x=1.5, y=0, z=0, xy_speed=0.75).wait_for_completed()

    ep_chassis.move(x=0, y=0, z=-135, xy_speed=1).wait_for_completed()

    ep_chassis.move(x=1.7, y=0, z=0, xy_speed=0.75).wait_for_completed()

    ep_chassis.move(x=0, y=0, z=135, xy_speed=1).wait_for_completed()

    ep_led.set_led(comp="all",r=0,g=0,b=255,effect="on")
    time.sleep(2) 
   
    ep_chassis.move(x=1.5, y=0, z=0, xy_speed=0.75).wait_for_completed()
   
    ep_chassis.move(x=0, y=0, z=90, xy_speed=1).wait_for_completed()

    ep_chassis.move(x=1.5, y=0, z=0, xy_speed=0.75).wait_for_completed()

    ep_chassis.move(x=0, y=0, z=-50, xy_speed=0.75).wait_for_completed()

    ep_led.set_led(comp="all",r=0,g=255,b=0,effect="on")
    time.sleep(2)
    ep_chassis.drive_speed(x=0.3,y=0,z=20)
    time.sleep(12)
    ep_chassis.drive_speed(x=0,y=0,z=0)

    ep_camera.stop_video_stream()
    print("Stopped video streaming...")

    ep_robot.close()
 ```
    
## MobileRobot Movement Image:

## Initial position:

![3da455f5-37cb-4534-8edb-79a445f7d49e](https://user-images.githubusercontent.com/113497340/194830652-f808ca35-8b0d-4e45-a613-8b5883a38456.jpeg)

## Final position:

![e50e36a8-fab4-4c4c-9eb5-0fb922afc386](https://user-images.githubusercontent.com/113497340/194830729-5d2ad62b-c166-48e6-ba42-69c8441393fa.jpeg)



<br/>
<br/>
<br/>
<br/>

### MobileRobot Movement Video:



https://www.youtube.com/shorts/t8nVyGZvT7w

<br/>
<br/>
<br/>
<br/>

### Result:
Thus the python program code is developed to move the mobilerobot in the predefined path.

