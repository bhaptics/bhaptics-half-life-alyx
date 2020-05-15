# bhaptics-half-life-alyx

## SUMMARY

bHaptics Tactsuit integration mod for Half-Life Alyx. Many different haptic effects on Vest, 
Arms and Face including feedback from enemy unarmed, gun damage, player weapon fire, reload,
item storing/retrieving, healing, heartbeat, gravity glove use and more.


## INSTALLATION
Manual Installation: Extract the contents of the Scripts rar file inside your “Steam\steamapps\common\Half-Life Alyx” directory so that you’ll have a vscripts folder like this: “Steam\steamapps\common\Half-Life Alyx\game\hlvr\scripts\vscripts”.

Extract the contents of the Application rar file anywhere you want. 
Run TactsuitAlyx.exe, set your Half-Life Alyx folder correctly and it’s ready to be used. Run your bhaptics player, 
press Start button on the app. You can change the settings from Settings button.


## REQUIREMENTS
You need to add -condebug to your Half-Life Alyx launch options like this:

![image](https://user-images.githubusercontent.com/1837913/82000781-5abec780-9694-11ea-9fb5-61b049c7f4f5.png)


## DESCRIPTION
This mod communicates with Tactsuit when certain events are detected in Half-Life Alyx to give you haptic feedback. It supports Tactot(Haptic Vest for Torso), Tactosy(Haptic Sleeve for Arms) and Tactal(Haptic Face Cushion for HMD)
These are the currently implemented haptic effects:


###  When player is attacked: (These feedbacks are applied to the angle they come from if possible)
* Unarmed attacks by different creatures on head and vest (14 different effects based on creature types)
* Grabbed by barnacle effect on vest
* Gun hits by enemies on head and vest (Different effects based on enemy types)
* Grenade explosion effect on vest (Different effects based on grenade type)
* Different effects on vest when player is killed by different causes (blast, burn, shock, radiation, poison etc.)
* Other effects caused by explosions etc.

### When player is attacking: 
* Player firing a weapon and grenade launch effect on arm (4 different effects based on weapon fire types)
* Fallback effects for gun fire on vest if arm devices are not detected(3 different fallback effects)
* Weapon fire kickback effect on vest near shoulder. (3 different kickback effects)

### Special Effects:
* Heartbeat effects on the vest when your health is low and very low (2 different effects).
* Health pen using effect on vest
* Health station using effect on vest and arm
* Player weapon eject clip/reload/open and close casing effects on arm
* Player backpack clip/resin store/retrieve effects(on shoulder). (4 effects for each side)
* Player item holder store/remove effects(on arms)
* Shock on arm effect when inserting device key to hologram
* Gravity glove lock on effect, pull effect, catch effect (3 different effects)
* Cough effect on vest and head when coughing.


## CONFIGURATION

This mod has a Settings window in the application. 
You can modify everything in the mod using that including adjusting intensity of the effects, 
adjusting durations etc. Also you can test the effects right there in the settings window
by clicking their labels to achieve intended intensity or duration settings.

![image](https://user-images.githubusercontent.com/1837913/82000813-72964b80-9694-11ea-87e3-715fef2d5a4d.png)


## COMPATIBILITY

This mod comes with scripts folder installed. 
If you have any other mod that adds “game/hlvr/scripts/vscripts/init.lua” file, then you need to manually merge the files.

Open init.lua with a text editor like notepad or notepad++ and at the end of the file you’ll see:

```
function include_script(script)
	if DoIncludeScript(script, _G) then
		print("...Included script "..script)
	end
end

-- ADD USER SCRIPTS HERE
Msg("Loading user scripts...")

include_script("user/tactsuit.lua")
```

Make sure this section is there, and include_script("user/tactsuit.lua") line is there for this mod, 
and add other mod’s content too to include any other scripts etc.


## CHANGELOG
* 1.0:
Official release.

* Beta 3:
Modified coughing detection and play code to make it more consistent. Added coughing sleep duration to settings.

* Beta 2: 
Half-Life Alyx folder is now saved in the config, so it’s selected automatically on reopen.

