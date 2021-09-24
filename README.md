# electron-iohook

[iohook](https://github.com/wilix-team/iohook) for Electron, with prebuilt binaries.


## Limitations

- It only works for the latest Electron, currently version 15.
- It only works for macOS and windows, no Linux support.
- It only works for 64-bit OS, no 32-bit support.
- It doesn't work with Node.js. It is for Electron only.

The limitations above could be worked around, of course. 
Please fork this project and do it yourself. 


## Usage

```
import ioHook, {IOHookEvent} from 'electron-iohook';

ioHook.on('mousedown', (event: IOHookEvent) => {
  console.log(event);
});

ioHook.start();
```


## How to build the latest prebuilt

Git clone official [iohook](https://github.com/wilix-team/iohook).

```
npm install
```

### macOS

```
node build.js --runtime electron --version 15.0.0 --abi 98 --upload=false
```

Built files are in `./build/Release` folder, they are

- iohook.node
- uiohook.dylib

### windows

Install VS Studio 2019 with C++ desktop development kit.

```
node build.js --runtime electron --version 15.0.0 --abi 98 --upload=false --msvs_version=2019
```

Built files are in `./build/Release` folder, they are

- iohook.node
- uiohook.dll

### How do I know Electron's abi?

```
./node_modules/electron/cli.js -a
```
