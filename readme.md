# GW2 Radial

# This version is no longer functional. Please see the main release here: https://github.com/Friendly0Fire/GW2Radial

---------------

An [*ArenaNET-approved<sup>TM</sup>*](https://www.reddit.com/r/Guildwars2/comments/746mar/mount_radial_menu_addon_very_alpha_much_untested/dnwqj9x/) addon to show a convenient, customizable radial menu overlay to select a mount, novelty item and more, on the fly, for *Guild Wars 2*.

[![GW2Radial Demo](https://thumbs.gfycat.com/IgnorantIllfatedCrocodileskink-size_restricted.gif)](https://gfycat.com/ignorantillfatedcrocodileskink)
(click to see a better video)

**Highlights include:**
* Predefined menus for mounts, novelties and markers
* Simple system to add custom radial menus and share them
* Conditional menus, making it possible to have multiple menus on the same key depending on the situation
* Smart automount: Skimmer is auto-selected when underwater or Warclaw when in WvW
* Input queuing: combat (and underwater without the Skimmer mastery) prevents mount usage, so the selected mount is "queued" until out of combat:

[![Input Queuing GW2Radial Demo](https://thumbs.gfycat.com/NegativeBlushingHake-size_restricted.gif)](https://gfycat.com/negativeblushinghake)
(click to see a better video)

## Installation

### Automatic Installation
- Download the [GW2 Addon Manager](https://github.com/gw2-addon-loader/GW2-Addon-Manager).
- From the list of addons, select GW2Radial.
- Click Update.
- Run the game!

### Manual Installation
- Download and extract the archive ``gw2radial_d3d9.zip`` found in the [latest release](https://github.com/gw2-addon-loader/GW2Radial/releases/latest).
- Rename ``gw2addon_gw2radial_d3d9.dll`` to ``d3d9.dll`` and place it in your bin64 directory (default path: ``C:\Program Files\Guild Wars 2\bin64``).
- Run the game! If everything was setup properly, you should be greeted by a prompt on your first launch.

## Usage
- When in game, press ``Shift+Alt+M`` for the options menu.
- Set a keybind to use the overlay. This is the only keybind you will use in practice.
- Set each game keybind for the mounts (you must set these first in your game options, under controls, after you've unlocked the mounts). These are used by the plugin to trigger mounting. They should be matching up like so: ![Setting your keybinds](https://i.imgur.com/gvQPQfX.png)
- Hold the main key to show the overlay, move the mouse in the desired direction, then release the key to trigger mounting/dismounting.

## Custom Radial Menus [New!]
Please refer to the readme in the `custom_examples` folder for more information on how to create or download new menus.

## Credits
- @QuitarHero and @TanukiSoup for extensive testing
- Cerulean Dream for providing me with the initial motivator and inspiration in making his AutoHotkey-based radial menu
- Ghost for the new mount art found in v0.3+
- [freepik](https://www.freepik.com/) for novelty art
- deltaconnected and Bhagawan for their amazing addons which helped frame this and direct the approach to take, including the ReShade compatibility fixes
- WoodenPotatoes for the great feedback and exposure, as well as the Spud Club for helping with testing
- /u/that_shaman for another really nice radial menu concept which requires far better Photoshop skills than I have to reproduce

## FAQ

### Q: I want to thank you in some way, how do I do that?

A: I do this for fun/because I wanted this to exist, but if you really want to, feel free to send me mail in game to my account ``FriendlyFire.6275`` and toss a few gold my way or just say hi!

### Q: I'm having a crash on launch (maybe mentioning "Coherent DLL"), what do?

A: There seems to be a lot of potential reasons for this particular crash. [BGDM's website](https://web.archive.org/web/20200409062402/http://gw2bgdm.blogspot.com/p/faq.html#2.5) lists quite a few. I'd especially recommend making sure you have the very latest [VC++ Redist](https://go.microsoft.com/fwlink/?LinkId=746572). Please also ensure that your graphics card drivers are up-to-date.

The crash may also be related to the Windows 10 Ransomware Protection system; you can add `Gw2-64.exe` and `CoherentUI_Host.exe` to the exception list following [these instructions](https://www.windowscentral.com/how-allow-blocked-apps-ransomware-protection-windows-10-october-2018-update) (thanks @Myster-Marz for the tip).

### Q: The addon doesn't seem to be loading at all, what's wrong?

A: There can be a few reasons for this, but the most common one is that you're using a special shortcut which skips the login prompt and boots the game directly. In this specific circumstance, you must put the addon's ``d3d9.dll`` directly next to the game's ``Gw2-64.exe`` (default path: ``C:\Program Files\Guild Wars 2``).

### Q: The game crashes with an error message mentioning "RivaTuner Statistics Server/RTSS", what's that?

A: RivaTuner Statistics Server is a component of some GPU management software such as MSI Afterburner which displays some information overlaid on top of games, such as FPS, temperatures, clocks, etc. Unfortunately, RTSS works in such a way that it breaks this addon, and as a result you must disable RTSS before launching the game. Fortunately, you do not have to uninstall RTSS or MSI Afterburner, simply shutting down the server (which can be done from the notification area located on the right side of the taskbar) before launching the game is sufficient. ![Shutting down RTSS](https://i.imgur.com/O9t9qZq.png)

### Q: I want to load up ArcDPS/GW2Hook/something else which also needs to be called ``d3d9.dll``, how do I load both?

A: You have three options: the first option is to use the GW2 Addon Loader through the [GW2 Addon Manager](https://github.com/gw2-addon-loader/GW2-Addon-Manager), **which is the recommended approach**.

Otherwise, either the other thing you want to run supports *chainloading* this, in which case you should look up the documentation for that plugin (e.g. ArcDPS supports chainloading by renaming this plugin to ``d3d9_chainload.dll``), or you can make this plugin chainload something else by renaming that other plugin to ``d3d9_mchain.dll``.

The most common use case would be combining ArcDPS, GW2Hook and this. For this instance, I heavily recommend setting things up as follows:
- ArcDPS is named ``d3d9.dll``.
- GW2Radial is named ``d3d9_chainload.dll``.
- GW2Hook is named ``ReShade64.dll``.

*N.B. If your Windows options hide file extensions (which is the default, you can confirm by looking at whether the game's file name is "Gw2-64.exe" or just "Gw2-64") leave out the ".dll" part of the file names (i.e. use "d3d9", "d3d9_chainload" and "ReShade64" respectively).

This should allow all addons to load properly. Note that there is special code present within GW2Radial to load GW2Hook properly, but this could break unexpectedly if GW2Hook/Reshade changes.

Finally, note that combining addons is largely unsupported. I will attempt to keep ArcDPS and d912pxy compatible with this, but that is the most I am able to do in a reasonable amount of time.

### Q: What is the "show in center" keybind used for?

A: It's a convenience feature for Action Camera users. When using Action Camera, the cursor is hidden and replaced with a targeting reticule fixed in the middle of the screen. Since that means the radial menu would appear all over the place, that keybind can be used to make it show up in the middle of the screen instead. As a bonus, it'll recenter the mouse to the middle of the radial menu so it's as easy as possible to select a mount *and* it'll show a temporary cursor so you know exactly where you're pointing.

Unfortunately, I can't make this automatic (i.e. switching to that mode when Action Camera is enabled) without hooking game functions, which would then require this become closed source again to avoid cheaters using it. On top of that, I'd be far more likely to break the EULA, so I'm afraid it's off limits without an official API.

### Q: Can you make it so selecting a mount while already mounted will directly swap to the new mount?

No. I talked with GW2 staff about this and they've decided that the can of worms it could potentially open is not worth it. Unfortunately, you'll need to select the new mount you want to use twice, once to unmount and then again to remount. This will not change unless ArenaNet's policy on addons changes.

### Q: Can I use this code for my project?

A: Absolutely! This whole repository is MIT licensed, so everything here is up for grabs. I would of course appreciate a small note or crediting if you do end up using something, but none of that is required.

### Q: I'm getting a bug/crash/issue that's not mentioned here, what do I do?

A: Please make an issue in the Github page and label it as ``bug`` or ``question`` as relevant to let me know, I'll do my best to help!

### Q: I have an idea for a new feature/new addon!

A: Feel free to make an issue in the Github page and label it as ``suggestion``!
