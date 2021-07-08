# Javascript and C++ mixin Debugging

## Javascript
add following configuration in launch.json
```
    {
      "name": "node:attach",
      "port": 9229,
      "request": "attach",
      "skipFiles": [
        "<node_internals>/**"
      ],
      "type": "pwa-node"
    }
```

## Addon(C++)
add following configuration in launch.json
```
    {
      "type": "lldb",
      "request": "launch",
      "name": "lldd:node",
      "program": "node",
      "args": ["--inspect-brk", "${workspaceFolder}/hello.js"],
      "cwd": "${workspaceFolder}",
      "preLaunchTask": "addon: build"
    }
```

## JS C++ mixin
see [launch.json](./launch.json)


## Reference
[1]. Vscode Debugging 
https://code.visualstudio.com/Search?q=debugging

[2]. Vscode Debugging : https://code.visualstudio.com/docs/editor/debugging#_launchjson-attributes

[3]. Node.js debugging in VS Code : https://code.visualstudio.com/docs/nodejs/nodejs-debugging

[4]. Browser debugging in VS Code : https://code.visualstudio.com/docs/nodejs/browser-debugging