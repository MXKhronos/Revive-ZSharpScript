---
layout: default
title: Home
nav_order: 1
description: "Welcome to Z-Sharp."
permalink: /
---

Welcome to Z-Sharp.

ZSharp runs on a sandboxed `lua` environment on the Revive engine.

1. [Getting Started](#getting-started-using-zsharp)
2. [Terminal](#terminal)
3. [ZSCode](#zscode)
4. [Libraries](#libraries)
5. [Examples](#examples)

### Getting Started using ZSharp:
- Locate and open up a terminal in [game](https://www.roblox.com/games/141084271/Rise-of-the-Dead).

---
## Terminal

![Terminal](resources/images/terminal.png)

The terminal mimicks a unix-based terminal but currently it has no file structure.

There are **two ways of running ZSharp**:
1) Using the `run` command on the terminal, anything after the `run` command will be interpreted as ZSharp.

```lua
run log("Hello World!");
```

2) Run the `code` command which brings up **ZSCode**, a text editor mimicking **VSCode**.

>⚡You can use `fullscreen` to fullscreen the terminal.

---
## ZSCode

![ZSCode](resources/images/zscode.png)

Currently, you'll be defaulted to `untitled.zs` and there are no saving and loading functionality. The output which was once the terminal's output will now show up as the output window.

To run your script, you can press the **Run** button on the bottom left.

>⚡You can close **ZSCode** by entering `code` command again into the bottom.

---

## Classes

- [global](docs/global)
- [ZInstance](docs/ZInstance)

---
### Examples
These are examples of what you can currently do in ZSharp. For more details, you will have to read through [Libraries](#libraries).

---

`void` **help**(path: *string*)
**ZSharp** has a built in `help` function to list available libraries and shows it's hints and descriptions.

> More info [here](docs/global#help)

Try running some of these in `run` or `code`.
```lua
help("Audio.Play"); -- Shows you how to use Audio.Play.

help("ZInstance.Classes"); -- Shows you all available classes

help("ZInstance.List"); -- Shows you how to use ZInstance.List.
```

---

#### Playing a sound
```lua
Audio:Play("Boombox:Stepping Up");
```

This plays the sound called `Boombox:Stepping Up` since it exists in the Revive engine, but you can do more since `Audio:Play` returns a [ZSound](docs/ZSound), you can use their methods and change their properties. `run help("ZInstance.Classes.ZSound")` for more.

>⚡To stop the sound. Use `ZInstance:DestroyList("ZSound", true)`. Which destroys all instances matching the word `ZSound` in its name.
>
>More info on [ZInstance](docs/ZInstance)

```lua
local zsound = Audio:Play("Boombox:Stepping Up");
zsound.Volume = 1;

task.wait(5);
zsound:Destroy();
```
---

#### Spawning an instance

```lua
local zsound = new("ZSound"){
    SoundId = "rbxassetid://142376088"; -- Parry Gripp - Raining Tacos
};

zsound:Play(); -- Plays the newly spawned sound.
```

> More info on [`new(className: *string*)`](docs/global#new).

