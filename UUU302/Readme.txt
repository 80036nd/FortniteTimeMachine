Universal Unreal Engine 4 Unlocker (UUU)
==========================================================
(for reasonably recent engines, 2016+)

To get started, run the UuuClient.exe. If you run the game as administrator, you have to run the UuuClient.exe also 
as administrator. After you've started the UuuClient.exe, click 'Select' to select the game process to inject the dll into. 
When you've selected the game to inject the dll into, click the 'Inject dll' button. 

That's it! When the dll is injected successfully, you'll get info on the screen when the camera is found, and the rest of the 
UuuClient GUI tabs are enabled. Please check the 'Available functionality' tab to see which features of the UUU are available
to you. 

To configure the key bindings, use the Key bindings tab, and to configure the camera and other settings, use the Configuration tab.

MULTIPLE PAUSE/TIMESTOP SYSTEMS
=====================================
The UUU has two ways to pause the game: using the normal UWorld::IsPaused hack, (Numpad 0), and one using the slomo command code, (Page down).
You can use either one, if they're both found of course. Numpad 0 is a hard-pause which could lead to TAA jitter in the scene. You can 
remove that by stepping down the AA a bit, using: r.postprocessaaquality 2 in the console. To set it back, use r.postprocessaaquality 6.
The downside of that is that cutscenes might play on and the lower quality AA might remove some effects. 

The slomo based pause using Page Down doesn't suffer from TAA jitter, and can pause most, if not all, cutscenes as well (except audio in some
situations). In general, if the latter is supported, you should use the slomo based pause. 

BUILT-IN CAMERA SYSTEM
=========================
The UUU comes with a built-in sophisticated camera system you can configure yourself using the keybinds in the Configuration tab. You can
select which device you'll use for camera movement (By default both kb/mouse and controller are selected). 

TROUBLESHOOTING
===================
If you enable the debug camera with toggledebugcamera, you might see info on the screen. Remove that by pressing backspace (or controller X).

You might get an error with older games that it can't find the EngineVersion key and it will fall back to the default version.
It will then try to auto-detect which engine version is being used. If that fails, it's likely not going to work. If it succeeds, 
the console can be created most likely. 

If you get AOB errors when injecting the dll, it might be the engine's code hasn't been fully initialized yet and AOB scanning can't
find it. Simply load a level and try again by pressing CTRL+END. 

The built-in HUD toggle might not work if the HUD is built with the simple HUD system in UE4. This is ok, the HUD will then automatically
be hidden when the debugcamera is enabled through the console. If the HUD is made with the more sophisticated system in UE4 (UMG), the hud
will be hidden if the code has been found. In-game, you can try 'showhud 0' (without the quotes) to hide the hud and 'showhud 1' to show it again.
This might not always work, it depends per game. 

It might be you see an error about AllowCheats not being found. This might not be a problem: some games don't disable this or have the code
which selects whether cheats are allowed at all stripped out and allow cheats regardless. All you have to do is type `Enablecheats 1` (without
the quotes) in the console to enable the debug camera.

In-game console doesn't open
---------------------------------
If the console doesn't open when pressing ~, but all AOBs are found, please do the following:
In the UuuClient, go to the Configuration tab. In there you can select the key to open the in-game console.
By default the key is '~' or 'Tilde'. Please select a key you don't use in-game and which is available on your
keyboard without using Shift. E.g. if you have a French keyboard (Azerty), you can choose 'Dollar ($)', which means you can 
press the $ key to open the console, which is right above the Enter key on most Azerty keyboards. 

Alternatively, you can choose a US-en keyboard layout, or add a custom key to the ini file of your game, but this might not
always work:

Go to:
c:\users\<your username>\AppData\Local\gamename\Saved\Config\WindowsNoEditor

open Input.ini
Add (pay attention to the empty line!):

[/Script/Engine.InputSettings]
ConsoleKey=Tilde

Save and set to readonly. You can also set it to another key, e.g. K. 
