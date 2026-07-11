### @hideIteration true
### @hideDone true
### @flyoutOnly 1
### @unifiedToolbox true
### @explicitHints 1

# Ymarfer Cloch 1

```template
agent.teleport(world(18, 57, 12), EAST)
agent.move(FORWARD, 1)
loops.pause(1000)
```

## Briff y Genhadaeth @showdialog

Bydd eich Asiant yn dechrau ar y deilsen aur, yn wynebu Cloch 1. Cyn adeiladu, pwyntiwch at y deilsen aur a Chloch 1 a rhagfynegwch ble bydd **ymlaen 1** ac **yn ôl 1** yn mynd ag ef. Nid oes angen teipio gorchymyn. Adeiladwch tra bo'r cod wedi'i stopio, yna pwyswch y botwm Chwarae gwyrdd unwaith i roi cynnig arno.

## Cam 1

Mae'r cod cychwynnol eisoes yn gosod yr Asiant, yn ei symud ymlaen ac yn aros. Ychwanegwch un bloc ``||agent:Asiant symud yn ôl||`` ar ôl y saib er mwyn iddo ddychwelyd yn ddiogel i'r deilsen aur.

#### ~ tutorialhint

Gosodwch y cyfeiriad i **yn ôl** a'r pellter i **1**.

```blocks
agent.move(FORWARD, 1)
loops.pause(1000)
agent.move(BACK, 1)
```

## Cam 2

Pwyswch y botwm Chwarae gwyrdd unwaith. Mae'r byd yn gwirio'r Asiant ar y platfform a bydd y Mentor yn eich arwain at y cam nesaf. Os oes angen cynnig arall arnoch, stopiwch y cod, defnyddiwch fotwm Ailgynnig y Mentor, gwnewch eich newid, a phwyswch Chwarae eto.

```ghost
agent.move(FORWARD, 1)
agent.move(BACK, 1)
loops.pause(1000)
```
