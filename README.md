# Edward's Bell Communication System

This repository hosts the guided Minecraft Education MakeCode prototype for
CADW Quest 2C. It demonstrates the proposed NPC-to-MakeCode handoff,
predict-code-test-debug learning flow, and English/Welsh localisation method.
It is a method demonstration, not a finished or fully tested learner activity.

## Open the tutorials

English SOS tutorial:

https://minecraft.makecode.com/?ingame=1&ipc=1&noRunOnX=1&lockedEditor=1#tutorial:github:BlockBuilderJoe/edward-bell-makecode-prototype/edward-bell-play-v2

Welsh-locale SOS tutorial:

https://minecraft.makecode.com/?liveforcelang=cy&skipgithubcache=1&ingame=1&ipc=1&noRunOnX=1&lockedEditor=1#tutorial:github:BlockBuilderJoe/edward-bell-makecode-prototype/edward-bell-play-v2

English practice tutorial:

https://minecraft.makecode.com/?ingame=1&ipc=1&noRunOnX=1&lockedEditor=1#tutorial:github:BlockBuilderJoe/edward-bell-makecode-prototype/practice-bell-play-v2

Welsh-locale practice tutorial:

https://minecraft.makecode.com/?liveforcelang=cy&skipgithubcache=1&ingame=1&ipc=1&noRunOnX=1&lockedEditor=1#tutorial:github:BlockBuilderJoe/edward-bell-makecode-prototype/practice-bell-play-v2

## Python editor example

The production repository now also contains a small Python version of the Bell
practice. It is a separate example for testing text-code routing; the released
world still defaults to the guided Blocks flow.

Open the Python example in Code Builder:

https://minecraft.makecode.com/?forcelang=en&skipgithubcache=1&ingame=1&ipc=1&noRunOnX=1&lockedEditor=1#tutorial:py:github:BlockBuilderJoe/edward-bell-makecode-prototype/python-bell-test

The route uses `#tutorial:py:` to select Python, `python-template` for starter
code, and `python` snippets for the missing line and completed example. The
matching Welsh placeholder is registered at `_locales/cy/python-bell-test.md`.
For the NPC handoff pattern and the equivalent JavaScript route, see
[CODEBUILDER-LANGUAGES.md](https://github.com/BlockBuilderJoe/edward-bell-makecode-python-test/blob/master/CODEBUILDER-LANGUAGES.md).

## Long text window test

The deliberately oversized Lorem Ipsum example is available here:

https://minecraft.makecode.com/?skipgithubcache=1&ingame=1&ipc=1&noRunOnX=1&lockedEditor=1#tutorial:github:BlockBuilderJoe/edward-bell-makecode-prototype/long-text-example

It is a layout test, not learner content. The companion world adds a **Text
Length Test** button to the Mentor so the tutorial can be opened directly from
Minecraft Education.

## Markdown authoring guide

For the full tutorial structure, code fences, language routes, hints,
localisation, NPC handoff, reset paths, and testing checklist, see
[MARKDOWN-GUIDE.md](MARKDOWN-GUIDE.md).

Both tutorials run from top to bottom when the learner presses the green Play
button. No Minecraft chat command is required. The practice checks whether the
Agent returned to the gold tile and gives an immediate success or retry message;
the world supplies wrong-bell and wrong-order feedback for the full SOS.

## Example world

Download the latest example world:

https://github.com/BlockBuilderJoe/edward-bell-makecode-prototype/releases/download/v0.0.10/Quest-2C-Edwards-Bell-MakeCode-Prototype.mcworld

Version `v0.0.10` is a localisation-mechanism test build. The Welsh-locale world
copy and tutorial copy deliberately contain `[WELSH PLACEHOLDER]`, `[CY]`, and
Lorem Ipsum. This is not Welsh translation, AI-generated Welsh, approved Welsh,
or learner-ready content.

**Verified 14 July 2026:** Minecraft Education loaded the Welsh world strings,
opened MakeCode automatically, bypassed its stale GitHub tutorial cache,
requested MakeCode's Welsh locale, and selected the tutorial Markdown from
`_locales/cy/`. This verifies the routing mechanism, not the quality or
completeness of any Welsh language content.

## How localisation is divided

There are three separate localisation layers:

1. **Tutorial instructions:** this repository stores English Markdown in the
   repository root and matching Welsh files in `_locales/cy/`.
2. **MakeCode interface and block labels:** MakeCode supplies these from its
   translation service. Welsh contributions and reviews are managed in the
   [MakeCode Welsh Crowdin project](https://crowdin.com/project/makecode/cy).
3. **Minecraft world text:** the resource pack stores NPC dialogue, buttons,
   titles, and feedback in `en_GB.lang`, `en_US.lang`, and `cy_CY.lang`.

`liveforcelang=cy` requests approved Welsh strings from MakeCode's translation
service. `skipgithubcache=1` prevents Code Builder from reusing an older English
copy of this GitHub tutorial during localisation testing. If a MakeCode control
or Minecraft block remains in English, it is not controlled by the Markdown in
this repository. Add or review that string in Crowdin, wait for it to be
approved and published by MakeCode, then retest the Welsh-locale link.

## Preparing the tutorial for human Welsh localisation

1. Finish or update the English tutorial in the repository root first.
2. Create or update the matching `_locales/cy/<same-filename>.md` file.
3. Have a human Welsh-language contributor translate learner-facing headings,
   instructions, and hints. Do not use AI-generated Welsh.
4. Keep MakeCode directives, fenced code, block identifiers, TypeScript, and
   tutorial step order identical so both languages execute the same program.
5. Add every English and Welsh tutorial filename to the `files` array in
   `pxt.json`, then increment its version.
6. Test the English and `?liveforcelang=cy&skipgithubcache=1` links. Check every
   step, hint, block, and the green Play flow in Minecraft Education.
7. Update the world's matching translation keys, increment both embedded pack
   versions, rebuild the `.mcworld`, and retest the complete NPC-to-MakeCode
   handoff in both languages.
8. Commit the English and human-supplied Welsh changes together and publish a
   new tag/release so MakeCode and world downloads use an immutable version.

## Editing and review

Use a branch and pull request for normal content changes so English, Welsh, and
code changes can be reviewed together. Send Joe the GitHub usernames that need
collaborator access to this repository.

Do not append a second `#branch-name` fragment to an in-world MakeCode URL.
Minecraft Code Builder cannot reliably route that form. For pre-merge testing,
use a temporary public test repository whose default branch contains the test
content; after approval, merge the files here and use the branch-free links
shown above.
