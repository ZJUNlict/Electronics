# Electronics

 ZJUNlict Electronics Design for the Robocup Soccer Small-Size League https://zjunlict.cn/
 

The electronics design covers the overall control of the hardware based on a team's strategy program. The detailed tasks for the electronics include driving motors, wireless communication, charging and discharging capacitors for shooting and chipping. 

There are three configurations of electrical systems shown in the Table below currently used in ZJUNlict robots. 

![Electronics Configurations](./Images/Configurations.PNG)

The single Cyclone III FPGA configuration was adopted since 2012 and explained in [2013 and 2014 champion papers](https://zjunlict.cn/?page_id=54). The FPGA handles both motor control and other tasks such as communication and motion sensor fusion based on embedded Nios II processor. 

The micro-controller STM32F407 was added to take over tasks other than motor control since late 2017 described in [2018 ETDP](https://zjunlict.cn/?page_id=54). 

Since 2018, a single micro-controller STM32H743 capable of operation frequency up to 400MHz combined with five BLDC controller Allegro A3930 was able to handle all the tasks.

Other improvements include increasing each encoder's counts per revolution (CPR) to increase motor low-speed control performance, implementation of the accelerometer and compass to achieve more accurate motion tracking and switching to nRF24L01+ wireless IC to deliver higher bandwidth communication with better signal sensitivity.

Please check each board also with possible corresponding firmware based on the following table. The archive of all the opensourced repositories can be found in [our website](https://zjunlict.cn/?page_id=54).

|                            | Since 2012           | Since 2017                       | Since 2018 |
|----------------------------|----------------------|----------------------------------|------------|
| Robot Configurations       | [Core Board](https://github.com/ZJUNlict/Core_Board)           | [Core Board FPGA & STM32](https://github.com/ZJUNlict/Core_Board_FPGA_STM32)          | [Main Board](https://github.com/ZJUNlict/Main_Board) |
|                            | [Core Board Firmware](https://github.com/ZJUNlict/Firmware_for_Core_Board)  | [Core Board FPGA & STM32 Firmware](https://github.com/ZJUNlict/Firmware_for_Core_Board_FPGA_STM32) |         (Combined into Main Board)   |
|                            | [Mother Board](https://github.com/ZJUNlict/Mother_Board)         | [Main Board Test](https://github.com/ZJUNlict/Main_Board_Test)                  |   (Combined into Main Board)  |
|                            | [Motor Driver Board](https://github.com/ZJUNlict/Motor_Driver_Board)   | (Combined into Main Board Test)                    |    (Combined into Main Board)        |
|                            | [Booster Board](https://github.com/ZJUNlict/Booster_Board)        |     (Same)                   |     (Same)       |
|                            |                      |                                  |            |
| Transmitter Configurations | [Transmitter](https://github.com/ZJUNlict/Transmitter)          | [Network Transmitter](https://github.com/ZJUNlict/Network_Transmitter)              |            |
|                            | [Transmitter Firmware](https://github.com/ZJUNlict/Firmware_for_Transmitter) | [Network Transmitter Firmware](https://github.com/ZJUNlict/Firmware_for_Network_Transmitter)     |            |
|                            |                      |                                  |            |
|  Communication Protocols   |                      |                                  | [Protocol V2018](https://github.com/ZJUNlict/Wireless_Communication_Protocol) |
|                            |                      |                                  |   |

All of the boards are designed using [Altium Designer](https://www.altium.com/altium-designer/).

The details of how to use the firmware can be found in each firmware's repository.