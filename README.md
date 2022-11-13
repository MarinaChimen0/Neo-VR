# Neo VR: A VR multiplayer experience for improving team working

[See a video demonstration clicking here](https://youtu.be/fe8MAGTPMJ0)

This project was developed at Hospital virtual Valdecilla (HvV) following the need of finding a more immersive way of training NEO (name possible contributions, stablish roles and orient in tasks), an algorithm for managing team working situations. Until now, for learning and applying this scheme, HvV instructors use to propose a roleplay where the players were outside the hospital, isolated from other persons and someone had got injured. They had to manage the situation together, naming the objects and abilities they had and talking about what they should do.

The previous experience achieved by the Innovation area of HvV applying virtual reality to surgery guidance and individual training, made us think that if they were using VR glasses, we could improve this kind of training sessions and made the players feel more in connection with the problem they had to deal with, and how the algorithm could help them. We had the challenge of the HvV courses’ attenders having totally different backgrounds, ages and levels of technology skills. Moreover, in general they are not usual video game players, so we had to work with easily understandable mechanics. 

Therefore, we wanted to make a game that was concise to avoid the possible dizziness effect on new VR users, and easy to play to decrease the amount of time needed in the learning controls process. We decided to have the maximum amount of two buttons, in addition to the movement of the headset and controllers, to be able to play the game. One of the buttons would be the right joystick, to allow the movement through the scenario. Although the game was going to allow movement of the character just by walking, HvV building hasn’t got a room with enough space to allow a safe gameplay. With the second button, we needed to give the users a way of interacting with the scenario, and the triggers of the controllers seemed an intuitive way of managing the opening of the hands and allowing grabbing objects.

On the other side, although we couldn’t control the course of the players’ conversation, we wanted to design a game context that would lead them towards using the NEO algorithm. In order to achieve that, their steps were taken in deeply consideration. Starting with the idea of pushing the players to name their possible contributions to solve the problem, I suggested the team the idea of creating a scenario in which each player had its own isolated space with exclusive objects, forcing them to have a conversation about their respective items. 

We started a design process considering different scenarios that would allow this on a team context, and finally we decided to set the game in a vacation resort on the sea, where players would be in different bungalows, having these bungalows a rope connecting system to let the players pass their objects to others. Following this concept, I created the bungalows with different decorations and purposes in order to make the players talk about in which kind of room they were, and to give context to different sets of items. At the same time, the placement of these objects, implied that players would likely adopt different roles to solve the problem in less time, assuring the application of the next step of the NEO algorithm.

The game was built in a time slot of 6 months, with me being the only developer, using Unity as the game engine and C# as the programming language. At HvV, we were moving in the direction of using Oculus Quest 2 as our VR equipment, because of the possibilities that brings you a VR headset that has wireless autonomy. Therefore, if the glasses weren’t going to be connected to a computer, we needed to use their WiFi connection in order to have a team experience. Since the training was always going to have place at HvV, I decided to go for a WLAN connection, instead of an online session, avoiding latency problems.  

Because of confidential reasons, the code of this project cannot be shared, but some aspects of the development can be discussed:
- In terms of creating a VR application, I chose the OpenXR Plugin for Unity, an open standard developed by Khronos whose aim is to simplify VR/AR development allowing developers to target a wide range of devices. Since VR is a constantly evolving industry, I though making the game compatible with the main VR headsets brands would give it a longer lifespan.  
- To develop the controllers’ behaviour, I used the Unity XR Interaction Toolkit package, an interaction system which provides a framework that makes 3D/UI interactions available from Unity input events. It contains a set of base Interactor and Interactable components, and an Interaction Manager to tie them together. This package also allows cross-platform XR controller input.
- In order to make a multiplayer experience, I worked with Mirror library. Mirror is a high-level Networking library for Unity, compatible with different real-time low-level transports, that provides useful functionalities within a client-server model. I customized the Interactor, Interactable and Interaction Manager classes from the XR Interaction Toolkit with them to achieve spreading the players’ interactions across the network.
- As it has been previously mentioned, I decided to go for a local area network instead of an online server. In the first testing phases, I discovered that using one client as the host server could cause problems: as soon as the Oculus headset lost the play area configured, the server used to shut down. For that reason, I decided to use a computer as the dedicated server and have the VR headsets just as clients. Therefore, the same game has two different builds: for PC and for Android, with an initial menu that lets you both create a game server or connect to one already created.
