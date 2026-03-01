# Super Nintendo

A Super Nintendo emulator designed for running in vanilla JavaScript pre-ECMAScript 2015 (no WebAssembly). Simply open the link below, click the red icon, and select a ROM file in `SFC` or `SMC` format from your computer; it will be loaded and booted automatically.

## Links:

- [Super Nintendo emulator](https://lrusso.github.io/SuperNintendo/SuperNintendo.htm)
- [Demo booting a sample game](https://lrusso.github.io/SuperNintendo/SuperNintendo.htm?demo)

## Screenshots:

![alt screenshot1](https://lrusso.github.io/SuperNintendo/SCREENSHOT1.jpg)

![alt screenshot2](https://lrusso.github.io/SuperNintendo/SCREENSHOT2.jpg)

![alt screenshot3](https://lrusso.github.io/SuperNintendo/SCREENSHOT3.jpg)

## How to use it:

Examples of loading local and online files can be found [here](https://github.com/lrusso/SuperNintendo/blob/main/SuperNintendo.htm#L132-L178) and [here](https://github.com/lrusso/SuperNintendo/blob/main/SuperNintendo.htm#L206-L247).

```js
embedSuperNintendo({
  container: "game",
  name: "Super Metroid",
  rom: romFile,
  player1: {
    up: "ArrowUp",
    down: "ArrowDown",
    left: "ArrowLeft",
    right: "ArrowRight",
    a: "KeyW",
    b: "KeyQ",
    x: "KeyS",
    y: "KeyA",
    l: "KeyZ",
    r: "KeyX",
    start: "Enter",
    select: "ShiftRight",
  },
  player2: {
    up: "KeyI",
    down: "KeyK",
    left: "KeyJ",
    right: "KeyL",
    a: "KeyU",
    b: "KeyH",
    x: "KeyO",
    y: "KeyN",
    l: "KeyP",
    r: "KeyM",
    start: "KeyB",
    select: "KeyV",
  },
  cbStarted: function cbStarted() {
    console.log("Emulator started.")
  },
})
```

| Parameter |    Type     | Required | Default value | Description               |
| :-------- | :---------: | :------: | :-----------: | :------------------------ |
| container |   string    |   yes    |       –       | Target element ID.        |
| name      |   string    |   yes    |       –       | Game name.                |
| rom       | ArrayBuffer |   yes    |       –       | ROM file.                 |
| player1   |   object    |    no    |       –       | Player 1 keys.            |
| player2   |   object    |    no    |       –       | Player 2 keys.            |
| cbStarted |  function   |    no    |       -       | Called on emulator start. |

## Special keys:

| Action          | macOS Shortcut | Windows Shortcut | Safari Shortcut |
| :-------------- | :------------: | :--------------: | :-------------: |
| Save state      |  Command + 1   |     Ctrl + 1     |    Ctrl + 1     |
| Load state      |  Command + 2   |     Ctrl + 2     |    Ctrl + 2     |
| Toggle sound    |  Command + 3   |     Ctrl + 3     |    Ctrl + 3     |
| Fullscreen mode |  Command + F   |     Ctrl + F     |    Ctrl + F     |
| Reset game      |  Command + R   |     Ctrl + R     |    Ctrl + R     |

## Main differences with the original project:

- Transpiled JS to pre-ES2015 via `node ConverterES5.js SuperNintendo.js`.

## This is a modified version of snes9x2005-wasm:

https://github.com/lrusso/snes9x2005-wasm

**NOTE:** Emscripten 4.0.23 was used to build the emulator.
