* _Ever want to make vMenu restricted to certain people but don't know how?_
* _View below to see how and what's needed!_
* _The following files below are NOT changing the gameplay whatsoever, the original creators work still is the same, I just added templates to the files allowing for ease when it comes to permission making and restricting weaponry for your rp server(s)!_
* _You don't have to use the templates I made, you can still use the orginal creators files and choose what YOU want to be there and what you don't want!_

* ***

# Main things needed:
* _Original Script Links (UnModded)_
1. _Badger_Discord_API_: [Link](https://forum.cfx.re/t/release-badger-discord-api/1698464)
2. _DiscordAcePerms_: [Link](https://forum.cfx.re/t/discordaceperms-release/573044)
3. _Discord_perms_: [Link](https://forum.cfx.re/t/discordroles-a-proper-attempt-this-time/1579427)
4. _vMenu_: [Link](https://forum.cfx.re/t/vmenu/88868)

* ***

# Files included with the zipped file (Modded)
* _The stuff(s) below are modded to work already with DiscordAcePerms, all you have to do is change anything with "CHANGEME"_
* _Download the LATEST release to get the modded files._

* ***

# Templates:
|    Script        |                          Addon Template                                    |
|------------------|----------------------------------------------------------------------------|
| DiscordAcePerms  | {RoleID, "group.member"} \| (Example: {23129812837283, "group.staff"}) |
| vMenu            | add_prinicple group.member \| Adding perms: add_ace group.member "vMenu.VehicleSpawner.Addon" allow|

* ***

# How to hook the scripts together (Starting from scratch):

* So you wanna know how to hook discord_perms, Badger_Discord_API, vMenu, and DiscordAcePerms together... Awesome, lucky for you I know how to do that.

1. _Add all the scripts to your \resources folder or wherever you want them to be._
2. _Add these lines to your server.cfg exactly! There is a specific order they need to be started!_
```css
# Discord Related
ensure Badger_Discord_API
ensure DiscordAcePerms
ensure discordroles
ensure vMenu
exec resources/vMenu/config/permissions.cfg # Directory your permissions.cfg for vMenu is located!
```
3. _The scripts are in working order! Restart your server to see them start up._

* ***

# Customizing the scripts to match your server:
* _Badger_Discord_API:_
1. _Open the Config.lua, you should be able to see a bunch of other information regarding the script. Look for the top line stating __guild_ID__, you want to put your server's ID there. (If you don't know how to get your server's ID, view this video > [here](https://www.youtube.com/watch?v=NLWtSHWKbAI&ab_channel=GaugingGadgets)_
2. _After adding the guild_id, scroll down until you find __Bot_Token__, you want to connect your bot created from [Discord Developer Portal](https://discord.com/developers/docs/intro) (If you don't know how to do so, view this video > [Here](Link)_

* ***

* _DiscordAcePerms:_
1. _Open the config.lua_
2. _You should see some premade fields, however, your best bet is to delete them and add new ones._
3. _View the template fields below to add more fields:_
```css
roleList = {
    {RoleID, "group.name"}, -- Template
    {0, "group.member"}, -- General Member Role.
}
```
* _DiscordAcePerms works from top to bottm, i.e. the higher the rank is via discord, the lower on the list you want it to be; For exmaple:_
```css
roleList = {
    {RoleID, "group.name"}, -- Template
    {0, "group.member"}, -- General Member Role
    {2389473248972334, "group.founder"}, -- Server Founder
}
```

* ***

* _Discordperms_
1. _Add your Bot_Token you used with Badger_Discord_API into Discordperms._
2. _Add your guid_id that was put in Badger_Discord_API into Discordperms._

* ***

* _vMenu_
* _vMenu permission editing can be a challenge for most people, view the text below for easier understanding._
1. _Open vMenu's permission.cfg_
2. _Scroll down until you see the lines regarding adding principles (Usually around line 152)
3. _You want to copy the groups you have in DiscordAcePerms into vMenu by doing the following below:_
* DiscordAcePerms:
```css
roleList = {
    {RoleID, "group.name"}, -- Template
    {0, "group.member"}, -- General Member Role
    {2389473248972334, "group.founder"}, -- Server Founder
}
```
* vMenu
```css
add_principal group.member
add_principal group.founder
```
4. _Adding specific permissions for a group is easy than most people think. ~ Example regarding that is also shown below!_
```css
add_ace group.member "vMenu.VehicleSpawner.Addon" allow
```
* The following code line above will only allow players that are a MEMBER to spawn addon vehicles in your server!

# Further Support:
|    Discord User    |    Discord Server       |
|--------------------|-------------------------|
| 𝓕𝓪𝓭𝓲𝓷_𝓵𝓪𝔀𝓼#0001  | https://discord.gg/fdrp |
