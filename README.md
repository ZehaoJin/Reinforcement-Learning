# Reinforced Learning
-Reinforced learning is about agent, environment, action, and reward: In an "environment"(or, a playfield), the deep learning neural network controls the "action" of an "agent" of our interest so that in the end the agent gets the highest "reward"! 
Take Mario game as an example, Super Mario himself is the agent, the map of the game is the environment and neural network gets the game controller to control our Mario's actions to achieve best reward--the highest game score.


-In this project, we want to use reinforced learning along with the Principle of least action to explore fundamental problems in Physics!
In physics, Action is the integral of Lagrangian over time. Nature tends to take the path where Action is smallest--principle of least action.

-Our idea is simple, use reinforced learning to minimize Action!




-Ideas are from dissusions between Joshua Yao-Yu Lin(https://github.com/joshualin24) and me!
-I learnt the basics of coding in reinforced leanring from Morvan Zhou's Reinforced Learning tutorial https://morvanzhou.github.io. Some code are modified from his examples(Maze and RobotArm).


 # Light Path--Principle of least action in reinforced learning
![](lightpathresult.gif)
-Light = blue box
-Initial position = yellow box
-final position = red box
-White background indicates index of refraction=1
-Grey background indicates index of refraction=1.3


-Physics: Light travels at different speeds in materials with different index of refraction. Given initial and final position, light     travels the path which takes shortest time. This is the reason behind the bending of light beams when light passes through the interface of two materials. The angles of incidence and refraction obeys Snell's Law, so that the "lightpath" will be shortest.

-Environment: Our agent--light(or a photon) can move freely in a 2-D continous map. i.e. it can move any Delta x and Delta z in x and z direction. Here it is just doing random brownian motion before any neural network training.
![](env.gif)

Reward: Within each episode(one run of training), we calculate the time consumed along the path. 
        Final reward∝-time consumed
        Final reward is zero if light does no reach goal position at all.
Intermediate reward: It gets some intermediate reward if it moves closer to the goal position. This intermediate reward greatly                              accelerates 
