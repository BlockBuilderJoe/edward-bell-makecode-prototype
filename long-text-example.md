### @hideIteration true
### @hideDone true
### @flyoutOnly 1
### @unifiedToolbox true
### @explicitHints 1

# Long Text Window Example

This is a deliberately oversized Lorem Ipsum example. It is a visual test of
how much guided text a learner can read inside the Minecraft Education Code
Builder window. The words are placeholder text, not lesson content.

```template
player.say("Starter program ready")
loops.pause(1000)
```

## Mission brief @showdialog

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer vitae sem
quis nibh porta aliquet. Curabitur luctus, sapien a tincidunt commodo, justo
turpis consequat arcu, vitae facilisis erat massa sed neque. This opening
dialogue is intentionally long enough to test wrapping, scrolling, and the
amount of text visible before the learner reaches the code.

Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere
cubilia curae; Mauris dignissim, nibh non tincidunt vulputate, justo neque
blandit massa, at posuere lectus sem id erat. Suspendisse potenti. Donec
fermentum, lorem a pretium laoreet, massa justo faucibus nibh, vitae commodo
urna ipsum at erat.

## Step 1: Read before pressing Play

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent consequat
finibus eros, sed luctus arcu consequat at. Aenean eget neque non nisl
ultricies posuere. In hac habitasse platea dictumst. Nam pellentesque, magna
at tincidunt suscipit, risus mauris consequat erat, sed tempor lorem neque
vel augue.

Quisque facilisis, ipsum a tristique pretium, dolor nunc aliquet ipsum, vitae
condimentum turpis sapien in metus. Aliquam erat volutpat. Nunc vitae libero
sed eros fermentum dignissim. Proin euismod, justo sed aliquet imperdiet, urna
diam consequat eros, sit amet efficitur purus lorem nec sem.

Before you change anything, predict what the starter will do. The learner has
not written a solution yet. Look at the blocks, describe the expected message,
and then press the green Play button once.

#### ~ tutorialhint

The starter only says one message and waits. If the window is crowded, scroll
inside the tutorial pane rather than closing Code Builder.

## Step 2: Add one small action

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed cursus lacus at
quam tincidunt, in consequat eros consequat. Morbi id faucibus risus. Integer
ac ipsum id lectus ultricies feugiat. Donec a mi eu ipsum posuere consequat.
Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac
turpis egestas.

Add one more action after the pause. Keep the order exactly as shown: message,
pause, then message. This is a small change so the learner can compare the
prediction with the result without being overwhelmed by a large program.

```blocks
player.say("Starter program ready")
loops.pause(1000)
player.say("Second message")
```

#### ~ tutorialhint

Drag a `||player:player say||` block below the pause. Type the short message
shown in the example. Do not delete the starter blocks.

## Step 3: Observe the window

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque habitant
morbi tristique senectus et netus et malesuada fames ac turpis egestas. Nulla
 facilisi. Donec sit amet eros non massa faucibus volutpat. Praesent at
 bibendum lectus. Etiam tincidunt, augue vel condimentum tincidunt, enim
 lectus tristique erat, quis sollicitudin purus lorem sit amet augue.

This paragraph exists to test a longer continuous block of prose. It should
wrap naturally, remain readable at the normal Code Builder size, and leave the
code workspace available. A good finished activity would replace this text
with a short explanation, a picture, a question, or a carefully translated
instruction.

## Step 4: Try, notice, and recover

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec at lacus
ultricies, tempor mauris at, interdum massa. Nam sed libero vitae augue
vestibulum tincidunt. Integer varius est id metus pretium, a facilisis massa
pulvinar. Cras non ex id arcu laoreet rhoncus. Sed consequat neque at ligula
maximus, non posuere ipsum blandit.

Press Play again. If the second message does not appear, stop the program,
check that the new block is below the pause, and choose Retry. The important
idea is that a long explanation should still contain a clear action, an
expected result, and a simple recovery path.

```blocks
// @highlight
player.say("Second message")
```

## Step 5: A longer explanation

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut sit amet lacus
velit. Pellentesque habitant morbi tristique senectus et netus et malesuada
fames ac turpis egestas. Vivamus interdum, neque id suscipit sollicitudin,
ligula nibh commodo lectus, non fermentum massa justo non erat. Integer
vulputate metus ac mauris viverra, at bibendum purus aliquet.

Morbi non magna sed ipsum aliquam porttitor. Suspendisse in sem sed arcu
finibus porta. Phasellus quis lectus euismod, faucibus nisl at, tempor libero.
Curabitur sit amet eros at elit pretium dignissim. Aenean at felis vel augue
congue sollicitudin. In aenean, ipsum at dictum interdum, neque nulla porta
magna, vel feugiat justo sem quis libero.

This is still placeholder copy. It lets a team compare short, medium, and long
sections in one tutorial. It also makes it easier to spot whether headings,
code fences, hints, and the green Play flow remain usable when the tutorial
contains substantially more text than a normal learner activity.

#### ~ tutorialhint

If the text feels too dense, split it into several steps. If the text feels
too sparse, add a diagram, a prediction question, or one short example rather
than another wall of words.

## Step 6: Optional extension

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc vitae ligula
vitae massa aliquet sodales. Nam scelerisque lacus non augue posuere, quis
commodo mauris pellentesque. Sed vitae nisl a augue gravida hendrerit. Nulla
facilisi. Donec finibus dolor id leo ultrices, quis interdum velit fermentum.

Try changing the second message to your own short sentence. Keep the first
message unchanged so the learner can see which part of the program they edited.
The final program is intentionally harmless and does not place, remove, or
spawn anything in the world.

```typescript
player.say("Starter program ready")
loops.pause(1000)
player.say("My own message")
```

## Step 7: Final reflection

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin sit amet
consectetur lectus. In hac habitasse platea dictumst. Nam vitae lectus sed
erat pretium porta. Integer ac lacus eu lorem vestibulum tristique. Donec
volutpat nibh id dui cursus, a feugiat arcu consequat. Sed at lorem vel felis
tempor accumsan.

Ask yourself three questions: Was the text easy to scan? Could you find the
next action without rereading everything? Did the tutorial give useful help
when the result was different from the prediction? These questions are more
important than the placeholder wording in this example.

## End of long text test

Lorem ipsum dolor sit amet, consectetur adipiscing elit. This is the end of the
deliberately lengthy sample. In a real activity, replace the placeholder text
with reviewed learner-facing content, keep each step purposeful, and provide a
Welsh file with the same structure when localisation is required.

```blocks
player.say("Long text test complete")
```
