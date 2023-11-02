# Testing a Map for Capture the Flag

## Table of Contents

- [Prerequisites](https://github.com/CTF-Handbooks/map-tester-handbook/blob/main/HANDBOOK.md#prequisites)
- [Structure of the CTF Maps Repository](https://github.com/CTF-Handbooks/map-tester-handbook/blob/main/HANDBOOK.md#structure-of-the-ctf-maps-repository)
    1. [Where can I find the CTF maps and those that require testing?](https://github.com/CTF-handbooks/map-tester-handbook/blob/main/HANDBOOK.md#1-where-can-i-find-the-ctf-maps-and-those-that-require-testing)
    2. [What do the folders and files mean?](https://github.com/CTF-Handbooks/map-tester-handbook/blob/main/HANDBOOK.md#2-what-do-the-folders-and-files-mean)
- [What are GitHub and Git?](https://github.com/CTF-Handbooks/map-tester-handbook/blob/main/HANDBOOK.md#what-are-github-and-git)
- [Git Terminology](https://github.com/CTF-Handbooks/map-tester-handbook/blob/main/HANDBOOK.md#git-terminology)
- [How do I know which maps to review?](https://github.com/CTF-Handbooks/map-tester-handbook/blob/main/HANDBOOK.md#how-do-i-know-which-maps-to-review)
    - [Where can I find Map PRs?](https://github.com/CTF-Handbooks/map-tester-handbook/blob/main/HANDBOOK.md#where-can-i-find-map-prs)
    - [Labels on Pull Requests](https://github.com/CTF-Handbooks/map-tester-handbook/blob/main/HANDBOOK.md#labels-on-pull-requests)
- [Fetching PR files for testing](https://github.com/CTF-Handbooks/map-tester-handbook/blob/main/HANDBOOK.md#fetching-pr-files-for-testing)
- [Testing the Map](https://github.com/CTF-Handbooks/map-tester-handbook/blob/main/HANDBOOK.md#testing-the-map)
    1. [Map config](https://github.com/CTF-Handbooks/map-tester-handbook/blob/main/HANDBOOK.md#1-map-config)
    2. [Making the world](https://github.com/CTF-Handbooks/map-tester-handbook/blob/main/HANDBOOK.md#2-making-the-world)
    3. [Playing the game](https://github.com/CTF-Handbooks/map-tester-handbook/blob/main/HANDBOOK.md#3-playing-the-game)
    4. [Selecting the Map](https://github.com/CTF-Handbooks/map-tester-handbook/blob/main/HANDBOOK.md#4-selecting-the-map)
    5. [Map Requirements](https://github.com/CTF-Handbooks/map-tester-handbook/blob/main/HANDBOOK.md#5-map-requirements)
        - [Basics](https://github.com/CTF-Handbooks/map-tester-handbook/blob/main/HANDBOOK.md#basics)
        - [Mechanics](https://github.com/CTF-Handbooks/map-tester-handbook/blob/main/HANDBOOK.md#mechanics)
    6. [*Your opinion is the key!*](https://github.com/CTF-Handbooks/map-tester-handbook/blob/main/HANDBOOK.md#6-your-opinion-is-the-key)
    7. [Posting your Review](https://github.com/CTF-Handbooks/map-tester-handbook/blob/main/HANDBOOK.md#7-posting-your-review)
- [Test away!](https://github.com/CTF-handbooks/map-tester-handbook/blob/main/HANDBOOK.md#test-away)

---

## Prerequisites

1. Minetest version 5.6 or above.
    - If your version is outdated, download the latest from the [official Minetest website](https://www.minetest.net/).
2. The `Capture the Flag` game. To get it,
    - Go to the `Content` tab in your Minetest client.
    - Click `Browse Online Content`
    - Search for `capturetheflag` (make sure that the `Games` category is selected)
    - Click on the `+` icon to install it.
3. `WorldEdit` mod (Note: Although this is *optional*, you will need it for a holistic map review).
    - Download it as you did for the CTF game, but you should have `Mods` set as the category.

---

## Structure of the CTF Maps Repository

### 1. Where can I find the CTF maps and those that require testing?

All the [maps on CTF](https://github.com/mt-CTF/maps) are stored in a repository on [GitHub](https://en.wikipedia.org/wiki/GitHub), the website via which you may be reading this. As a map tester, you will review "Pull Requests" for maps. If you're unfamiliar with "Pull Requests" and GitHub in general, read along to learn more.

### 2. What do the folders and files mean?

The repository contains folders for each map. For example, the “Intervention in the Ice Age” map files are in the `iceage` folder. The files within a map folder are:
```
<map folder>
  ├── barriers.data
  ├── map.conf
  ├── map.mts
  └── screenshot.png
```
1. `barriers.data`: The calculated and compressed file containing the build-time barrier locations for the map. This speeds up the barrier removal (Note: `barriers.data` is optional and is only supported by map version 3 or above).
2. `map.conf`: The configuration of various values and fields essential to the map.
3. `map.mts`: The schematic file used to import the map into the game world. The "map" itself is inside this file.
4. `screenshot.png`: A screenshot of the map. It should make the critical parts of the map visible, and it needs to have an aspect ratio of 3:2 (600×400px is suggested).

## What are GitHub and Git?

GitHub is one of the many services for managing code and other projects using the version control system - [Git](https://git-scm.com/). For now, this handbook will only cover the primary ways of obtaining the files of the map you would like to test without any command line interface.

---

## Git Terminology

Below is a list of a few terms you need to know while testing maps and using GitHub. Don't be intimidated by these; keep them in mind for future reference.
- A **repository** is a virtual storage for projects that tracks all changes made to the project's files. In this case, the [map's repository](https://github.com/MT-CTF/maps) is the remote storage of the maps for CTF.
- A **fork** is a copy of the original repository. It can be modified without affecting the original repository and then be made into a **pull request** if needed.
- A **commit** is a snapshot of a project. As a verb, it means the action of saving a snapshot (you can understand this as "save" or "apply changes").
- A **branch** refers to a separate version of the repository that initially has the same code base as the repository in which it was made. A new branch can have its own set of files and commits.
- A **pull** from a repository means getting the latest source code from the repository to one's local machine.
- A **push** means pushing the **commits** made on a local machine to the remote repository.
- A **pull request** (PR) refers to when you make changes on the fork of the repository and request to merge those changes with the main repository. Here, those who wish to make maps first fork the maps repository, create a separate branch on that fork dedicated to adding the map, and make a **pull request** to the maps repository upon completion.

---

## How do I know which maps to review?

#### *Where can I find Map PRs?*

- Go to the [CTF maps repository](https://github.com/mt-CTF/maps) using the web browser of your choice.
- Click `Pull Requests`:

![PR button](pr-s_section_example.png)

- You will be directed to a webpage listing PRs with their respective labels. Clicking on a particular PR will take you to it.
- There will be a series of tabs that will help you navigate through the things related to a specific PR. (An example image is shown below.)

![Intra-PR Ribbon Example](ribbon_example.png)

- You discuss the PR and post your reviews in the ***Conversation*** tab. The ***Commits*** tab lists the commit history (basically the various series of changes made to it). Similarly, the ***Files changed*** tab shows the files that have been added, removed, or modified.

#### *Labels on Pull Requests*

The Map PRs have labels that indicate their current development stage and give information about them. You should look for the ***"New Map"*** and ***"Review Required 🔍"*** labels, as they are the ones that need a review. There are also others, such as, ***"PR not created properly"***, ***"WIP 🏗️"*** (= Work In Progress), ***"Enhancement"***, and ***"Action/change needed ❕"***. A good example of a PR that you can test is:

![Labels Example](label_example.png)

---

## Fetching PR files for testing

- Go to the `Pull Requests` tab and select the PR you want to review.
- Click on the blue text indicating the `<pr-author>:<branch-of-their-fork>`, like:

![PR Fork/Branch Example](pr-fork-branch-example.png)

- After doing so, press the `Download ZIP` button:

![Getting the files Example](pr-forked-repo-code-example.png)

- Extract the ZIP file.
- From the extracted folder, select the map folder that the PR author has added. In the example PR mentioned, the folder is `sewer_village`.
- After successfully identifying the new map folder, copy and paste it to `<YOUR MINETEST FOLDER>/games/capturetheflag/mods/ctf/ctf_map/maps/` on your computer. You can go to your Minetest folder and paste the following into your file manager's search/directory to navigate there quickly:
```
/games/capturetheflag/mods/ctf/ctf_map/maps
```
> If you experience a problem with the above path on certain file managers, copy it without the `/` at the start.

> Going to the `About` section in Minetest and pressing the `Open User Data Directory` button will take you to your Minetest folder.

- You have now retrieved the map folder!

> Make sure that the map has all the required files as stated in [What do the folders and files mean?](https://github.com/CTF-Handbooks/map-tester-handbook/blob/main/HANDBOOK.md#2-what-do-the-folders-and-files-mean). If not, then drop a message regarding it in the PR if not addressed by others already.

## Testing the Map

### 1. Map config

The configuration values and fields for the map are in the `<map_folder>/map.conf` file. It should first satisfy these criteria:
- Required fields such as `game_modes`, `name`, and `author` are filled.
- The map should be enabled, or else the map cannot be played. (Look for the line `enable = true`)
- The map has a license. It should be in the family of free (as in freedom) culture licenses like `CC BY-SA 4.0`. Note that not all Creative Commons licenses are free. E.g. `CC BY-ND` - these are not accepted.
- The initial items for the map are appropriate for the map (take notes of the terrain, the ores, etc.).
- If the map has a hint, it should be relevant for it.
- If values of [these map constants](https://github.com/MT-CTF/capturetheflag/blob/master/mods/ctf/ctf_map/README.md#map-constants) are overridden from the default, the modifications do not negatively impact gameplay.
  You can check for some of these before or after testing the map in-game.

### 2. Making the world

- Open your Minetest client and make sure you are in the `Start Game` tab.
- Click the Capture the Flag game icon:

![Game icon](game_icon.png)

- Press `New World`.
- It is vital that you ensure you are setting the world's mapgen as `singlenode`, like the screenshot below.

![Mapgen example](mapgens.png)

- Finally, click `Create`.

### 3. Playing the game

- Select the new world that you just created.
- Disable `Creative Mode` to play the game. You can turn of `Enable Damage` as well.
- Enable the `WorldEdit` mod by pressing `Select Mods` and double-clicking the `WorldEdit` mod to enable it.
- Then click `Play Game` to begin.

### 4. Selecting the Map

> You will need the `ctf_admin` privilege to run most of the commands in this handbook. So, grant yourself the privs using `/grantme ctf_admin`. If you would like other privileges such as `fly`, `nolcip`, `fast`, etc., running the `/grantme all` command would cover them all.

- Check the `map.conf` file's `game_modes` field, if the one you are voting for in-game is not included in the list, vote `0` and go to the mode the map is set for (TODO).
- Upon starting the game, you will be playing like how the server works, with a random map at first. To choose your map, run `/ctf_next -f <map_folder>`. In the case of the example PR, it would be `/ctf_next -f sewer_village`. (TODO)

> Common commands:
> - To end build time, use the `/ctf_start` command.
> - To set yourself to the other team, run:
>  ```
>  /grantme ctf_team_admin
>  ```
>  Then:
>  ```
>  /ctf_teams set singleplayer <team color>
>  ```
>  For example:
>  ```
>  /ctf_teams set singleplayer blue
>  ```

### 5. Map Requirements

#### *Basics*

- No errors appear (red text in the chat) when loading/playing the map. The error would mention what is causing the issue, so bring it to the PR author's notice accordingly.
- Base:
    - The area under the flag (base floor) is indestructible and has a surface area of 5x5 at minimum.
    - The flag is placed in the middle of the indestructible area.
    - It has a team chest.
- The map **should** be inescapable. This means map's **walls** and **floor** should be made of "Indestructible Barrier Glass" (`ctf_map:ind_glass`) ando or indestructible variants of blocks. The map may not have a roof while still not allowing the player to escape through it. Make sure you can't escape through the open roof.
- It has red build-time barriers separating teams that disappear when build time is over. Check if all of these are correctly placed. Make sure no areas that need it are missing.
- Treasure chests are functional.
- Flags can be captured without any bugs.
- All the team zones are to the extent of where they should be and work as intended. You can test if they function correctly by ensuring you do not get teleported back to the base during build-time while at the edges of the map's walls and the build-time barriers. It is also important to ensure you get teleported back to base if you cross the barriers (for example, by digging under the build-time barrier). You should also make sure that you do not get teleported back to base during build-time if you dig straight down to the bottom layer or build up to the roof.
- The map is without any holes leading to the void, "misplaced" blocks/accidental inconsistencies, does not contain unsupported blocks, and so on.

#### *Mechanics*

- All the teams should have an **equal chance of winning** and **be subject to the same amount of difficulty in gameplay**. Things that affect those are base position, terrain balance, chests, and ore count.

> To count ores in a region, you can use WorldEdit.
> 1. Go to the first coordinate of the area and run `//1`.
> 2. Go to the second position and run `//2`.
> 3. Suppress (in other words, hiding without destroying) all the ores you want to find the count of (amount gets printed in the chat) by using `//suppress <node name>`. Ensure you are correctly typing the node name. For example, you will do `//suppress Mese Ore` for "Mese Ore" (hover over blocks in the inventory to obtain their exact name). Use `//restore` in a selected region to bring back the suppressed nodes.

- The map should be unique and not be similar to other maps. Maps that are too plain or are very similar to existing maps such that they do not add new value have a higher chance of rejection. The map design should encourage differing gameplay and tactics, with creativity on the map maker's part.

### 6. *Your opinion is the key!*

What's next? It is your thoughts on the map! Is it fun to play? What do you think about it? How can its mechanics/style/idea be improved? All this matters.

### 7. Posting your Review

To post your review, go to the ***Conversation*** tab within the PR on GitHub. Write your review in the text box and press the green `Comment` button.

---

## Test away!

Now that you have completed reading this and can test a map, you can use [`CHECKLIST.md`](Map-Tester-s-Checklist.md) as a summary of the process so that you never miss a step. Thank you, and enjoy your time testing map PRs for CTF!
