# WVR-Glove-Unreal-Engine-5.1-testing-ground
# Unreal Engine 5 testing ground
This repository contains the the unreal engine 5.1 project to try out the [WVR Glove](https://github.com/Wbiu/WVR-GLOVE-Firmware).

> **Note** : No VR component was used in this project and the whole grabbing and holding mechanism has to be build from the ground up.

## Before playing
A serial connection is used to communicate between unreal engine and the glove via a [this](https://github.com/videofeedback/Unreal_Engine_SerialCOM_Plugin) plugin.



Before playing the serial **port** and the **bound rate** needs to be set.<br/>
The **FFB Force** is at **0** ( off ) by default for safety reasons.
Content>VRTemplate>VRHands>Right_Hand>VR_Hand_Right_BP

![tmp](https://user-images.githubusercontent.com/112129893/227538976-968bbcab-3bd1-4951-bc09-568392b77d58.png)

After the connection is established the data set structure needs to be checked.<br/>
By default the project expect this data structure.
> **default data set structure**  " {255;255;255;255;255;100;100;100;1;2;3} "

* The First 5 data sets are the finger position [0-4].<br/> 
  Thumb;Index;Middle;Ring;Pinky
* The next 3 data sets are the IMU data sets [5-7].<br/>
  X;Y;Z
* And the last 3 are the position data sets [8-10].<br/>
  X;Y;Z

If you want to excluding or including any data sets you can change it in Content>SerialCOM>SerialCOM_BP

Example for excluding the position data sets :<br/> 
Simply disconnecting these nodes.

![exclude](https://user-images.githubusercontent.com/112129893/227539241-a0a45840-e6b7-42b4-bd11-823692caadec.png)
![bool exclude](https://user-images.githubusercontent.com/112129893/227539291-8105fe91-8ade-4776-ac6f-64455e0de6ca.png)


## Play
If every thing is set up the way you want it to be, then you should be able to start playing and grabbing stuff.<br/>
Since the **FFb Force** is turned off you won´t be able to feel any resistance if an object is grabbed.<br/>

By turning the **FFb Force** value up little by little, starting from 100, and increase the value by 10 each time you replay, the Force Feedback should get stronger if an object has been grabbed. The max **FFb Force** value is 255 ! 

> **Note** : this project is an early testing stage, so some unwanted behavior might occur.

Have fun playing ÒwÓ :)
![UE5 Greif Test _Trim](https://user-images.githubusercontent.com/112129893/228447222-9a7d7522-b9ad-4f0b-85b0-2efa980ad3ed.gif)

