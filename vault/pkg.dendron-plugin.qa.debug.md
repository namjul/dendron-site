---
id: 626zjfxg91OFbDse
title: Debug
desc: ''
updated: 1627140434647
created: 1627140313776
---

## Launch
This goes over how to launch the extension from your local source. 

1. launch the `Run Extnesion: Local` build task (copied below for reference)
  ```json
      {
        "name": "Run Extension",
        "type": "extensionHost",
        "request": "launch",
        "runtimeExecutable": "${execPath}",
        "args": [
          "--disable-extensions",
          "--extensionDevelopmentPath=${workspaceFolder}"
        ],
        "outFiles": [
          "${workspaceFolder}/out/**/*.js"
        ],
        "env": {
          "STAGE": "dev",
          "VSCODE_DEBUGGING_EXTENSION": "dendron"
        }
      },
  ```

## Debug
<!-- How to step through tests using debugger -->

### Breakpoints
<!-- Setting Breakpoints -->
For testing [[Dendron Plugin|pkg.dendron-plugin]], you can set a regular breakpoint inside of VSCode.

For non plugin code, this won't work.  The current workaround is to manually add a `debugger;` statement inside the code. The extension will hit it when restarted under the debugger. 

### Verbose Logs

- set in `dendorn.workspace.config`

```json
"dendron.logLevel": "debug",
```
