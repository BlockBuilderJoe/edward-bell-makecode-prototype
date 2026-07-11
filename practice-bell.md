### @hideIteration true
### @hideDone true
### @flyoutOnly 1
### @unifiedToolbox true
### @explicitHints 1

# Practice Bell 1

```template
agent.move(FORWARD, 1)
loops.pause(1000)
if (agent.inspect(AgentInspection.Block, DOWN) == GOLD_BLOCK) {
    player.say("Great work! The Agent returned to gold.")
} else {
    player.say("Not quite. Add move back, then press Play again.")
}
```

## Mission Brief @showdialog

Move the Agent forward to Bell 1, wait, then move it back to the gold tile. You do not need to type a command. Build while the code is stopped, then press the green Play button once to try it.

## Step 1

The starter already moves forward and waits. Add one ``||agent:agent move back||`` block after the pause and before the feedback check.

#### ~ tutorialhint

Set the direction to **back** and the distance to **1**.

```blocks
agent.move(FORWARD, 1)
loops.pause(1000)
agent.move(BACK, 1)
```

## Step 2

Press the green Play button once. The world checks the gold tile automatically: it celebrates a correct return or tells you exactly what to fix. If you need another try, stop the code, use the Mentor's Retry button, make your change, and press Play again.

```ghost
agent.move(FORWARD, 1)
agent.move(BACK, 1)
loops.pause(1000)
if (agent.inspect(AgentInspection.Block, DOWN) == GOLD_BLOCK) {
    player.say("Great work!")
} else {
    player.say("Try again")
}
```
