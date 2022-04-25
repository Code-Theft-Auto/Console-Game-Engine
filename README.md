# ConsoleGameEngine
### C# Graphics Library for drawing graphics in Windows Command Prompt

![downloads](https://img.shields.io/github/downloads/BananaBoii600/Console-Game-Engine/v1.0.0)
![release](https://img.shields.io/github/release/BananaBoii600/Console-Game-Engine)
![licence](https://img.shields.io/github/license/BananaBoii600/Console-Game-Engine)
![issues](https://img.shields.io/github/issues-raw/BananaBoii600/Console-Game-Engine)

---
**ConsoleGameEngine** is a C# library that wraps around the `System.Console` class, adding enhanced 
functionality for displaying graphics. Implements a new ConsoleGame abstract, a custom buffer, custom 
color palette, fullscreen capabilites, input handling and more.

<p align="center">
  <img src="https://github.com/BananaBoii600/Console-Game-Engine/blob/master/Media/monkeyspin.gif" />
</p>

## Installation / Getting Started
- [Download Lastest Build](https://github.com/BananaBoii600/Console-Game-Engine/releases/)
- Clone git repo and build yourself
> git clone https://github.com/BananaBoii600/Console-Game-Engine.git

<br />

After installing you'll have to:
1. Import `ConsoleGameEngine.dll` to project.
2. Reference the namespace `using ConsoleGameEngine;`

---

## Uses
- retro-terminal-styled games and applications
- easy-to-use graphics library for basic and advanced graphics in games and applications
- ~~Creating heavy 3D graphics running in 4K~~

Does the last apply to you? Then sorry, *this is not the library you are looking for.*

## Usage / Features
Library contains two main classes, `ConsoleEngine` and `ConsoleGame`

- Custom character screen buffer, allows clearing and blitting to console window
- Console colors with full rgb capabilities
- Custom & premade Palettes, used for changing console window palette
- Accessing and setting pixels individually
- Functions to draw basic shapes and primitives (Triangles, Rectangles, Lines etc.)
- Writing characters to screen using plain-text and FIGlet fonts
- Multiple game loops, including fixed framerate and deltatime settings
- Point and Vector class, for int and float positions
- Setting console window settings, changing window size and running console borderless
- Input handling

#### ConsoleEngine
Is used to draw to the screen, replacement for the `System.Console` class *(kind of)*

```c#
using ConsoleGameEngine;
...
Engine = new ConsoleEngine(windowWidth, windowHeight, fontWidth, fontHeight);

Engine.SetPixel(new Point(8, 8), ConsoleCharacter.Full, 15);

```

#### ConsoleGame
Keeps an instance of the `ConsoleEngine` and implements game loops.

**Note** *Not neccessary, you could use the ConsoleEngine as is*

```c#
using ConsoleGameEngine;
...

new AppName.Construct(windowWidth, windowHeight, fontWidth, fontHeight, FramerateMode.Unlimited);
class AppName : ConsoleGame {
  public override void Create() {
  }
  
  public override void Update() {
  }
  
  public override void Render() {
  }
}
```

##### Try out some example games over [here](https://github.com/ollelogdahl/ConsoleGameEngine/tree/master/Examples)

## Notes
- Color palette limited to 16 colors in a single session *(this is an internal limitation, see [MDSN](https://docs.microsoft.com/en-us/windows/console/console-screen-buffer-infoex))*
- Only **ONE** reference to a `ConsoleEngine` is allowed per session
- Press *Delete Key* to close application if running in borderless
---

<p align="center">
  <img src="https://github.com/BananaBoii600/Console-Game-Engine/blob/master/Media/cave.gif" width = 512 heigth = 384 />
</p>

## This project was heavily inspired by the github user logan dahl

## Licensing

This project, and all code it contains, is licensed under *The Unlicense* and can be read [here](UNLICENSE).
