### @hideIteration true
### @hideDone true
### @flyoutOnly 1
### @unifiedToolbox true
### @explicitHints 1

# Practice Bell 1

```template
agent.teleport(world(18, 57, 12), EAST)
agent.move(FORWARD, 1)
loops.pause(1000)
```

## Mission Brief @showdialog

Your Agent will start on the gold tile, facing Bell 1. Before you build, point to the gold tile and Bell 1 and predict where **forward 1** and **back 1** will take it. You do not need to type a command. Build while the code is stopped, then press the green Play button once to try it.

## Step 1

The starter already places the Agent, moves it forward and waits. Add one ``||agent:agent move back||`` block after the pause so it returns safely to gold.

#### ~ tutorialhint

Set the direction to **back** and the distance to **1**.

```blocks
agent.move(FORWARD, 1)
loops.pause(1000)
agent.move(BACK, 1)
```

## Step 2

Press the green Play button once. The world checks the Agent in the platform and the Mentor will guide the next step. If you need another try, stop the code, use the Mentor's Retry button, make your change, and press Play again.

```ghost
agent.move(FORWARD, 1)
agent.move(BACK, 1)
loops.pause(1000)
```
