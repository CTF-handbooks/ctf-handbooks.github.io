# Troubleshooting

## 1. Finding the cause
When running into an issue, you may observe one or more of the following types:
1. Errors in the chat when testing a map. In this category, the cause of the error is displayed as red error messages in the chat. They are usually accompanied by improper functioning of the affected entities. For these, please refer the [**"Map Related Errors" section**](#map-related-errors).
2. The world crashes (in other words, closes) *with a visible error* in your client. If you are running your Minetest client from the terminal, then these errors will appear there as well. These can be for a variety of reasons (WIP)
3. Last but not least, in contrast to the previous type, the whole client crashes with no visible error. However, you are likely to find the error in the log of your terminal if you ran the client using it as well as the `debug.txt`.

> The easiest way to obtain a complete log of errors and several other information is by reading through the `debug.txt` file located in `<YOUR MINETEST FOLDER>`. The latest errors that you have experienced will be located somewhere at the end of the file. Go through them and do as instructed in the next part. {style="note"}

- ***Special case:*** [Game Freezes on Map Load](#game-freezes-on-map-load)

## 2. Fixes 

> Make sure your client is **up-to date**. The recommended version for the latest CTF game versions is **5.6 and above** , as per its [ContentDB page](https://content.minetest.net/packages/rubenwardy/capturetheflag/).
> {style="warning"}

- The second type of errors (visible error in client) are fairly rare. If you cannot figure it out yourself (probably going to add something else here), you can always ask for help on the [CTF Minetest Forums Topic](https://forum.minetest.net/viewtopic.php?f=10&t=13157) or the [`#maps` channel on the CTF discord server](https://discord.gg/vcZTRPX) as per your convenience.
- For the third case, if you find that the `debug.txt` prints errors along the lines of "not enough memory", then your solution is most likely [Low RAM Mode Setting](#low-ram-mode)

### Map Related Errors
WIP


### Low RAM Mode
(WIP)

## Game Freezes on Map Load
* When testing a map, one might encounter the problem of the game freezing upon loading a map.

* For example, after running the command `/ctf_next -f <map_folder>` or clicking "Skip to Map" in the maps catalog, the game freezes and nothing happens. The map will eventually load after several minutes.

* To avoid waiting for that long, vote "1" for Classes when you join the world. After that, run the `/ctf_next -f <map_folder>` command or skip to your desired map through the maps catalog. Then, you will be asked to vote how many matches of Classic you would like to play. Vote "1" again. This should prevent your game from freezing.

    ![img.png](../images/vote_1_classic.png)
