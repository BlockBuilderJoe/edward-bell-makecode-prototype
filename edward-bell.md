### @hideIteration true
### @hideDone true
### @flyoutOnly 1
### @unifiedToolbox true
### @explicitHints 1

# Edward's Bell Communication System

```template
player.onChat("sos", function () {
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
})
```

## Mission Brief @showdialog

Edward's workshop bell system must send SOS. Bell 1 is S. Bell 2 is O. Repair the starter code so the Agent rings Bell 1 three times, Bell 2 three times, then Bell 1 three times again.

## Step 1

The starter code already has a chat command called ``||player:sos||``. It almost sends the first S, but after the third ring the Agent must step back to the gold reset tile.

#### ~ tutorialhint

Add one more ``||agent:agent move back||`` and a ``||loops:pause||`` after the final Bell 1 ring.

```blocks
player.onChat("sos", function () {
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
})
```

## Step 2

Now turn the Agent around to face Bell 2. Each Agent turn block turns 90 degrees, so use two turns.

#### ~ tutorialhint

Add two ``||agent:agent turn left||`` blocks after the first S pattern.

```blocks
player.onChat("sos", function () {
    agent.move(FORWARD, 1)
    loops.pause(1000)
    agent.move(BACK, 1)
    loops.pause(1000)
    agent.turn(LEFT_TURN)
    agent.turn(LEFT_TURN)
})
```

## Step 3

Send the O by ringing Bell 2 three times. The same forward, pause, back, pause pattern works because the Agent is now facing Bell 2.

#### ~ tutorialhint

Copy the ring pattern and place it after the two turns.

```blocks
player.onChat("sos", function () {
    agent.turn(LEFT_TURN)
    agent.turn(LEFT_TURN)
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
})
```

## Step 4

Turn back to Bell 1 and send the final S. When you press Play and run ``sos`` in chat, the world will check the Agent's sequence.

#### ~ tutorialhint

Use two more turns, then repeat the Bell 1 pattern.

```blocks
player.onChat("sos", function () {
    agent.turn(LEFT_TURN)
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, 1)
    loops.pause(1000)
    agent.move(BACK, 1)
    loops.pause(1000)
})
```

## Extension

Your code works, but it is long. Use a ``||loops:repeat||`` loop to shorten one letter, then make a function called ``||functions:formLetter||`` and call it three times.

#### ~ tutorialhint

This extension keeps the same behaviour but makes the main program easier to read and debug.

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
player.onChat("sos", function () {
    formLetter()
    formLetter()
    formLetter()
})
```

```ghost
for (let index = 0; index < 3; index++) {
}
function formLetter () {
}
player.onChat("sos", function () {
})
agent.move(FORWARD, 1)
agent.move(BACK, 1)
agent.turn(LEFT_TURN)
loops.pause(1000)
```
