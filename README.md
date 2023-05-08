# Tanks

https://bottledev.itch.io/tank

Source code for the Tanks game which can be played using the link above. 

# Summary

Tanks is a single player arcade style shooter where you play as a tank in a small arena and fend off a never-ending onslaught of enemy Tanks.

# Objective

The goal of developing Tanks was to recreate a game I had always loved as a kid, "Wii Tanks". The goal was to recreate the game but in a more arcade style as the source material uses a level system and I wasn't too keen on learning how to do levels so at the time I simply wanted to do an endless shooter in a single arena. Throughout development I ran into various roadblocks and issues which slowed down work and as such I cut down the scope of the project significantly to only one have one type of enemy.

# Gameplay

In it's current state the game offers an endless onslaught of enemy tanks to fight against and in the process you will earn score for killing each one. The tanks operate with the instruction of pathing towards the player, getting within firing range, aiming, and then firing at the player. They will continue to fire at the player until the player moves out of their maximum firing range, at which point they will begin the cycle once more. Rolling around and destroying the tanks is the only thing you can do as the player.

# Development

Due to this being one of my first projects in Unity, I had a tremendous amount to learn throughout development of the project. One of the biggest challenges was learning how to implement to enemy logic, I knew I wanted them to behave similarly to how they behave in "Wii Tanks" but in that game, the most basic of tank simply gets line of sight (LOS) and then begins to fire at your position, it does not lead or attempt to bounce the shells to have them hit you around corners. Given I was early in my learning, I chose to model this basic enemy in my game.

The first step of this involved figuring out how to get the enemy to move towards the player's position while avoiding obstacles. Having been in my last years of University, I was aware of various Pathfinding algorithms and had read that A* was very good for my use case. As such I did further research and found the A* Pathfinding Project for Unity. I implemented the solution for my use case and managed to get it working. 

Difficulty arose when I wanted to have the object navigate as a tank would. In that it should rotate to the desired direction and move smoothly along a curve. I chose to do this my implementing my own custom form of the pathfinding component in that mine would have the tank rotate towards the next waypoint, and then simply move in the direction it was facing, this would have it move in a curve manner more akin to that of a tank. After this it would check its distance to the next waypoint, and if close enough it would consume the waypoint and move onto the next one in the list. This gave the tanks a very nice smooth movement that to this day I am very proud of.

After this it was a matter of implementing a sort of state machine to control the enemy's actions. If a condition was met such as being within range of the player and having LOS, it would change to the firing state and engage the player.

# Conclusion

In the end, the game is very simple and barebones, the replayability is lacking the choice to have tanks on death emit an explosion of pixels resulted in a very difficult experience distinguishing between fired shells and destroyed tank fragments. Regardless, I am very proud of the game, it being one of my first, and would like to revisit it someday and see how I would change things with my newfound knowledge.
