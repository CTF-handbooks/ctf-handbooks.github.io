# Troubleshooting

> Always ensure that your client is **up-to-date**. The recommended Minetest version for the latest CTF game is **5.6 and above**, per its [ContentDB page](https://content.minetest.net/packages/rubenwardy/capturetheflag/).
> {style="warning"}

* Errors in the chat when testing a map; the game displays the cause of the error as red error messages in the chat. They are usually accompanied by improper functioning of the affected entities. For example, errors indicating
  * Improperly placed flags would require the flags to be removed and placed again in map edit mode.
  * Chests not being placed correctly need to have the chest zone bounds modified or the number of chests decreased.
* The world crashes (closes) *with a visible error message* shown in your client. If you are running your Minetest client from the terminal, these errors will also appear there. These are rare and usually due to outdated clients.
* Last but not least, in contrast to the previous type, the client crashes with no visible error. However, you will likely find the error messages in your terminal if you ran the client using it and the `debug.txt`.

> The easiest way to obtain a complete log of errors and other information is by reading through the `debug.txt` file in `<YOUR MINETEST FOLDER>`. The latest errors that you have experienced will be located close to the end of the file. {style="note"}

* *Special cases:*
  * [Game Freezes on Map Load](#game-freezes-on-map-load)
  * For RAM/Memory related crashes: [Low RAM Mode](#low-ram-mode)

> If none of the solutions on this page work, you can reach out for help on the [Minetest CTF Forum Topic](https://forum.minetest.net/viewtopic.php?f=10&t=13157) or the [`#maps` channel on the CTF Discord server](https://discord.gg/vcZTRPX). Be sure to attach the relevant information, such as error messages and the process that led to your problem!

### Low RAM Mode
> CTF can sometimes reduce CPU usage by calculating things once and putting them in the RAM. Turn on low ram mode if you're getting crashes related to RAM/Memory usage.

  ![Low RAM Mode](enable-low-ram-mode.png){width=433}


## Game Freezes on Map Load
* When testing a map, one might encounter the problem of the game freezing upon loading a map.

* For example, after running the command `/ctf_next -f <map_folder>` or clicking "Skip to Map" in the maps catalog, the game freezes and nothing happens. The map will eventually load after several minutes.

* To avoid waiting for that long, vote "1" for Classes when you join the world. After that, run the `/ctf_next -f <map_folder>` command or skip to your desired map through the maps catalog. Then, you will be asked to vote how many matches of Classic you would like to play. Vote "1" again. This should prevent your game from freezing.

    ![img.png](../images/vote_1_classic.png)
