For the development of this captivating 2D game, I embarked on a meticulous approach, starting with the creation of detailed maps using TILED, an essential tool in the design of game spaces. Each level was conceived to offer a unique experience: level 1 was based on a single map, while level 2 was expanded by adding two distinct maps. I integrated a variety of graphic elements to enrich each scene, dividing the game environment into multiple layers, such as Platforms, Colliders, Environment, Background, Player Zones, Enemy Spawns, Collectibles, and Traps. These layers were carefully designed to include challenging paths, obstacles, and rewards, creating a dynamic landscape for the players' adventure.

The game resources, including the maps, were exported in JSON format and incorporated into the development arsenal, ready to be brought to life through JavaScript code with the help of the Phaser framework. This allowed me to build a robust structure for the game, starting with a preload class where all necessary elements - from characters to visual effects - are prepared for action.

The game configuration was clearly defined in index.js, setting the screen dimensions and essential visual parameters, while the animations, from the characters' movements to the collectibles' effects, were meticulously created in anims.js, adding an impressive visual dimension to the game.

The combat system implementation included classifying weapons into MeleeWeapons.js for direct confrontations and Projectile.js for ranged attacks, each adapted to fit the game mechanics. The collectibles, represented in collectables.js, not only provide points but also add a strategic layer to the game, encouraging exploration.

Enemies, whether we talk about Birdman or Snaky, were equipped with raycasting techniques to offer a real challenge, each with its set of animations to reflect different states - from inactivity to elimination. The player, managed in Player.js, benefits from a wide range of movements and attacks, providing a fluid and intuitive gaming experience.

At the interface level, I introduced a health bar and a scoring system in the Hud file, essential for monitoring progress and the player's state. Additionally, I included a start menu and an end menu, enriching the narrative structure of the game and giving players a well-deserved break between levels.

Beyond gameplay, I paid special attention to the audio aspect, integrating background music and sound effects to complete the game's atmosphere, from the player's footsteps to the enemies' noises and collectibles' sounds.

In conclusion, this 2D game is the result of a careful combination of graphic design, programming, and storytelling, each element thoughtfully designed to provide an immersive and challenging experience for players.
