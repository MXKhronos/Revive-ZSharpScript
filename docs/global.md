---
layout: default
title: global
nav_order: 1
---

These are global values that exists in the **ZSharp** environment. 

---

### Lua

| Type | Key |
| --- | --- |
| function | getfenv |
| function | ipairs |
| table | math |
| function | next |
| function | pairs |
| function | pcall |
| function | print |
| table | string |
| function | select |
| table | table |
| table | task |
| function | tick |
| function | tonumber |
| function | tostring |
| function | typeof |
| function | unpack |
| | |
| table | CFrame |
| table | Vector2 |
| table | Vector3 |

### ZSharp

| Type | Key |
| --- | --- |
| string | ScriptName |
| | |
| table | Audio |
| table | ZInstance |
| | |
| function | [help](#help) |
| function | [log](#log) |
| function | [new](#new) |

---

### Method Description

<a name="help"></a>
`void` **help**(path: *string*)
- Outputs help hints and descriptions.
- Any tables within ZSharp can be explored into with `help`.

Examples:

```lua
help("Audio.Play"); -- Shows you how to use Audio.Play.

help("ZInstance.Classes"); -- Shows you all available classes

help("ZInstance.List"); -- Shows you how to use ZInstance.List.
```

---

<a name="log"></a>
`void` **log**(...)
- Basically print, but properly formats value.

---

<a name="new"></a>
`ZInstance` **new**(className: *string*)
- Instantiates a new instance of `ClassName`.

Examples:
- Spawns a new sound with volume set to 1 and assign a `SoundId`.

```lua
local zsound = new("ZSound"){
	Volume = 1;
	SoundId = "rbxassetid://3430334696"; -- "Collectible"
};

task.wait(3);

zsound:Play();
```

---