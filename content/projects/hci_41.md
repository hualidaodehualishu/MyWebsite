+++ 
date = "2023-01-30"
title = "Play in VR"
+++

##Play in VR
I developed VR games with my classmates in this one lab. VR games are highlighted by immersive play, and during the development process I discovered differences from many general 3D games, such as the user experience and the sense of vertigo to be taken into account in VR games.
Unlike developing general 3D games, developing VR requires special development kits, XR interaction and foundation, which are two important kits in XR, by using them we can get scripts such as XR input, XR interactable, etc., simplifying the burden of game developers. Another difference is that XR has its own game target, XR Origion, so you need to remove the original camera to work, the most important point is that you need to start XR Plugin in the project setting, many students forget to start during the development process, resulting in no response to enter the game
![截屏2023-01-30 03.41.26.png](https://s2.loli.net/2023/01/30/Zzaech86rXW4TEo.png)
My colleagues and I first developed the left and right hands of the VR character, considering the user's experience, a realistic hand model can make the user feel pleasant and realistic, in addition, a hand with feedback and animation will make the game more comfortable compared to a static hand, the following is a picture of the user's hand that we developed.
![截屏2023-01-30 03.46.58.png](https://s2.loli.net/2023/01/30/3yJzXTgNiQV5DoM.png)
Then an important feature in VR games is interaction with objects. In XR games, there is often remote interaction and direct interaction, and given the importance, my companion and I kept both, triggering different interaction modes through different buttons on the controller and different objects. Likewise, teleportation is essential, which can reduce the user's vertigo, so we also developed the teleportation function, and here are pictures of the related functions.

Finally, to make the game more interesting, we created a simple scene based on the previous lab scene and added an attractive object - a pistol, again, we added animations for the pistol to make it more realistic, the following is a demo video:
https://youtu.be/x-4LteGI6TA


##Some Difficulties 
During the development process, the problems encountered mainly come from the interaction with objects, such as the position of the object and the distance, and the deviation of the position of the object held in the hand. In addition, the steering in the process of moving, continuous movement is easy to make the user feel dizzy, in the future development needs to pay more attention to the details of the movement to reduce the user's discomfort.

