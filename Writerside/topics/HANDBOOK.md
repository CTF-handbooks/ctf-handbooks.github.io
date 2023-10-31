# Making a Map for Capture the Flag

***
### 1. Required tools
* Minetest version 5.6 or above.
    > If you don't have Minetest installed, you can download it from the [official Minetest website](https://www.minetest.net/).
* Capture the Flag game for Minetest.
    > You can install the game from either the Minetest in-game ContentDB or from the [ContentDB website](https://content.minetest.net/packages/rubenwardy/capturetheflag/).
    
    > Once you downloaded the .zip file from the ContentDB website, extract the .zip file and move the folder inside it to `[Minetest folder]/games`.
* WorldEdit mod for Minetest (_optional_).
    > Although this is optional, it is recommended that you install WorldEdit. Creating maps requires you to build the borders and barriers of the map manually. This tool speeds the process up and is also helpful when building other desired map structures.

    > You can install WorldEdit from either the Minetest in-game ContentDB or from the [ContentDB website](https://content.minetest.net/packages/sfan5/worldedit/).

    > Once you download the .zip file from the ContentDB website, extract the .zip file and move the folder inside it to `[Minetest folder]/mods`.
  
***
### 2. Planning the map
* A map shouldn't be too big or too small. The size of a map can vary depending on the terrain and structures that the map will have. With a typical map size, players should be able to reach the middle of the map with a full sprint bar before running out of sprint. A maximum of `230 x 230` blocks in surface area is recommended.
* If you are making a map for the official CTF server, it is important to note that your map should be unique and not similar to the maps that already exist in the game.

    > "The design of a map should encourage differing gameplay and tactics." - -sniper-
* The map design shouldn't give any team advantages (such as having a better position or more resources). All teams should have an equal chance of winning.
* Using certain mods on the world the map-making takes place might cause unpredicted problems to the finished map. Switching Minetest or CTF game versions in the midst of the map-making process might also cause problems.
  
***
### 3. Creating the world
* Open Minetest and select the `Capture the Flag` game.
  
  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/d64da4d8-10e7-4a0e-b555-775f3804097b)
* Create a new world. You can use any mapgen. If you would like to use generated terrain, you can choose the `v7` or `flat` mapgen. If you plan on building the terrain/structures yourself, you can choose the `singlenode` mapgen. 

  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/d49ea3a7-87b4-4d42-af98-e003790b8ad4)
* After you click `Create`, uncheck `Enable Damage` and check `Creative Mode`. Creative mode will enable `mapedit` mode.
  
  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/158625b3-5596-4143-8a7e-8969835c17a2)
* If you would like to use WorldEdit, click `Select Mods`, select `WorldEdit`, and click `Enable modpack`.

  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/a40dea59-fdab-459f-b2f8-5c281c037498)
* Click `Save` and play the world.
  
***
### 4. Setting up
* Grant yourself the "ctf_map_editor" priv by running `/grantme ctf_map_editor`. You can also use `/grantme all` to grant yourself "ctf_map_editor" and all the other privs that will be useful while making a map, such as fly, noclip, fast, etc.
* You can hit <kbd>Esc</kbd> on your keyboard and click `Change Keys` to see your controls (such as how to fly, noclip, etc.).

  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/98117763-d42c-4a64-ade6-a894c14f61a9)
* *Tip*: Run `/time 12000` and `/set -n time_speed 0` if you want to disable nighttime while building the map.
  ```
  /time 12000
  ```
  ```
  /set -n time_speed 0
  ```

***
### 5. WorldEdit basics
* To use WorldEdit, first, you must select an area where your actions occur.
* You can use the `WorldEdit Wand tool` to select your area. To select your area, you select the two opposite corners of the area. Left-click a node with the tool to make the node the first corner, and right-click to set the second.
  
  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/fbf6847c-34ed-4c6b-892e-2c862aa3927f)
* An alternative method is to stand at the point you would like to select and run `//1` in chat to set the first corner and `//2` to set the second.
* The area within will be selected.

  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/ee5175f2-5071-405f-a7f1-d175261002a9)
* **Remember to backup your world before risky operations!**
* Open your inventory. Under the `Crafting` tab, an earth icon is hidden behind the crafting options. Click it to open the WorldEdit GUI.

  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/d8db8d4c-ee38-4d12-a90b-d2fb73884611)
* These are the tools that you can use to alter the nodes within your selected area. You can experiment with the options.

  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/ef0db7f5-696a-4611-ad54-c4def6d1aa2f)
* To set the area you've selected earlier with a certain type of node, click `Set Nodes`, type in the name of the node you would like to set in the field, click `Search` or press enter, and click `Set Nodes`.
  
  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/3b12e708-f60e-42c4-8ebc-1a1c764dd093)

* If you've selected a large area, WorldEdit might warn you in chat. Type `//y` in chat to continue.

  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/1e84188f-52a6-43db-a79c-fc662e75d987)
* To replace a certain node type with another one in your selected area, select `Replace Nodes`. In the first field, type in the node you would like to replace; in the second field, type in the node you would like to replace with.
* To only place nodes where there are no nodes, you can replace `air` with the node you want to use.

  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/63fe78c0-ab9f-458d-b6bd-7d90ea4414c5)

***
It is your choice to build the barriers first or the map first. For this example, we are going to build the barriers first.
### 6. Removing the surrounding terrain
* This is optional and only applies if you're using generated terrain.
* It might be hard to place the outer barriers when the terrain outside your map area blocks your view.
* To get rid of the extra terrain, first, select the area your map will be in with WorldEdit.
  
  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/0c966405-3ac4-4b82-b404-e7f6526c74c3)

* Once you select the area, run `//mtschemcreate <any name>`. For example:
  ```
  //mtschemcreate map_terrain
  ```
* You can copy the exported schems to a singlenode world and place the terrain there. But to keep it simple, you can just fly up in the air and place the terrain in the sky.
* Enable fly, fly up, and find a suitable place. Place a corner with WorldEdit by running `//1` in chat. Then, run `//mtschemplace <your schem name>`. For example:
  ```
  //mtschemplace map_terrain
  ```
* With that, your terrain should be placed there successfully. If you're unhappy with the result, you can go back down, pick another terrain, and do it again.
  
  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/ed6996b5-3181-40b9-8080-c50cd7258cef)

***
### 7. Placing the barriers
* To make the bottom of the map indestructible so that players can't escape, select the bottom layer of your map and replace it with any indestructible node through the WorldEdit GUI, or the command `//s <node itemstring>`. For example:
  ```
  //s ctf_map:ind_stone
  ```
  > To see the itemstring of a node when hovering over it inside your inventory, you can go to settings, search for "append", and enable `Append item name`.
  
  > You can find a list of commonly used itemstrings during map making [here](https://github.com/CTF-handbooks/map-maker-handbook/blob/main/ITEMSTRING.md#a-list-of-the-itemstring-for-the-indestructible-nodes-ctf-provides).
* Your outer barriers can be placed outside your map area, override the outer slice of your map, or leave parts of the map terrain/structures outside the barrier.
  
  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/99393b5b-8172-4593-9ada-8bd8c0966d50)
  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/a65611d8-8c40-4e6a-b48c-2d43da4b495e)
  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/03a968d2-8822-4904-9302-9835ca3c4848)

* To place the outer barrier, select the area where the barrier will be with WorldEdit (this area should only be one node thick) and set it to `Indestructible Barrier Glass` (`ctf_map:ind_glass`) or any type of indestructible node. Many nodes have indestructible variants, which you can use. You can place it using the WorldEdit GUI, or through the command `//s <node itemstring>`. For example:
  ```
  //s ctf_map:ind_glass
  ```
  This method will penetrate the terrain/structures if you have some within your selected area.
  
  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/ab6b6c1e-1341-4a34-bbcd-af2970c99b10)

* To replace the terrain with a type of indestructible node and everything that is not terrain with the barrier glass like the image below, you can replace-inverse air with your indestructible node and then replace air with `Indestructible Barrier Glass`.
  
  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/8880f9df-4bb6-416e-95cf-a0555b2103e6)

* To do that, select the area where the barrier will be with WorldEdit and replace-inverse air with your indestructible node through the WorldEdit GUI or using `//ri air <node itemstring>`. For example:
  ```
  //ri air ctf_map:ind_stone
  ```
* Then, without selecting a new area, replace `air` with `Indestructible Barrier Glass` using the WorldEdit GUI, or through the command:
  ```
  //r air ctf_map:ind_glass
  ```
* After finishing your first barrier wall, proceed to build the other 3 sides of the barrier.
* You can also make a roof using any type of indestructible node such as `Indestructible Barrier Glass`, but if you set your map area correctly later on, players shouldn't be able to escape through the roof. So, you do not necessarily need to add a roof.

***
### 8. Building the map
* If you are using the singlenode mapgen, players will not be able to move around without noclip. You have to set the area you want players to move in to `air` using WorldEdit. To do that, you can use the command:
  ```
  //s air
  ```
* When building your map, you can add any structure you want. Many blocks have indestructible variants, which you can use for builds you don't want players to destroy (use the admin pickaxe to break indestructible blocks).

  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/3a724fe8-9005-4dde-9438-36d424a2e7be)
  
* You should also add the following:
    * Indestructible blocks under the position of the flag (the flag will be added later). The minimum surface area for this indestructible platform is `5x5` blocks (the flag should be in the middle).
    * Team chests for each team. You can find them as a node in the inventory.
      
      ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/74f210ba-3b94-473a-bff8-886f8578d3d3)
    * _Optional_: ores (such as iron, diamond, or mese ores). The number of ores for each team should be about the same to ensure that no team has an advantage (please note that mapgens such as v7 and flat come with ores).

***
### 9. Building the build-time barrier
* Your build-time barrier should be in the middle of the map. It is fine if it can't be precisely in the middle.
  > You can press <kbd>F5</kbd> to show your current coordinates.
* The `Indestructible Red Barrier Glass` will disappear once build-time is over, so your build-time wall should not replace any part of the map terrain/structures.
* To do this, select the area where the build-time barrier wall will be with WorldEdit (you can include terrain/structures in the selection too; don't worry they won't be replaced), and run:
  ```
  //r air ctf_map:ind_glass_red
  ```
* If there are stone nodes within the barrier wall, you can replace them with `Indestructible Red Barrier Stone`, which will turn into normal stone once the match starts. To do this, maintain the same selected area as before and run:
  ```
  //r default:stone ctf_map:ind_stone_red
  ```
* If there is water within the barrier wall, you can replace it with `Indestructible Water Barrier Glass`, which will turn into water once the match starts. To do this, maintain the same selected area as before and run:
  ```
  //r default:water_source ctf_map:ind_water
  ```
* If there is lava within the barrier wall, you can replace it with `Indestructible Lava Barrier Stone`, which will turn into lava once the match starts. To do this, maintain the same selected area as before and run:
  ```
  //r default:lava_source ctf_map:ind_lava
  ```
* If there are still breakable nodes within the barrier wall, you can leave them there, because if you set your team-zones correctly later on, players should be teleported back to base if they cross the barrier wall.

***
### 10. Selecting the map area
* After you finished building your map, run the following command in chat:
  ```
  /ctf_map editor
  ```
* Click `Create New Map`.
  
  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/b57294e1-b6f1-4a5d-aeb7-40408c5c580d)

* Follow the instructions given to you in chat and select the area your map is in, just like how you would select the area with WorldEdit. You can either punch a node to select or stand where you want to select and run the following command:
  ```
  /ctf_map here
  ```
  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/bdca51e0-a439-4bf3-a65a-75530f2f5d2d)
  
  Make sure you selected your entire map and make sure you did not select any extra space. If you have decided to leave some terrain/structures outside your outer glass barrier, include them too.

***
### 11. Exporting the map
* After selecting your map area, run `/ctf_map editor` in chat again. This will open the Map Editor.
* Check `Map Enabled` unless you don't want to make the map available for play. If you are making the map for the official server, you will check this.
  
  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/a1bfc7bb-0b84-4cea-b41c-b15668c15f55)

* In the license field, add the license of your map. Every map must have a license. The official CTF server will only accept free culture licenses like `CC BY-SA 4.0`. Please note that some CC licenses, such as `CC BY-ND` are not free. You can find a list of CC licenses [here](https://creativecommons.org/share-your-work/cclicenses/).

  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/e3e0a9e8-8968-423a-8b54-3288f303d0d9)

  From the ctf_map README:
  > You can append any attribution you need to give to the `license` field (For example: If you modified someone's map or used one of their builds you'd list their name and what map/build of theirs that you modified/used). If you want to give more information, you can use the `Other Info` field.
  
  > Please make sure you know what you are doing when choosing a license.

* In the `Folder Name` field, type in the name you want the map folder to be. For example, if your map name is "My Map", it is recommended for you to name the folder `my_map`.
  
  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/caf03394-10db-49cb-9adb-86206271458d)

* Give players a hint about your map in the `Map Hint` field, such as where the treasures/ores are.
  
  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/2aa3b7d9-b006-4b6a-afa4-2b6960854935)

* Use `Other Info` for additional information about the map. You can leave this empty.

  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/0cbab0b8-28b6-443e-8ead-51cfb924758e)

* In the `Map Name` field, type in the name of your map. For example, "My Map".

  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/61e82cf7-5665-45ec-82c6-580824d34184)

* In the `Map Author(s)` field, type in the name(s) of the author(s) of your map.

  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/97132307-260e-4d1a-b065-f909d30ee39b)

* From the ctf_map README:
  > `initial_stuff` are the items given to players at their (re)spawn. The `initial_stuff` field is located in the `map.conf` file. At least a pickaxe and some torches should be given in the map's `initial_stuff`.

  > An example of `initial_stuff` value that registers a stone pickaxe, 30 cobblestones, 5 torches and a pistol is given below.

  ```
  default:pick_stone,default:cobble 30,default:torch 5,ctf_ranged:pistol_loaded
  ```
  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/30c84310-aef6-4cd5-b527-167a53425a6a)

* `Map Treasures` is **optional**. You can leave this field untouched. From the ctf_map README:
  > (`Map Treasures` is) a list of treasures that can be added specifically for your map that don't end up in chests by default.

  > Format:
  ```
  [name];[min_count];[max_count];[max_stacks];[rarity];[TREASURE_VERSION];
  ```

  > `rarity` is a value between 0 and 1 specifying the probability it will be added to a chest.
  > `TREASURE_VERSION` should currently be set to one.

  > Example:
  >  ```
  >  default:lava_source;1;10;1;0.2;1;default:water_source;1;10;1;0.2;1;
  >  ```
  >  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/4a06abae-25df-4895-a1b0-515f00ea5070)

* The `Skybox` is an image of a sky that will replace the default Minetest sky when players play your map. You can leave this as `none` to use the default Minetest sky or select one of the skyboxes. You can also add custom skyboxes.
  
  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/15ca58b2-3600-460b-87fc-e11cf7fd9589)

* In `Map Modes`, you can select the modes that will be enabled for your map. By default, all modes are enabled. To disable/enable a mode, double click it. Disabled modes are in the `Available Modes` box.
  
  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/602d38cd-1a02-448f-85e8-685040ac7ee0)

* Map Constants (from the ctf_map README):
1. `Map Shadow Intensity`: Sets the intensity of the shadows.
2. `Map Gravity`: Gravitational constant of the map. (default = 1)
3. `Map Movement Speed`: Regulates the speed at which players move. (default = 1)
4. `Map Jump Height`: Regulates the height of jumps. (default = 1)
5. `Map start_time`: Sets time of the day the match begins at. Changing this field will instantly update the time of day in the world you are editing.
   * `0` is for midnight
   * `1000` is for 1 AM
   * `2000` is for 2 AM
   * etc.
  
* Below the map constants, you will see a list of the different teams with a checkbox next to them. Use the checkbox to enable the teams that exist in your map.
  
  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/6b893f4d-ef85-460c-a67a-a2b60eb2f49b)

  Next, click the `Set Flag Pos` button below your first enabled team and punch the node where that team's flag will be on. This will place the flag on top of that node.

  Then, click the `Zone Bounds` button below the `Set Flag Pos` button and select the team's team-zone. A team-zone is the area where the team's players interact within during build-time before the build-time barriers drop. During build-time, players who leave the team-zone will be teleported back to base. Even standing on the edge of the team-zone will teleport the player back to base, **so make sure to include the barriers within your team-zone too, or players will get teleported back to base if they touch the barriers during build-time!**

  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/7186f5fd-1e8d-416b-a7a6-a6eb9b2796bd) ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/843e65d0-6dba-4de7-b8d6-d4b9fee34b2a)

  The `Look position` is the direction the players will look when they spawn at base. You can leave this by default (default is: auto).

  Repeat the same process for every enabled team.

* To add treasure chests to your map, click the `Add Chest Zone` button to add a chest-zone. A chest-zone is an area where the treasure chests will spawn randomly. You can add multiple chest zones. Click on the `Chest Zone - (0,0,0) - (0,0,0)` button for each chest zone to select each chest zone's area. You can only add one chest zone and have it cover the whole map, or you can add several different chest zones. You can edit the number of chests that will spawn randomly in each chest-zone.

  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/65433e30-3307-4ab5-811d-cfcbc72e085b)

  You can click the `X` button to remove a chest zone. Make sure each team gets around the same number of chests on their side!

* Once you finish configuring the map, click the `Finish Editing` button at the very bottom to finish.
  
  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/7544f651-0f90-45b3-bca4-684eb472043f)

***
### 12. Testing the map
* You can find your exported map in `[Minetest folder]/worlds/[Map World]/schems/`.
* To test your map, copy that folder into `[Minetest folder]/games/capturetheflag/mods/ctf/ctf_map/maps`. You can go to your Minetest folder and paste the following into your file manager's search/directory to navigate there quickly:
  ```
  /games/capturetheflag/mods/ctf/ctf_map/maps
  ```
  > If you experience a problem with the above path on certain file managers, copy it without the `/` at the start.

* Create a new world in the Capture the Flag game with the `singlenode` mapgen.
  
  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/a7b93c30-8578-4e98-a582-53b4f84a60a4)

* Disable `Creative Mode`, and play the game.

  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/8a1e3147-2a17-4037-8edd-cb0b4367e792)

* Grant yourself the `ctf_admin` priv by running the following command:
  ```
  /grantme ctf_admin
  ```
* To skip to your map, you can run the command `/ctf_next -f <map_name>` or run the command `/maps`. Once you run the `/maps` command, you will be in the "Map catalog" menu. Find your map in the list, select it, and press the `Skip to map` button.
  
  ![image](https://github.com/CTF-handbooks/map-maker-handbook/assets/88883098/66d933d6-e5ae-4e01-bc8c-dd366d99711b)

* To skip build-time, you can run the following command:
  ```
  /ctf_start
  ```
* To set yourself to the other team, run:
  ```
  /grantme ctf_team_admin
  ```
  Then:
  ```
  /ctf_teams set singleplayer <team color>
  ```
  For example:
  ```
  /ctf_teams set singleplayer blue
  ```

***
### 13. Screenshot
From the ctf_map README:
> If you choose to submit your map, include a screenshot of it in the exported map's folder. It should be taken without any texture packs enabled and must have an aspect ratio of 3:2 (screenshot `600px`x`400px` is suggested).

> You can take a screenshot easily by doing the following:
> 1. Hide the HUD. By default <kbd>F1</kbd> does that.
> 2. Hide the chat log. By default <kbd>F2</kbd> does that.
> 3. See if your screenshot looks better with/without fog enabled. You can toggle it with <kbd>F3</kbd> by default
> 4. Try to find a good view that shows most of the map.
> 5. *(Optional)* Increase your view range if important parts of the map cannot be seen. By default the <kbd>=</kbd> (or <kbd>+</kbd>) and <kbd>-</kbd> keys do that.
> 6. Take a screenshot **from Minetest**. By default <kbd>F12</kbd> does that.
> 7. You can find the screenshot in `[Minetest folder]/screenshots` unless you have changed the path in the settings.

> Crop the screenshot into the aspect ratio mentioned above using a tool of your choice, and put the screenshot inside your exported map's folder. It should be named `screenshot.png`.

To crop your screenshot, you can use [this](https://imagy.app/image-aspect-ratio-changer/) website.

***
### 14. Submission
* Now that you have finished making your map, you can submit it to the official CTF server. You can learn more about submission [here](https://github.com/MT-CTF/capturetheflag/blob/master/mods/ctf/ctf_map/README.md#9-submission).
