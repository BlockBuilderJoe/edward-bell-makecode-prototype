# Edward's Bell Communication System

This repository hosts the MakeCode tutorial used by the CADW MakerCode world for Quest 2C.

Open it in Minecraft MakeCode:

https://minecraft.makecode.com/?ingame=1&ipc=1&noRunOnX=1&lockedEditor=1#tutorial:https://github.com/BlockBuilderJoe/edward-bell-makecode-prototype/edward-bell-play-v2

Practice tutorial:

https://minecraft.makecode.com/?ingame=1&ipc=1&noRunOnX=1&lockedEditor=1#tutorial:https://github.com/BlockBuilderJoe/edward-bell-makecode-prototype/practice-bell-play-v2

Both tutorials run once from top to bottom when the learner presses the green
Play button. No Minecraft chat command is required. The practice checks whether
the Agent returned to the gold tile and gives an immediate success or retry
message; the world supplies wrong-bell and wrong-order feedback for the full SOS.

Example world (method demonstration only, not a tested end product):

https://github.com/BlockBuilderJoe/edward-bell-makecode-prototype/releases/download/v0.0.8/Quest-2C-Edwards-Bell-MakeCode-Prototype.mcworld

Version `v0.0.8` is deliberately a localisation test build. Select Welsh in
Minecraft Education and look for `[PRAWF CYMRAEG]`, `[CY]` and `Lorem ipsum`
in the opening HUD message, Mentor name, first NPC page and its first buttons.
These markers are placeholders, not approved Welsh copy.

## Localising the tutorial into Welsh

Welsh tutorial copies live in `_locales/cy/`. MakeCode selects them when its
language is Welsh; this link requests the Welsh SOS tutorial explicitly:

https://minecraft.makecode.com/?lang=cy&ingame=1&ipc=1&noRunOnX=1&lockedEditor=1#tutorial:https://github.com/BlockBuilderJoe/edward-bell-makecode-prototype/edward-bell-play-v2

1. Finish or update the English tutorial in the repository root first.
2. Create the matching Welsh file at `_locales/cy/<same-filename>.md`.
3. Translate learner-facing headings, instructions and hints. Keep MakeCode
   directives, fenced code, block identifiers and TypeScript unchanged so both
   languages run the same program.
4. Keep the English and Welsh files in the same step order, and add any new
   tutorial filename to `pxt.json`.
5. Test both the normal link and the `?lang=cy` link above. Check that every
   step, hint and code block appears and that Play runs the same sequence.
6. Increment the version in `pxt.json`, commit the English and Welsh changes
   together, then publish a new tag/release so MakeCode refreshes its cache.

The Minecraft world uses a second localisation layer for NPC dialogue, buttons
and feedback. World packs should use translation keys rather than hard-coded
sentences, with the same key present in `en_GB.lang`, `en_US.lang` and
`cy_CY.lang`. Ensure `languages.json` lists Welsh, bump the resource-pack
version after text changes, rebuild the `.mcworld`, and test the English and
Welsh learner routes from the NPC through to MakeCode.
