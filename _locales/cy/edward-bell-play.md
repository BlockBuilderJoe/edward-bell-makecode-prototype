### @hideIteration true
### @hideDone true
### @flyoutOnly 1
### @unifiedToolbox true
### @explicitHints 1

# System Cyfathrebu Clychau Edward

```template
agent.teleport(world(18, 57, 12), EAST)
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

Rhaid i system glychau gweithdy Edward anfon SOS: Cloch 1 deirgwaith, Cloch 2 deirgwaith, yna Cloch 1 deirgwaith. Yn gyntaf, pwyntiwch at y deilsen aur, Cloch 1 a Chloch 2, yna dywedwch y llwybr yn uchel: **S, O, S**. Mae eich Asiant yn dechrau ar y deilsen aur yn wynebu Cloch 1, ac nid oes angen gorchymyn sgwrsio. Adeiladwch tra bo'r cod wedi'i stopio, yna pwyswch y botwm Chwarae gwyrdd unwaith i redeg y signal cyfan.

## Cam 1 — Rhagfynegi

Peidiwch â newid y cod cychwynnol eto. Dilynwch ef o'r brig i'r gwaelod. Rhagfynegwch ble bydd yr Asiant yn stopio a pham mae saib 1000 ms gyda phob symudiad. Ysgrifennwch y camau fel ffug-god, tynnwch lun ohonynt, neu actiwch nhw.

#### ~ tutorialhint

Bydd yr Asiant yn canu Cloch 1 deirgwaith, ond bydd yn stopio ar Gloch 1 ar ôl y trydydd caniad. Mae'r seibiau'n gadael ichi glywed pob caniad ac yn rhoi amser i'r plât pwysau ailosod.

## Cam 2 — Rhedeg ac arsylwi

Pwyswch Chwarae unwaith heb drwsio'r cod. Gwiriwch eich rhagfynegiad: a ddychwelodd yr Asiant i'r deilsen aur? A barhaodd yr SOS cyfan? Stopiwch y cod ar ôl arsylwi'r nam.

## Cam 3 — Dadfygio'r S cyntaf

Ychwanegwch un ``||agent:Asiant symud yn ôl||`` ac un ``||loops:saib||`` ar ôl trydydd caniad Cloch 1. Mae hyn yn cwblhau'r patrwm dibynadwy: ymlaen, saib, yn ôl, saib.

```blocks
agent.move(FORWARD, 1)
loops.pause(1000)
agent.move(BACK, 1)
loops.pause(1000)
```

## Cam 4 — Troi at O

Trowch yr Asiant o gwmpas i wynebu Cloch 2. Mae pob tro yn 90 gradd, felly ychwanegwch ddau floc ``||agent:Asiant troi i'r chwith||``.

```blocks
agent.turn(LEFT_TURN)
agent.turn(LEFT_TURN)
```

## Cam 5 — Adeiladu O

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

## Cam 6 — Dychwelyd at S a phrofi

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
