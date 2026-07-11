### @hideIteration true
### @hideDone true
### @flyoutOnly 1
### @unifiedToolbox true
### @explicitHints 1

# System Cyfathrebu Clychau Edward

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
```

## Briff y Genhadaeth @showdialog

Rhaid i system glychau gweithdy Edward anfon SOS: Cloch 1 deirgwaith, Cloch 2 deirgwaith, yna Cloch 1 deirgwaith. Nid oes angen gorchymyn sgwrsio. Adeiladwch tra bo'r cod wedi'i stopio, yna pwyswch y botwm Chwarae gwyrdd unwaith i redeg y signal cyfan.

## Cam 1

Mae'r cod cychwynnol bron yn anfon yr S cyntaf. Ychwanegwch un ``||agent:Asiant symud yn ôl||`` ac un ``||loops:saib||`` ar ôl trydydd caniad Cloch 1.

#### ~ tutorialhint

Mae pob caniad yn defnyddio'r un patrwm: ymlaen, saib, yn ôl, saib.

```blocks
agent.move(FORWARD, 1)
loops.pause(1000)
agent.move(BACK, 1)
loops.pause(1000)
```

## Cam 2

Trowch yr Asiant o gwmpas i wynebu Cloch 2. Mae pob tro yn 90 gradd, felly ychwanegwch ddau floc ``||agent:Asiant troi i'r chwith||``.

```blocks
agent.turn(LEFT_TURN)
agent.turn(LEFT_TURN)
```

## Cam 3

Anfonwch O drwy ailadrodd y patrwm ymlaen, saib, yn ôl, saib deirgwaith wrth Gloch 2.

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

## Cam 4

Trowch o gwmpas ddwywaith, yna ailadroddwch Gloch 1 deirgwaith ar gyfer yr S olaf. Pwyswch Chwarae unwaith pan fydd y dilyniant cyfan yn barod.

#### ~ tutorialhint

Mae'r byd yn rhoi adborth ar unwaith os bydd y gloch anghywir yn canu. Os yw'n dweud bod y drefn yn anghywir, stopiwch y cod, dewiswch Ailgynnig gan y Mentor, trwsiwch yr adran honno, a phwyswch Chwarae eto.

```blocks
agent.turn(LEFT_TURN)
agent.turn(LEFT_TURN)
agent.move(FORWARD, 1)
loops.pause(1000)
agent.move(BACK, 1)
loops.pause(1000)
```

## Estyniad

Byrhewch y rhaglen gyda dolen ailadrodd a swyddogaeth. Mae'r tair galwad swyddogaeth yn rhedeg unwaith, o'r brig i'r gwaelod, pan fydd Chwarae yn cael ei bwyso.

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
```
