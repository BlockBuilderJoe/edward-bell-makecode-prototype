### @explicitHints 1

# Edward's Bell: Python editor example

```python-template
agent.teleport(world(18, 57, 12), EAST)
agent.move(FORWARD, 1)
loops.pause(1000)
```

## Check the editor @showdialog

This example opens Minecraft Code Builder in its Python text editor. The
starter sends the Agent from the gold tile to Bell 1 and pauses, but it does
not bring the Agent back.

## Add the missing Python line

Click after `loops.pause(1000)` and add this line:

```python
agent.move(BACK, 1)
```

Keep `BACK` in capital letters and leave the distance as `1`.

## Predict, then run

Predict where the Agent will finish, then press the green Play button once. It
should ring Bell 1 and return to the gold tile.

If it stays on the bell, check the spelling, brackets, comma, and indentation,
then run the program again.

```python
agent.teleport(world(18, 57, 12), EAST)
agent.move(FORWARD, 1)
loops.pause(1000)
agent.move(BACK, 1)
```
