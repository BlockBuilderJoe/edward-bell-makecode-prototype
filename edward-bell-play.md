### @hideIteration true
### @hideDone true
### @flyoutOnly 1
### @unifiedToolbox true
### @explicitHints 1

# Edward's Bell Communication System

```template
agent.move(FORWARD, 1)
loops.pause(1000)
agent.move(BACK, 1)
loops.pause(1000)
agent.move(FORWARD, 1)
loops.pause(1000)
agent.move(BACK, 1)
loops.pause(1000)
agent.move(FORWARD, 1)
loops.pause(1000)
if (agent.inspect(AgentInspection.Block, DOWN) == GOLD_BLOCK) {
    player.say("Agent is home. Read the Mentor's SOS result.")
} else {
    player.say("Not finished. Return the Agent to gold, fix the blocks, then press Play again.")
}
```

## Mission Brief @showdialog

Edward's workshop bell system must send SOS: Bell 1 three times, Bell 2 three times, then Bell 1 three times. You do not need a chat command. Build while the code is stopped, then press the green Play button once to run the whole signal.

## Step 1

The starter almost sends the first S. Add one ``||agent:agent move back||`` and one ``||loops:pause||`` after the third Bell 1 ring, before the feedback check.

#### ~ tutorialhint

Every ring uses the same pattern: forward, pause, back, pause.

```blocks
agent.move(FORWARD, 1)
loops.pause(1000)
agent.move(BACK, 1)
loops.pause(1000)
```

## Step 2

Turn the Agent around to face Bell 2. Each turn is 90 degrees, so add two ``||agent:agent turn left||`` blocks.

```blocks
agent.turn(LEFT_TURN)
agent.turn(LEFT_TURN)
```

## Step 3

Send O by repeating the forward, pause, back, pause pattern three times at Bell 2.

```blocks
agent.move(FORWARD, 1)
loops.pause(1000)
agent.move(BACK, 1)
loops.pause(1000)
agent.move(FORWARD, 1)
loops.pause(1000)
agent.move(BACK, 1)
loops.pause(1000)
agent.move(FORWARD, 1)
loops.pause(1000)
agent.move(BACK, 1)
loops.pause(1000)
```

## Step 4

Turn around twice, then repeat Bell 1 three times for the final S. Keep the feedback check at the very end. Press Play once when the entire sequence is ready.

#### ~ tutorialhint

The world gives immediate wrong-bell feedback. If it says the order is wrong, stop the code, choose Retry from the Mentor, fix that section, and press Play again.

```blocks
agent.turn(LEFT_TURN)
agent.turn(LEFT_TURN)
agent.move(FORWARD, 1)
loops.pause(1000)
agent.move(BACK, 1)
loops.pause(1000)
```

## Extension

Shorten the program with a repeat loop and a function. The three function calls run once, from top to bottom, when Play is pressed.

```blocks
function formLetter () {
    for (let index = 0; index < 3; index++) {
        agent.move(FORWARD, 1)
        loops.pause(1000)
        agent.move(BACK, 1)
        loops.pause(1000)
    }
    agent.turn(LEFT_TURN)
    agent.turn(LEFT_TURN)
}
formLetter()
formLetter()
formLetter()
```

```ghost
for (let index = 0; index < 3; index++) {
}
function formLetter () {
}
agent.move(FORWARD, 1)
agent.move(BACK, 1)
agent.turn(LEFT_TURN)
loops.pause(1000)
if (agent.inspect(AgentInspection.Block, DOWN) == GOLD_BLOCK) {
    player.say("Agent is home")
} else {
    player.say("Try again")
}
```
