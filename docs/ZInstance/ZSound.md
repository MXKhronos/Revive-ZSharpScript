---
layout: default
title: ZSound
parent: ZInstance
nav_order: 1
---

**Inherits:** [ZInstance](ZInstance)
### Description
A sandboxed version of [Sound](https://create.roblox.com/docs/reference/engine/classes/Sound).

### Properties

| Type | Key | Default Value |  
| --- | --- | --- |  
| string | ClassName | ZSound |  
| number | PlaybackSpeed | 1 |
| string | SoundId |  |
| number | Volume | 0.5 |

### Methods

| Return Type | Name |
| --- | --- |
| void | [Play](#play) () |
| void | [Stop](#stop) () |

---

### Property Descriptions

`number` **PlaybackSpeed** *= 1*
- `PlaybackSpeed` defaults to 1 for new instances but if you use [Audio:Play](Audio#play), the default value may vary.

---

`string` **SoundId** *= ""*
- Changing SoundId will stop the sound.

Example:

```lua
local zsound = Audio:Play("Boombox:Stepping Up");
task.wait(3);
zsound.SoundId = "rbxassetid://1836846557"; -- "Boombox:Get Up On Your Feet"
zsound:Play();
```

Changes the playing sound to *"Boombox:Get Up On Your Feet"* after 3 seconds.

---

`number` **Volume** *= 0.5*
- `Volume` defaults to 0.5 for new instances but if you use `Audio:Play()`, the default value may vary.

---

### Method Descriptions
<a name="play"></a>
`void` **Play**()
- Plays the sound

---

<a name="stop"></a>
`void` **Stop**()
- Stops the sound

---
