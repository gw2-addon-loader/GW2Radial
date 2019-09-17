# GW2 Radial

An [*ArenaNET-approved<sup>TM</sup>*](https://www.reddit.com/r/Guildwars2/comments/746mar/mount_radial_menu_addon_very_alpha_much_untested/dnwqj9x/) addon to show a convenient, customizable [radial menu overlay](https://giant.gfycat.com/WarpedInsistentIrishterrier.mp4) to select a mount, novelty item and more, on the fly, for *Guild Wars 2: Path of Fire*. This addon is compatible with the Windows client only; it will not work with the Mac client.

This fork is managed by [GW2 Developement Community](https://discord.gg/VmREt7X) and uses addon loader/addon manager.

[![Build status](https://ci.appveyor.com/api/projects/status/437fhcd36bf0jkx5?svg=true)](https://ci.appveyor.com/project/megai2/gw2radial)

## Installation

Use [addon manager](https://github.com/fmmmlee/GW2-Addon-Manager)

## Usage
- When in game, press ``Shift+Alt+M`` for the options menu.
- Set a keybind to use the overlay. This is the only keybind you will use in practice.
- Set each game keybind for the mounts (you must set these first in your game options, under controls, after you've unlocked the mounts). These are used by the plugin to trigger mounting. They should be matching up like so: ![Setting your keybinds](https://i.imgur.com/gvQPQfX.png)
- Hold the main key to show the overlay, move the mouse in the desired direction, then release the key to trigger mounting/dismounting.

## Credits
- Cerulean Dream for providing me with the initial motivator and inspiration in making his AutoHotkey-based radial menu
- Ghost for the new mount art found in v0.3+
- [freepik](https://www.freepik.com/) for novelty art
- deltaconnected and Bhagawan for their amazing addons which helped frame this and direct the approach to take, including the ReShade compatibility fixes
- WoodenPotatoes for the great feedback and exposure, as well as the Spud Club for helping with testing
- /u/that_shaman for another really nice radial menu concept which requires far better Photoshop skills than I have to reproduce

## FAQ

### Q: I want to thank you in some way, how do I do that?

A: I do this for fun/because I wanted this to exist, but if you really want to, feel free to send me mail in game to my account ``FriendlyFire.6275`` and toss a few gold my way or just say hi!

### Q: What is the "show in center" keybind used for?

A: It's a convenience feature for Action Camera users. When using Action Camera, the cursor is hidden and replaced with a targeting reticule fixed in the middle of the screen. Since that means the radial menu would appear all over the place, that keybind can be used to make it show up in the middle of the screen instead. As a bonus, it'll recenter the mouse to the middle of the radial menu so it's as easy as possible to select a mount *and* it'll show a temporary cursor so you know exactly where you're pointing.

Unfortunately, I can't make this automatic (i.e. switching to that mode when Action Camera is enabled) without hooking game functions, which would then require this become closed source again to avoid cheaters using it. On top of that, I'd be far more likely to break the EULA, so I'm afraid it's off limits without an official API.

### Q: Can you make it so selecting a mount while already mounted will directly swap to the new mount?

No. I talked with GW2 staff about this and they've decided that the can of worms it could potentially open is not worth it. Unfortunately, you'll need to select the new mount you want to use twice, once to unmount and then again to remount. This will not change unless ArenaNet's policy on addons changes.

### Q: Can you make it so the addon doesn't send keys to the chat window?

No. Similarly to the previous question, I'd need to hook into the game in ways that the devs don't want to deal with. As a result, the best I can suggest is to use non-character keys for the mounts (e.g. the F-row).

### Q: Can I use this code for my project?

A: Absolutely! This whole repository is MIT licensed, so everything here is up for grabs. I would of course appreciate a small note or crediting if you do end up using something, but none of that is required.

### Q: I'm getting a bug/crash/issue that's not mentioned here, what do I do?

A: Please make an issue in the Github page and label it as ``bug`` or ``question`` as relevant to let me know, I'll do my best to help!

### Q: I have an idea for a new feature/new addon!

A: Feel free to make an issue in the Github page and label it as ``suggestion``!
