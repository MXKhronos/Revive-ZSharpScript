---
layout: default
title: Audio
parent: Class
nav_order: 1
---

### Description
Audio is a ZSharp library derived from Revive Engine's Audio Librar. It easy and convenient to play [ZSound](ZSound) on the fly.

### Properties

| Type | Key | Default Value |  
| --- | --- | --- |
| No available properties |

### Methods

| Return Type | Name |
| --- | --- |
| [ZSound](ZSound) | [Play](#play) (soundName: *string*) |
| [ZSound](ZSound) | [New](#new) (soundName: *string*) |
| table | [Find](#find) (pattern: *string?*) |

---
### Property Descriptions

---
### Method Descriptions

<a name="play"></a>
`ZSound` **Play**(soundName: *string*)
- Plays the specified sound with default values.
- Function returns a [ZSound](ZSound).

Examples:

```lua
local zsound = Audio:Play("Boombox:Stepping Up");	-- Plays the sound;
zsound.PlaybackSpeed = 2;	-- Change to play the audio at twice the speed.
```

---

<a name="new"></a>
`ZSound` **New**(soundName: *string*)
- Spawns a new sound, similarly to `Audio:Play` but it won't auto play the sound.

---

<a name="find"></a>
`table` **Find**(pattern: *string?*)
- `pattern` & `search` works the same as [List](#list)
- Returns a table of sound names that `string.match` the `pattern`.