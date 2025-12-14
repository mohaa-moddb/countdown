# Countdown - Version 1.7 - Release date: 10:22 30/09/2006

## Change Log

### 1.7
- fixed typo in player_radio.scr that stopped the radio timer working.

### 1.6b
- Fixed hold time.
- Fixed pass radio.
- Radio Hold time Feature, The players must not hold the radio for this amount of time, or they will drop it, unable to pick it up again.
- Pass the radio to other members of your team.

### 1.5
- Changed the way countdownstarts and removed dmprecache conflicts.
- tiny tweaks to the hud draw.

### 1.4
- New Map change code
- Moved gametype string above wait's with a check to auto correct the game type string if countdown should not run.

### 1.3
- Merged Seperate Game pk3's into one pk3 again

#### All Following changes only apply to SH Countdown=

- Changed radio targetname to fix conflict bug on berlin
- Fixed berlin Spawn point
- Fixed mp_flughafen_tow spawn points
- Added mp_ardennes_tow spawn points
- Fixed Map change for TDM
- Map Change in TOW Checked

### 1.2
- Added new countdown_idle cvar to respawn radio
- Added new map change for SH
- No "radio location" for unsupported maps
- Added radio locations for all SH maps as well as all AA maps.

### 1.1
- Added new countdown_rounds cvar - To change map
- Added New countdown_light cvar - To glow radio player
- Added new countdown_locate cvar - To announce radio location
- Added more random locations for Stock AA Maps

## Description

This mod add's a radio to maps. Each team has
to find and keep the radio in their possession for the counter on the
oposite team to countdown. The player who finds the radio has the job of 
staying alive, if they die or leave the radio drops to the floor ready
to be found again. Once the countdown hits 0. The oposite team will explode.

This mod will probably be included in the next update of Admin-Pro.
The use of Admin-Pro will bring about many additional advantages and settings.

## Supported gametypes:

The mod should run on all game team types.

## Supported games and maps

All maps in AA and SH are supported. The mod will work for BT but only on the supported maps.
these maps are maps found in SH and AA.

## Possible Conflicts

The mod uses the global/DMprecache.scr file. Any mod using this 
file may cause a conflict with this mod.

With the Admin-pro version the mod will not use that file. 

## Supporting maps

All the stock AA maps are supported. More radio spawn points and 
custom maps can be easily added. 


## Adding more radio spawn points

The radio spawn points for the maps are held in script named after the maps in  the countdown folder.

The mod will choose between a random number of starting positions. 
I only added one but you can add as many as you want.
By adding them into an array of local.origin and then ending with the local.origin variable.
Each time you add an origin use the same format but increase the number by one for the index, for example.

main:

	local.origin[0] = ( 504 -5128 -447 )
	local.origin[1] = ( -1414 162 -127 )
	local.origin[2] = ( 120 96 9 )

end  local.origin

## Adding more maps

The mod searches for a file inside countdown folder named after the map name. 
If it is not found. it will not run. So to make it run. Create a file named after your map
and place it in the countdown folder.

Inside this file you should place the following code

	main:

		local.origin[0] = ( COORD )

	end  local.origin

In place of the word 'COORD' you should place the coordinates for the spawning point of the radio.

## Cvars

### countdown

Turns the mod on and off.
0 = off, anything else is on.

### countdown_hold_for

Sets the time in seconds, That the player is allowed to hold the radio for.
If they are holding the radio for longer than this time, They will be forced to drop the radio.

### countdown_death_print

If set to 1, then it will print the location of the player when they die.

### countdown_time

Sets the time for the mod to countdown from
default: 03:00
When changing this cvar. It must remain within 90:00. 5 characters long including ":"

### countdown_light

make the player with the radio glow
0 = off, anything else = on

### countdown_rounds

This allows you to set fraglimit and timelimit 0 and use countdown_rounds ot change the map.
After this limit of rounds has been reached the map will change. 0 - no limit

### countdown_locate 

Set default to 15. Each 15 seconds the place of the radio will be announced on supported maps into
the hud. If set 0 the location will not show. The location displays for 3 seconds and then fades out.

### countdown_idle

Set default to 300. When the radio is dropped or spawned after this amount of time in seconds the radio 
will respawn to another random location for that map. 

## Setting up your config

If you are not going to use normal fraglimit or timelimit to change the map then you need to add
the following to your config only if you are going to use another countdown_rounds setting other 
then default, default being 3 rounds.

	seta countdown_rounds 5

This will create the cvar and set countdown rounds to 5. Otherwise it will be 3.

If you do not want to use countdown_rounds then set:

	seta countdown_rounds 0

The countdown_rounds will not effect the map change.

## How to install ?

Place the zzz_countdown.pk3 inside your maintt/mainta/main folder.

## Contact me
Email : elgan.sayer@gmail.com

www.mods-r-us.net

Thanx to everyone who helped test!
Thank to Mefy for use of his location script!


