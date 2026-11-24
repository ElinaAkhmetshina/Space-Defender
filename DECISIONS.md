Space Defender
Assignment 10
By Elina Akhmetshina

For this assignment I created 3 types of enemies: walker, speedster and flyer.
Walker - walks from the spawn to the nearest non occupied slot and then damages player (they all with wind-ups and cooldowns);
Speedster - faster, but has less health - fastly runs from one hiding spot to another, until reaches the player;
Flyer - spawns by a differen spawner in the sky, flyes to the waypoint, shoots, and switches places.

One thing to mention - the game doesn't have a victory, so, to count as victory, and count the tries for playtesters, I made them "survive" for 1 minute.

2026-11-11 Playtest: Renata 5 tries, less enemies spawned (Spawn interval from 3 to 5 - for the ground spawner, and 6 to 10 and start delay from 2 to 5).
2026-11-11 Playtest: Semyon 3 tries. Fliyers are killing player too fast (cooldown(2 to 3.5) and wind-ap(0.6 to 0.8) times are increased, and shots before move decreased(3 to 2)).

AI controll: Through this project I used AI to help with calculations, troubleshooting, and complex nodes systems:
2026-11-03  Asked the Claude AI on how to build for Android. Gradle failed with Java 25 and the NDK was r30 - installed JDK 21, switched to NDK r27c and moved GRADLE_USER_HOME out of the Cyrillic user folder.
2026-11-07  Asked to make the gun aim at the crosshair. The aim point ignored the crosshair's render translation.
2026-11-09  Defence-zone slots were cut off on 4:3 screens - changed the camera to Maintain X-Axis FOV so every aspect ratio sees the same width.
2026-11-10  Asked the agent for the Speedster's sight check (distance, angle, raycast). Delayed state changes could overwrite newer states.
2026-11-11  Package Project stayed grey and the command-line build failed - ANDROID_HOME pointed to an SDK without an NDK. Set ANDROID_HOME/NDKROOT to C:\Android\Sdk and packaged with RunUAT BuildCookRun.

Assignment 11

For this assignment I've moved all the Tuning variable into the PDA and DA files;
Made three different levels: level 1 - tutorial, level 2 - boss fight, level 3 - endless;
All the progrees player makes is saved, and can be reseted(with confirmation), or it can automatically go to defaults on delete of the file; 
On the levels player can see how long they have to survive, or can see their score in endless level, which is seen in the main menu.

AI controll:
2026-11-16  Enemies spawned in T-pose with "Accessed None: Stats" - Stats had Expose on Spawn, so the spawner overwrote it with None. Turned Expose on Spawn off.
2026-11-16  Flyers flew between points but never shot - DA_Flyer's Vision Range kept resetting to 0 because a SET node with a Target wrote into the data asset. Replaced it with Get from the asset + SET on the Flyer's own variable.
2026-11-18  Asked the agent for a save system. Used Unreal SaveGame (Saved/SaveGames) instead of JSON; a missing or corrupted SaveSlot.sav falls back to defaults.

Assignment 12
