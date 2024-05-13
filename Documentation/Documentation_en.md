
# Sigma Drive

## 1. Game Description
Sigma Drive is a game created for the "invent your game 2024" competition, inspired by the "ryan gosling drive meme". It is an endless first person driving game in which you drive a car on a straight road. The goal in the game is to be a sigma, get a score for dangerous driving, and earn money and upgrade your car. Good luck on the road.


## 2. Build Instructions
- Open (or install) Unity Hub
- In the upper right corner, click "Add" and select the "Sigma Drive Project" folder
- Install Unity 2022.3.17f1 if not installed
- Open "Sigma Drive Project"
- After launching the project editor, go to File->Build Settings
- In "Build Settings" in the lower right corner, click "Build" or "Build And Run"
- Select the folder where the compiled game will be located
- After compilation is complete, launch the game if it did not start automatically

## 3. Launch Instructions
- There is a compiled version of the game in the "Sigma Drive" folder
- To run the game, open the "Sigma Drive.exe" file


## 4. Tutorial
### a. Controls
Sigma Drive can be played with a keyboard and mouse or a joystick

Keyboard:
- Use mouse, WSAD or arrow keys to navigate the menu
- Press lmb or enter to select
- Press esc to exit
- Use W / S or ArrowUp / ArrowDown to accelerate / decelerate
- Use A/D or ArrowLeft/ArrowRight to steer your car
- Press Space to pause

Joystick:
- Use the left stick to navigate the menu
- Press the lower button to select
- Press the right button to exit
- Use the Joystick Triggers to accelerate/brake
- Use the Left Stick to control the car
- Press the Start button to pause

### b. Interface
Menu:
- In the menu you can go to settings where you can change the volume of the game or music, change the language (currently English and Polish), or view the tutorial again
- The Best Score is displayed in the upper left corner
- To the right of the High Score your money is displayed, which you earn while playing and can be used to purchase car upgrades
- Car upgrades are Power, Handling, Braking and Durability, they have levels 1-12 and you can choose any purchased level
- In the menu you can select the time of day (day/night) and the difficulty level (easy - one-way traffic, medium - two-way traffic, difficult - one-way traffic in the opposite direction)

Game:
- Durability is displayed in the top left corner, try to keep it above 0. Durability can be lost by hitting cars or other objects.
- The Score is displayed in the middle to the right of the durability. The score can be obtained for distance and dangerous driving, e.g. close overtaking or destroying an object.
- To the right of the Score is the Score Multiplier. It can be increased if you drive above 70kmh, by driving dangerously, driving fast and driving on the wrong side of the road
- Information, e.g. about the destruction of an object, is displayed to the right of the multiplier
- The speed and gear are displayed in the lower right corner, and there is also a pause button

### c. Tips
- Remember, be sigma
- The faster you go, the higher your score multiplier
- If you drive below 70kmh your multiplier resets
- The multiplier increases x2 when you drive on the wrong side of the street
- Score and Multiplier Can also be increased by close overtaking, scratching and destroying cars, destroying obstacles and driving through crossings, red lights and holes in the road
- While driving you can collect upgrades: (multiplier increase, speed increase, repair)
- You can drive onto the sidewalk and drive backwards (no, you can't fall under the map by reversing, don't try)
- Don't destroy your car (optional)
- all game data is saved in gameData.json, you can change it at your own risk


## 5. Details
### a. Player Car Movement
- The player's car moves on the Z (front) and X (side) axis, and cannot rotate
- The maximum speed that can be achieved is approx. 360 kmh
- The car has 6 gears that are automatically adjusted to the power
- gear 6 is only used after collecting the speed boost
- after changing gear, the car is in neutral for 0.3 s, after 0.8 s it can change gear again
- reversing speed is approx. 25 kmh
- When durability drops to 0 for 0.5s you can still control the car, after 2s Game Over appears
- If you collect repairs 2 seconds after losing all durability, you can still drive

### b. Upgrades
- The upgrade price is 1000 * 1.5^n where n is the upgrade level - 2
- Power has a base value of 102 and increases by 10 with each upgrade. Power increases maximum speed and acceleration.
- Handling has a base value of 7 and increases by 0.5 with each upgrade. Handling increases steering acceleration and maximum steering speed.
- Braking has a base value of 50 and increases by 20 with each upgrade. Increases braking power.
- Durability has a base value of 100 and increases by 20 with each upgrade. Increases the number of durability points

### c. Obstacles and Durability
- For a front impact, the damage is the speed difference X + the speed difference Z
- For a side impact, damage is the speed difference X + (speed difference X * 0.1)
- Obstacles have a damage multiplier and max damage where max damage is checked before being multiplied by the multiplier
- Minimum damage to player's car is 2
- damage done to the player is (damage||max damage) * multiplier - 2
- Obstacles have minimum damage to destroy, if the damage is less, the obstacle will not be destroyed and the damage will be subtracted from the damage to destroy
All obstacles:

| Name          | Multiplier    | Max damage    | Damage to dest|  
| ------------- |:-------------:|:-------------:|:-------------:|
| BarrierLight  | 0.5           | 60            | 3             |
| BarrierHeavy  | 2             | 100           | 20            |
| Bollard       | 0.5           | 40            | 3             |
| Cone          | 0.5           | 30            | 1             |
| Tire          | 0.5           | 30            | 1             |
| Bench         | 0.5           | 50            | 5             |
| TrashCan      | 0.5           | 40            | 5             |
| Sign          | 0.5           | 50            | 4             |
| Lantern       | 2             | 100           | 15            |
| TrafficLight  | 2             | 100           | 15            |

- There are also 3 special obstacles
    - Hole - the faster you drive through it, the less damage it deals
    - Crossing - does not deal damage, after traveling over 70 km/h it gives you score
    - Lights - does not deal damage, after passing through red light it gives you score (Only the lights count in passages with lights)

There are 3 groups of obstacles in the game:
- Road obstacles, e.g. barriers - on each level (level is approx. 200M) 1 random obstacle is spawned in a random position. Obstacle List:
    - 2 Bollards
    - 2 Tire Stacks
    - 3 Cones
    - 4 Bollards
    - Light Barrier
    - Heavy Barrier
    - Cones with Hole
    - Light Barrier with Hole
    - Heavy Barrier with Hole
    - Hole
- Sidewalk obstacles, e.g. lamps - on each level, random sidewalk obstacles are spawned on both sides. Obstacle List:
    -Nothing
    - Lanterns
    - Benches
    - Signs
    - Lanterns + Benches
    - Lanterns + Signs
- Level obstacles, e.g. Crossing - on each level there is a 20% chance to spawn a random level obstacle. Obstacle List:
    - Crossing
    - Traffic Lights
    - Traffic Lights with Crossing

### d.Traffic
- There are 9 different traffic cars including:
    - 6 cars
    - 2 buses
    - 1 van
- In each level, random traffic will spawn equally on both sides in random positions
- The base number of traffic is 2, every 8 levels the number is increased by 2 up to 10
- All traffic has a different base speed (approx. 1), when spawning it is changed by -0.2 to 0.5
- Traffic can change lanes randomly (2% every 1-2 seconds) or in special cases
- Traffic changes lane randomly when both sides are going in the same direction, if not, it changes lane to the other lane on its side
- If there is another traffic car in front of the traffic car, the traffic car will slow down to the speed of the other car and try to change lanes every 2-6 seconds (it will not change lanes if it is blocked)
- If there is a crossing in front of the traffic car, the car will slow down by half
- If there are lights in front of the traffic car, the car will brake if the light is red
- If there is a player in front of the traffic car, the car will brake and try to change lanes every 2-6 seconds
- If there is an obstacle in front of the traffic car, the car will brake and try to change lanes every 0.1s
- If the traffic car hits an obstacle, it will disappear
- If a traffic car hits another traffic car, the destroyed car will disappear, if neither is destroyed, both will disappear

- Damage is calculated the same as for obstacles, but cars do not have max damage
- If the damage is less than the damage to destroy, the car will be scratched and the damage will be subtracted from the damage to destruction
- if the damage is enough, the car will be destroyed, it will stop driving and disappear in 3 seconds

| Type          | Multiplier    | Damage to dest|  
| ------------- |:-------------:|:-------------:|
| car           | 1.5           | 15            |
| van           | 2             | 22            |
| bus           | 2.5           | 30            |

### e. Power Ups
- There are 3 power ups in the game
- In each level there are 40% spawn a power up
- Speed ​​Boost increases power by 20% for 10s
- Multiplier Increase increases the multiplier by x1
- Repair adds 20% durability points

### f. Score and Multiplier
- Each score obtained is multiplied by a multiplier
- Score can be obtained per distance, every 0.1s
- You won't get a distance score by going back and forth

- Score multiplier is base multiplier * speed multiplier * wrong side multiplier
- When you are driving on the wrong side, the score multiplier is multiplied x2
- Speed ​​multipliers are:
    - 100 - x2
    - 200 - x3
    - 300 - x4
- the base multiplier can be increased by driving dangerously
- the base multiplier has a minimum value of x1 and a maximum value of x10
- base multiplier is reduced every 2s:
    - greater than x7, -0.4
    - greater than x5, -0.3
    - greater than x3, -0.2
    - less than x3, -0.1

Score and Multiplier can be earned for dangerous driving:

| Name                               | Score         | +Multiplier   |  
|:----------------------------------:|:-------------:|:-------------:|
| Destroying a bus                   | 350           | 1.4           |
| Destroying a van                   | 250           | 1             |
| Destroying a car                   | 200           | 0.8           |
| Scratching a car                   | 50            | 0.2           |
| Close overtake                     | 50            | 0.2           |
| Destroying BarrierHeavy            | 250           | 1             |
| Destroying Lantern, TrafficLight   | 125           | 0.5           |
| Destroying Lantern, TrafficLight   | 125           | 0.5           |
| Destroying Bench, TrashCan, Sign   | 75            | 0.3           |
| Destroying BarrierLight            | 75            | 0.3           |
| Destroying Bollard                 | 50            | 0.2           |
| Destroying Cone, Tire              | 25            | 0.1           |
| Running through red light          | 250           | 0.5           |
| Running through crossing           | 100           | 0.2           |
| Running over hole                  | 50            | 0.2           |






