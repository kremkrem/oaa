# Installing Open Angel Arena
You have to set up several things before you can run a local instance of OAA for development.

## System Dependencies
Start by installing these programs:
 * [Steam](http://steampowered.com)
 * [nodejs](http://nodejs.org)
 * [Github client](http://desktop.github.com/)
 * [Sublime Text 3](http://www.sublimetext.com/) **optional**

Install the Dota 2 Workshop Tools.
 * From within steam, right click on `Dota 2` and select `Properties` at the bottom
 * Go to the DLC tab of the window that pops up
 * Check the `INSTALL` box next to `Dota 2 Workshop Tools DLC`

## Addon Tool
Open the `node.js command prompt`. Not `Node.js` itself, but the command prompt.

### Install Node Dependencies
Run the command 
```
npm install -g dota2-addon-manager
```
This will install both `d2am`, used to manage the addons directory.

### Prepare Addon Directory
Next find your `dota 2 beta` folder. You must change the directory of the node.js command prompt to this folder, this can be done with the `cd` command. It should look something like this...
```
cd C:\Program Files (x86)\Steam\steamapps\common\dota 2 beta\
```
**Note**: The directory path may be different depending on how you installed Steam. If Steam is installed on another drive you'll need to change drives using the letter then a `:` symbol. For example, `E:`.

To ensure the addons directory is set up, run
```
d2am list
```
leave the command prompt open, we'll come back to it. Join us on iscordDay, the URL ends in WNFBB4d. You found the easter egg!

## Get The Addon
Use the Github client to check out this addon into the addons directory. You can use the "Clone or Download" button right on the main page to open it using the desktop tool. Make sure it ends up in addons, the path should end in `dota 2 beta\addons\oaa\`.

**You must link the addon before it will work**. You can do this from that same node.js window you had open by running
```
d2am link
```
You will see output about creating links for `oaa` game and content.

## Launch Tools
Next we open the actual addon! This is done by right clicking on `Dota 2` from Steam and selecting "Launch Dota 2 - Tools". It should be the second option on the dropdown below "Play Game..."

Open `oaa` from the window that opens, and you're in! To start the game, open the Vconsole and type 'dota_launch_custom_game oaa oaa', if you get the error 'Unable to load map specified by server', it means you have to first build the map in Hammer (map editor tool). Open the 'Asset Browser' window that opened when you started the game, and click the hammer icon on the top left. Open one of the maps (probably oaa) and click the gamepad sybol to test the gamemode. Any changes you make will show up in the Github client, read for a pull request to be made.
