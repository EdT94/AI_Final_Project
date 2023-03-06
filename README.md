# AI_Final_Project

The teams start the game in two different rooms, each team in a different room. Each team has 2 types of NPC's: Warriors and Armor bearers. Every NPC calculates his path to target every A_STAR_ITERATION steps(see definitions in "main.h" and "NPC.h").

------------------------------------------------------------------------------------------------------------------------------
Warrior:
Each warrior has 3 states: "Attack", "RunAway", and "Idle".

Attack:
If the warrior has more than MIN_HP health points & MIN_AMMO ammunition. Always focuses on the closest enemy, starting to shoot towards the enemy if the distance between them is less than FAR_DISTANCE_FROM_ENEMY. As a result, enemy health points decrease by FAR_SHOT_DAMAGE. If the distance between the warrior and the enemy is less than ClOSE_DISTANCE_FROM_ENEMY, it can throw a grenade towards him and the enemy would die immediately, or it can shoot towards the enemy and the enemy health points will be decreased by CLOSE_SHOT_DAMAGE.

RunAway: 
If the warrior has lower health points than MIN_HP or lower ammunition than MIN_AMMO, he will go towards his armor bearer to pick from him what he needs and the armor bearer will go towards him to help, or towards closest health points storage/ ammunition storage, if it is closer than the armor-bearer.

Idle: 
From this state, we move to 2 other states, depending on the health points and ammunition values.
------------------------------------------------------------------------------------------------------------------------------
Armor-bearer:
Always moving from "Idle" to "RunAway" state. When in the "RunAway" state, look for the closest health points and ammunition storages and pick them. can carry up to MAX_HP_STORAGE_CARRIAGE health points storages and up to MAX_AMMO_STORAGE_CARRIAGE ammunition storages. When a teammate is in need of health points or ammunition and he is close enough, he takes what he needs and the health storage number of the armor bearer decreases by 1. The armor-bearer can use one of his health storages if his health points are lower than MIN_HP.



![ezgif com-gif-maker](https://user-images.githubusercontent.com/81565589/179821440-f98e7155-c66c-43ba-af1e-fdac423944ce.gif)
