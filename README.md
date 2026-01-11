# Build FORK Project

Install [Visual Studio Build Tools](https://aka.ms/vs/17/release/vs_BuildTools.exe)

- Desktop development with C++

Admin power shell

```
npm i
npm run build
npm run package:dir
```

Find build in: `C:\git\cs-demo-manager\dist\win-unpacked`

Point to built version

`Set-Alias -Name csdm -Value "C:\git\cs-demo-manager\dist\win-unpacked\csdm.cmd"`

**Environment variables**

Update PATH

- from `C:\Users\dayon\AppData\Local\Programs\cs-demo-manager`
- to `C:\git\cs-demo-manager\dist\win-unpacked`

**Rebuild**

```
npm run build; npm run package:dir
```

**Rebuild C++**

Folder cs-demo-manager

```
git submodule update --init --recursive
```

Visual Studio

- cs2-server-plugin > `Rebuild` (Release)
- Verify date modified `C:\git\cs-demo-manager\dist\win-unpacked\resources\static\cs2\server.dll`

DEBUG
```
const mandatoryCommands = [
  'sv_cheats 1',
  // --- START DEBUG MODIFICATION ---
  'cl_showpos 1', // Draws Velocity/Position stats (Red/Green text top-left)
  'cl_showfps 1', // Draws FPS counter (Green/Red text top-left)
  'say ">>> CSDM DEBUG <<<"', // Prints to the in-game Chat window
  // --- END DEBUG MODIFICATION ---
  'volume 1',
  'cl_hud_telemetry_frametime_show 0',
  'cl_hud_telemetry_net_misdelivery_show 0',
  'cl_hud_telemetry_ping_show 0',
  'cl_hud_telemetry_serverrecvmargin_graph_show 0',
  'cl_trueview_show_status 0',
  'r_show_build_info 1', // CHANGE THIS FROM 0 TO 1 (Shows build date watermark on screen)
  'mirv_streams record screen enabled 1',
];
```