### @hideIteration true
### @hideDone true
### @flyoutOnly 1
### @unifiedToolbox true
### @explicitHints 1

# Practice Bell 1

```template
player.onChat("ring1", function () {
    agent.move(FORWARD, 1)
    loops.pause(1000)
})
```

## Mission Brief @showdialog

Before sending SOS, practise one signal. Move the Agent forward to Bell 1, wait, then move the Agent back to the gold tile.

## Step 1

The starter code already moves the Agent forward to Bell 1. Add the missing back step so the Agent returns to the gold tile.

#### ~ tutorialhint

Place ``||agent:agent move back||`` after the pause.

```blocks
player.onChat("ring1", function () {
    agent.move(FORWARD, 1)
    loops.pause(1000)
    agent.move(BACK, 1)
})
```

## Step 2

Press Play, then run ``ring1`` in chat. If the Agent rings Bell 1 and returns to gold, the full SOS challenge unlocks.

```ghost
player.onChat("ring1", function () {
})
agent.move(FORWARD, 1)
agent.move(BACK, 1)
loops.pause(1000)
```
