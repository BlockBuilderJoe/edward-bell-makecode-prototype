# MakeCode tutorial Markdown guide

This guide explains how to write a Markdown tutorial that opens inside
Minecraft Education Code Builder and behaves like a guided activity. It is
written for this repository, but the same structure can be reused for other
NPC-led quests.

## 1. The file and the NPC route

Put the English tutorial in the repository root. Use a short, stable filename
with no spaces, for example:

```text
mechanical-gardener.md
```

Register the file in `pxt.json`:

```json
{
  "files": [
    "main.ts",
    "mechanical-gardener.md"
  ]
}
```

The NPC opens the tutorial with a Code Builder navigation command. Use the
default branch after the tutorial has been merged:

```mcfunction
codebuilder navigate @s true https://minecraft.makecode.com/?ingame=1&ipc=1&noRunOnX=1&lockedEditor=1#tutorial:github:BlockBuilderJoe/edward-bell-makecode-prototype/mechanical-gardener
```

Use a language-specific route when the activity should open in a text editor:

```text
#tutorial:github:OWNER/REPOSITORY/tutorial-file       Blocks
#tutorial:js:github:OWNER/REPOSITORY/tutorial-file    JavaScript/Static TypeScript
#tutorial:py:github:OWNER/REPOSITORY/tutorial-file    Python
```

The route selects the editor; the filename selects the Markdown tutorial. A
single repository can contain as many activity files and NPC routes as needed.
Do not append a second `#branch-name` fragment to an in-world URL. For an
unmerged test, use a temporary public repository whose default branch contains
the test file.

## 2. Start every tutorial with control metadata

Place control metadata before the title. These options make the activity feel
like a guided lesson rather than a blank project:

```markdown
### @hideDone true
### @explicitHints true

# Mechanical Gardener
```

Use only the options the activity needs:

- Leave `@hideIteration` unset for a multi-page lesson: it hides Back, Next and
  the step counter. In Minecraft Education 1.26.32, a briefing followed by
  Predict became a dead end with this option enabled.
- `@hideDone true` removes the normal tutorial completion button when the game
  world is responsible for confirming success.
- Leave `@flyoutOnly` and `@unifiedToolbox` unset when the lesson requires
  categorized toolbox navigation, such as Agent and Advanced → Text. Test any
  alternate toolbox layout against the blocks the learner actually needs.
- `@explicitHints true` makes the parser use the authored `~ tutorialhint`
  delimiter. Verify hints are hidden, can be opened and can be dismissed.
  Without this metadata, prose-only hints can leak into captions with the raw
  delimiter. A hidden `ghost` fence does not establish a hint boundary.

Do not put executable code, a blank line, or a heading above the metadata.

## 3. Give the learner a safe starter program

Use `template` for a Blocks/JavaScript tutorial. The code appears in the
workspace before the first step:

````markdown
```template
agent.teleport(world(18, 57, 12), EAST)
agent.move(FORWARD, 1)
loops.pause(1000)
```
````

Use `python-template` for a Python tutorial:

````markdown
```python-template
agent.teleport(world(18, 57, 12), EAST)
agent.move(FORWARD, 1)
loops.pause(1000)
```
````

Keep the starter safe and deliberately incomplete when the learner is meant
to add a missing block or line. Avoid putting destructive `fill`, `clone`,
large `spawn`, or unrestricted command code in a starter program.

## 4. Structure the learning sequence

Use headings to create a clear ramp. A reliable sequence is:

1. Mission brief and success condition.
2. Predict what the starter will do.
3. Run the starter once and observe the result.
4. Add one missing block or line.
5. Test again and explain the feedback.
6. Extend or simplify the solution.

`@showdialog` opens a step as an introductory dialog:

```markdown
## Mission brief @showdialog

Your Agent must carry the signal from the gold tile to Bell 1 and return.
Predict the ending position before pressing Play.
```

Use normal Markdown for learner-facing instructions. Keep each step short and
describe exactly what should be changed, what Play should do, and what a
wrong result means.

## 5. Show the code the learner needs

Use a `blocks` fence for a Blocks example:

````markdown
```blocks
agent.move(FORWARD, 1)
loops.pause(1000)
agent.move(BACK, 1)
```
````

Use `python` for Python code:

````markdown
```python
agent.move(BACK, 1)
```
````

Use `typescript` for JavaScript/Static TypeScript text:

````markdown
```typescript
agent.move(FORWARD, 1)
```
````

For language-independent JavaScript/Python examples, `spy` can be used where
the target supports it. In this prototype, separate language-specific files
and routes are preferred when starter code, hints, or validation differ. Do
not assume that a Blocks snippet, Python snippet, and TypeScript snippet are
interchangeable: test each route in its intended editor.

## 6. Add hints, missing code, and validation

With `@explicitHints true`, add an expandable hint after the relevant step:

```markdown
#### ~ tutorialhint

The Agent needs to move back after the pause so it returns to the gold tile.
```

Use `@highlight` to draw attention to the next block or line and
`@validate-exists` when the step should check that a particular item exists.
The comment syntax follows the language:

````markdown
```blocks
// @highlight
agent.move(BACK, 1)
```

```python
# @highlight
agent.move(BACK, 1)
```
````

The most useful missing-code instruction names the exact location, spelling,
direction, and value to enter. Always include a recovery hint such as “stop,
choose Retry, correct this step, and press Play again”.

## 7. Localise the tutorial

Keep the English file in the repository root and create a matching Welsh file
with the same basename:

```text
mechanical-gardener.md
_locales/cy/mechanical-gardener.md
```

Add both paths to `pxt.json`. The Welsh file must preserve the same:

- metadata directives;
- code fences and executable code;
- tutorial headings and step order;
- filenames, anchors, and validation markers.

Only learner-facing prose should be replaced. Welsh placeholder content in
this prototype must remain clearly marked Lorem Ipsum until a human Welsh
reviewer supplies the final copy. Do not use AI-generated Welsh.

For Welsh testing, add `liveforcelang=cy&skipgithubcache=1` to the URL. The
cache bypass matters because Code Builder can retain an older GitHub tutorial
copy for about an hour. MakeCode's interface and built-in block labels are a
separate translation layer managed through the
[MakeCode Welsh Crowdin project](https://crowdin.com/project/makecode/cy).

## 8. Connect the activity to the world

The Markdown controls the Code Builder lesson; the world controls NPC text,
buttons, feedback, reset functions, and success detection. Keep those layers
separate:

- NPC button: calls one named `function`.
- Function: starts or resets the quest, then runs `codebuilder navigate`.
- Tutorial: teaches the code and tells the learner what to press.
- World logic: checks the result and gives success or retry feedback.

Give every activity a reset or retry path. If learners can use JavaScript or
Python, assume they may experiment with powerful APIs and accidentally alter
the prototype world. A reset function or “return to quest” NPC button is safer
than requiring them to download a new world.

## 9. Register, test, and publish

Before committing a tutorial:

1. Add every English and locale file to `pxt.json`.
2. Increment the `pxt.json` version.
3. Check the Markdown fences, metadata, URLs, and code indentation.
4. Open the exact English route in Minecraft Education.
5. Open the Welsh route with `liveforcelang=cy&skipgithubcache=1`.
6. Test the complete NPC → Code Builder → Play → world feedback flow.
7. Test Retry/reset after an incorrect solution and after a deliberately
   altered world state.
8. Publish a new immutable Git tag/release only after the client test passes.

Use the MakeCode tutorial checker where available. A GitHub page loading is not
enough: the tutorial must open in Code Builder, show the intended starter code,
accept the intended learner change, and return useful feedback from the world.

## 10. Common mistakes

- **The NPC opens the wrong activity:** check the final filename in the route
  and the function called by the NPC.
- **Python opens as Blocks:** use `#tutorial:py:` and `python-template`.
- **The latest Markdown is missing:** bump `pxt.json` version, use
  `skipgithubcache=1`, and verify the exact default-branch source. These do not
  prove what the client loaded: Raglan retained an older copy during a retest.
  A fresh temporary public QA repository and disposable world handoff resolved
  that ambiguity. Record the QA URL and immutable source hashes.
- **Next/Back is missing:** remove `@hideIteration` from multi-page lessons and
  exercise every page in both directions, including a return to `@showdialog`.
- **Raw tutorialhint text or answers appear before Hint:** enable
  `@explicitHints true` and test both prose-only and rendered block hints.
- **The tutorial is blank:** check that its file is listed in `pxt.json` and
  that the first metadata lines appear before the title.
- **Welsh remains English:** check the matching `_locales/cy/` filename, use
  `liveforcelang=cy`, and bypass the GitHub cache.
- **Learners cannot recover:** add a world reset/retry function and a visible
  NPC route back to the activity.

## Client evidence behind these defaults

Raglan UI regression run `5635afca-71aa-4db6-9378-94acd1b4cb81` on 1 October
2026 used Minecraft Education 1.26.32 and tutorial revision
`a90690331584c0be189f152c38685c9fe3994330` (`pxt.json` 0.0.3). Both actual Mentor
buttons opened the QA lessons. All 9 Bell and 13 Garden pages, all 11 on-request
hints, and the categorized Agent inspection and Text join blocks were checked.
Program execution, world success, reset/replay, Welsh and multiplayer were
separate pending cases; this evidence does not certify those paths.

The parser implementation is [Microsoft PXT tutorial.ts](https://github.com/microsoft/pxt/blob/master/pxtlib/tutorial.ts),
particularly `parseTutorialHint` after hidden snippets are stripped. Client
behaviour settles any discrepancy with prose descriptions of the options.
