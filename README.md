# MapTool utilities for Tephra, the steampunk RPG

This is a set of macros and similar for playing [Tephra](https://tephrarpg.com/)
in [MapTool](https://www.rptools.net/toolbox/maptool/). Changelog is at the
bottom.

## Installation:

This pack depends on the tokens having the properties defined in the
`tephra.mtprops` campaign properties file, and the library token from
`Lib:tephra.rptok`. The campaign file `test.cmpgn` already has both of these
added, but the steps to making a new campaign file with the relevant stuff is
pretty easy.

1. In a (preferably new) MapTool campaign, edit the campaign preferences
   (edit -> Campaign properties...), and import (not import predefined!)
   `tephra.mtprops`.
2. Add this folder to your resource library, or copy `Lib:tephra.rptok` into a
   folder that is already there. Copy this token onto pretty much any map. I
   expect it will even work on the hidden layer, but I haven't tested it yet.
3. For each character you add, in the config tab set the type to "Tephra
   character", and import the macro set `skills_and_attributes.mtmacset` into
   their token macros. Important statistics (skills, combat stats, etc) should
   be set in the token properties.
4. Enjoy!

You might also want to fiddle around with the health and wounds bars, as well as
the states (currently the only one I've provided is the "grabbed" state).

## update 2.0: new features, QoL, bugfixes?

I have now added calculation of damage soak (damage class changes more
often than soak class does, so you can calculate your damage yourself),
as well as a button to roll priority. Combat, attribute and skill rolls
now also say the tier of the roll, for easier lookup. Health and wounds
are now shown on bars, which you can configure in the campaign settings.
Health and wounds now have macros for modifying them (x damage dealt,
taking a breather, one day of downtime). I've also added a "grabbed"
state, as my players keep grabbing enemies.

### Technical notes:

The exploding die is no longer implemented by hand, as it turns out
1d12e is the required syntax. The "dice" macro now handles adding the
bonuses/penalties, and ensuring that a 1 is a 1. Also, it now actually
returns a value, and doesn't just print stuff. Useful for things like
calculating roll tier.

The old Lib:dice library token is now called Lib:tephra, and is packaged
ready to use. No more chosing a redundant image and importing macros.
Just drag him in, and leave the default settings. Lib now also handles
hit points and wounds.
